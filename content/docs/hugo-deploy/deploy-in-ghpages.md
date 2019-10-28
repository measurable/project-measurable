---
title: "ghpages로 발행"
date: 2019-10-27T19:46:27+09:00
categories:
    - generic
tags:
    - generic
keywords:
inspired:
motivation: ""
draft: true
---

<em class="strongkorean">주의: </em>
<em class="emkorean">
ghpages의 full URL을 사이트 설정의 `baseURL` 키값으로 주어야 한다.
ghpages URL의 기본값을 사용한다면 `<USERNAME>.github.io/<PROJECT>/`이다.
</em>

gh project page는 다음 둘 중 하나의 방식으로 만든다.

- from Your `gh-pages` branch
- from `/docs` folder on master branch

## Deployment of Project Pages From Your gh-pages branch

`master` 브랜치를 published site로 설정할 수도 있다.
그러나,
별도의 `gh-pages` 브랜치를 두는 것은 조금 더 복잡하긴 하지만, 다음과 같은 장접이 있다.

- 사이트 소스와 생성된 웹사이트 각각에 대해 별도의 버전관리를 할 수 있다.
- `/docs` 방식과 달리 hugo의 기본값인 `public` 폴더를 사용한다.

### Preparations for `gh-pages` Branch

#### Add the public Folder

먼저, 프로젝트 루트의 `.gitignore` 파일에 `public` 폴더를 추가해서,
`master` 브랜치가 이 폴더를 무시하도록 한다.

```zsh
echo "public" >> .gitignore
```

#### Initialize Your gh-pages Branch

`gh-pages` 브랜치를 git의 prphan 브랜치로 초기화한다.

```zsh
git checkout --orphan gh-pages
git reset --hard
git commit --allow-empty -m "Initializing gh-pages branch"
git push upstream gh-pages
git checkout master
```

### Build and Deployment

git의 [worktree feature](https://git-scm.com/docs/git-worktree)를 사용해서 `gh-pages` 브랜치를 `public` 폴더로 check-out한다.
worktree는 로컬 저장소의 서로 다른 브랜치들을 각각의 디렉토리로 check-out되도록 해준다.


```zsh
rm -rf public
git worktree add -B gh-pages public upstream/gh-pages
```

`hugo` 명령으로 사이트를 다시 생성하고, 생성된 파일들을 `gh-pages` 브랜치로 커밋한다:

**`commit-gh-pages-files.sh`**

```
hugo
cd public && git add --all && git commit -m "Publishing to gh-pages" && cd ..
```

로컬의 `gh-pages` 브랜치가 제대로 생성됐으면 원격 저장소로 `push`한다:

```zsh
git push upstream gh-pages
```

#### `gh-pages`를 Publish Branch로 설정

Publishing branch는 GitHub UI에서 설정해 주어야 한다.
`gh-pages` 브랜치를 만들면 이 브랜치가 자동으로 publishing branch로 설정된다. GitHub 프로젝트에서 수동으로 설정할 수도 있다.

1. Go to `Settings > GitHub Pages`
2. From `Source`, select `gh-pages branch` and then `Save`. If the option isn't enabled, you likely have not created the branch yet OR you have not pushed the branch from your local machine to the hosted repository on GitHub.
After a short while, you'll see the updated contents on your GitHub Pages site.

### Put it Into a Script

**`publish_to_ghpages.sh`**

```
#!/bin/sh

if [ "`git status -s`" ]
then
    echo "The working directory is dirty. Please commit any pending changes."
    exit 1;
fi

echo "Deleting old publication"
rm -rf public
mkdir public
git worktree prune
rm -rf .git/worktrees/public/

echo "Checking out gh-pages branch into public"
git worktree add -B gh-pages public upstream/gh-pages

echo "Removing existing files"
rm -rf public/*

echo "Generating site"
hugo

echo "Updating gh-pages branch"
cd public && git add --all && git commit -m "Publishing to gh-pages (publish.sh)"

#echo "Pushing to github"
#git push --all
```

This will abort if there are pending changes in the working directory and also makes sure that all previously existing output files are removed. Adjust the script to taste, e.g. to include the final push to the remote repository if you don't need to take a look at the gh-pages branch before pushing.

## GitHub User Pages

You can host a user/organization page in addition to project pages. Here are the key differences in GitHub Pages websites for Users and Organizations:

1. You must use a `<USERNAME>.github.io` to host your generated content
2. Content from the `master` branch will be used to publish your GitHub Pages site

This is a much simpler setup as your Hugo files and generated content are published into two different repositories.

### Step--by--step Instructions

1. GitHub에 프로젝트 저장소(사이트 소스 저장소)를 만든다.

2. GitHub에 ghpages 저장소 `<USERNAME>.github.io`를 만든다.

3. 리모트 소스 저장소를 로컬로 `clone`한다.

```zsh
git clone <YOUR-PROJECT-URL> && cd <YOUR-PROJECT>`
```

4. 로컬 프로젝트 저장소에 Hugo 프로젝트를 붙여넣는다. 프로젝트 저장소에서 사이트 작동을 검사한다.

```zsh
hugo server
```

5. public 하위폴더에 ghpases 저장소를 `submodule`로 `add한다`.

```zsh
rm -rf public
git submodule add -b master git@github.com:measurable/measurable.github.io.git public
```

이제 `hugo` 명령으로 생성되는 `public` 폴더는 ghpages를 리모트로 가지는 submodule이 된다.
