---
title: "ghpages (2): 페이지 만들기"
date: 2019-10-23T21:57:30+09:00
categories:
    - generic
tags:
    - generic
keywords:
inspired:
motivation: ""
draft: true
---

## quick start

1. Create a repository:
Head over to GitHub and create a new repository named username.github.io, where username is your username (or organization name) on GitHub.

If the first part of the repository doesn’t exactly match your username, it won’t work, so make sure to get it right.


## 사이트 저장소 생성

- If your site is an independent project, you can create a new repository to store your site's source code.
- If your site is associated with an existing project, you can add the source code for your site to a `gh-pages` branch or a `docs` folder on the master branch in that project's repository.

1. Use the `+` drop--down menu in the upper--right corner of any page, and select `New repository`.

2. Use the `Owner` drop--down menu, and select the account you want to own the repository.

3. Type a name for your repository and an optional description.
    - If you're creating a user or organization site, your repository must be named `<user>.github.io`.

4. Choose to make the repository either public or private. Public repositories are visible to the public, while private repositories are only accessible to you, and people you share them with. For more information, see [Setting repository visibility](https://help.github.com/en/github/administering-a-repository/setting-repository-visibility).

5. Select `Initialize this repository with a README`.

6. Click `Create repository`.

## 사이트 생성

1. On GitHub, navigate to your site's repository.

2. 프로젝트 사이트 or 유저 사이트:
    - If you're creating a project site, decide which publishing source you want to use.
    - If you're creating a user or organization site, you must store your site's source code on the `master` branch.

3. If your chosen publishing source already exists, navigate to the publishing source. If your chosen publishing source doesn't exist, create the publishing source.

4. In the root of the publishing source, create a new file called `index.md` that contains the content you want to display on the main page of your site.

5. If you're using a non-default publishing source for a project site, configure your publishing source. For more information, see [Configuring a publishing source for your GitHub Pages site](https://help.github.com/en/github/working-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#choosing-a-publishing-source).

6. Under your repository name, click `Settings`.

7. To see your published site, under `GitHub Pages`, click your site's URL.

**Note**: *It can take up to 20 minutes for changes to your site to publish after you push the changes to GitHub.*

**Note**: *If your site's source files are located in the default publishing source--—`master` for user and organization sites or `gh-pages` for project sites—--but your site has not published automatically, make sure someone with admin permissions and a verified email address has pushed to the default publishing source.*

## Next Steps

You can add more pages to your site by creating more new files. Each file will be available on your site in the same directory structure as your publishing source.
For example, if the publishing source for your project site is the `gh-pages` branch, and you create a new file called `/about/contact-us.md` on the `gh-pages` branch, the file will be available at `https://<user>.github.io/<repository>/about/contact-us.md`.

You can also add a theme to customize your site's look and feel. For more information, see [Adding a theme to your GitHub Pages site with the theme chooser](https://help.github.com/en/github/working-with-github-pages/adding-a-theme-to-your-github-pages-site-with-the-theme-chooser).

---

## Configuring a Publishing Source

People with admin permissions for a repository can configure a publishing source for a GitHub Pages site.[^custom]

[^custom]: If you use the default publishing source for your GitHub Pages site, your site will publish automatically.


## Choosing a publishing source

<em class="emkorean">Before you configure a publishing source, make sure the branch or folder you want to use as your publishing source already exists in your repository. </em>

1. On GitHub, navigate to your site's repository.
2. Under your repository name, click  `Settings`.
3. Under `GitHub Pages`, use the `Source` drop--down menu and select a publishing source.
