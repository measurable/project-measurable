---
title: "Git 튜토리얼 (2)"
date: 2019-10-24T20:30:20+09:00
categories:
    - generic
tags:
    - git
keywords:
inspired:
motivation: ""
draft: true
---

# 3. Git branching

## 브랜치란?

Git stores a commit object that contains:

- a pointer to the snapshot of the content you staged.
- author’s name and email,
- the message that you typed, and
- pointers to the commit or commits that directly came before this commit (its parent or parents):
    - zero parents for the initial commit,
    - one parent for a normal commit, and
    - multiple parents for a commit that results from a merge of two or more branches.

working dir에 세개의 tracked file이 있다고 가정할 때, 파일을 Stage하면

1. 해당 파일들을 checksome하고
2. 현재 버전을 git repo(blob)에 저장하고
3. 체크섬을 staging area에 추가한다.

커밋하면,

1. root와 subdir을 체크섬해서 그 tree objects를 git repo에 저장하고
2. 메타데이터와 프로젝트 트리에 대한 포인터를 갖는 commit object를 만들어 언제든 필요할 때는 해당 스냅샷을 재구성할 수 있게 한다.

이제 저장소는 다섯개의 ogject를 갖는다.

- three blobs for the contents of each of your three files,
- one tree that lists the contents of the directory and specifies which file names are stored as which blobs, and
- one commit with the pointer to that root tree and all the commit metadata.

<figure class="center">
    <img width="98%" alt="" src="../figures/commit-and-tree.png">
    <figcaption>
        <span class="pretag">커밋과 그 트리</span>
    </figcaption>
</figure>

파일을 변경하고 다시 커밋하면 parents commit에 대한 포인터도 저장한다.

<figure class="center">
    <img width="98%" alt="" src="../figures/commits-and-parents.png">
    <figcaption>
        <span class="pretag">commits and parents</span>
    </figcaption>
</figure>

A branch in Git is simply a lightweight __movable pointer to one of these commits__.
The default branch name in Git is master.
As you start making commits, you’re given a master branch that points to the last commit you made.

<figure class="center">
    <img width="98%" alt="" src="../figures/branch-and-history.png">
    <figcaption>
        <span class="pretag">브랜치와 그 커밋 히스토리</span>
    </figcaption>
</figure>

### 새 브랜치 만들기

`git branch <branchname>`
:직전의 커밋을 가리키는 새 브랜치를 만든다.
HEAD는 이동하지 않는다.
HEAD를 이동시키는 명령은 `git commit`와 `git checkout`이다.

`git log --decorate`로 HEAD와 branch가 어떤 커밋을 가리키는지 확인할 수 있다.

`git checkout <branchname>`
:HEAD를 다른 브랜치로 이동한다.
브랜치를 이동하면 working dir의 파일들이 해당 브랜치의 커밋 내용으로 변경된다.

`git branch testing`
:직전의 커밋을 가리키는 새 브랜치를 만든다. HEAD가 이동하진 않는다.

<figure class="center">
    <img width="98%" alt="" src="../figures/head-to-master.png">
    <figcaption>
        <span class="pretag"></span>
    </figcaption>
</figure>

`git chekout testing`
:헤드를 다른 브랜치로 이동하고 해당 커밋 내용으로 checkout한다.
working dir의 contents가 바뀐다.

<figure class="center">
    <img width="98%" alt="" src="../figures/head-to-testing.png">
    <figcaption>
        <span class="pretag"></span>
    </figcaption>
</figure>

`git commit -a -m 'to advance testing'`
:새로 커밋하면 헤드가 현재 브랜치를 물고 이동한다.

<figure class="center">
    <img width="98%" alt="" src="../figures/advance-testing.png">
    <figcaption>
        <span class="pretag"></span>
    </figcaption>
</figure>

`git chekout master`
:HEAD 이동

<figure class="center">
    <img width="98%" alt="" src="../figures/checkout-master.png">
    <figcaption>
        <span class="pretag"></span>
    </figcaption>
</figure>

`git commit -a -m 'to advance master'`
:헤드가 브랜치를 물고 이동한다. 이제 프로젝트는 갈라져 진행되기 시작한다.

<figure class="center">
    <img width="98%" alt="" src="../figures/advance-master.png">
    <figcaption>
        <span class="pretag"></span>
    </figcaption>
</figure>


Git의 브랜치는 어떤 한 커밋을 가리키는 SHA-1 체크섬 파일에 불과하기 때문에 만들기도 쉽고 지우기도 쉽다.
새로 브랜치를 하나 만드는 것은 41바이트 크기의 파일을(40자와 줄 바꿈 문자) 하나 만드는 것에 불과하다.

그래서 Git은 빠르다. 게다가 커밋을 할 때마다 이전 커밋의 정보를 저장하기 때문에 Merge 할 때 어디서부터(Merge Base) 합쳐야 하는지 안다. 이런 특징 때문에 개발자들이 수시로 브랜치를 만들어 사용하게 된다.

## Branching and Merging

브랜치와 Merge는 보통 이런 식으로 진행한다.

1. 작업 중인 웹사이트가 있다.
2. 새로운 이슈를 처리할 새 Branch를 하나 생성한다.
3. 새로 만든 Branch에서 작업을 진행한다.

이때 중요한 문제가 생겨서 그것을 해결하는 Hotfix를 먼저 만들어야 한다. 그러면 아래와 같이 할 수 있다.

1. 새로운 이슈를 처리하기 이전의 운영(Production) 브랜치로 이동한다.
2. Hotfix 브랜치를 새로 하나 생성한다.
3. 수정한 Hotfix 테스트를 마치고 운영 브랜치로 Merge 한다.
4. 다시 작업하던 브랜치로 옮겨가서 하던 일 진행한다.

### Git Branching

현재 커밋 히스토리가 아래 그림과 같다고 가정한다.

<figure class="center">
    <img width="98%" alt="" src="../figures/basic-branching-1.png">
    <figcaption>
        <span class="pretag">현재 커밋 히스토리</span>
    </figcaption>
</figure>

이슈 관리 시스템에 등록된 특정 이슈를 먼저 처리한다고 하면 이 이슈에 집중할 수 있는 브랜치를 새로 하나 만든다.
브랜치를 만들면서 Checkout까지 한 번에 하려면 `git checkout -b` 옵션을 이용한다.

```
git checkout -b <branchname>
```

위 명령은 아래 명령을 줄여놓은 것이다.

```
git branch iss53
git checkout iss53
```

뭔가 일을 하고 커밋하면 iss53 브랜치가 앞으로 진행한다.

<figure class="center">
    <img width="98%" alt="" src="../figures/basic-branching-3.png">
    <figcaption>
        <span class="pretag">진행중인 iss53 브랜치</span>
    </figcaption>
</figure>

다른 상황을 가정해보자.

만드는 사이트에 문제가 생겨서 즉시 고쳐야 한다.
버그를 해결한 Hotfix에 iss53이 섞이는 것을 방지하기 위해 iss53과 관련된 코드를 어딘가에 저장해두고 원래 운영 환경의 소스로 복구해야 한다.
Git을 사용하면 그냥 master 브랜치로 옮기면 된다.

브랜치를 이동하려면 먼저 해야 할 일이 있다.
브랜치를 변경할 때에는 워킹 디렉토리를 정리하는 것이 좋다.
아직 커밋하지 않은 파일이 Checkout 할 브랜치와 충돌 나면 브랜치를 변경할 수 없다.[^tomvHEAD]
우선 작업하던 것을 모두 커밋하고 master 브랜치로 옮긴다:

[^tomvHEAD]:이런 문제를 다루는 방법은(주로, Stash이나 커밋 Amend에 대해) 나중에 “Stashing과 Cleaning” 에서 다룰 것이다.

```
git checkout master
```

Git는 워킹 디렉토리에 파일들을 추가하고, 지우고, 수정해서 Checkout한 브랜치의 마지막 스냅샷으로 되돌려 놓는다.
워킹 디렉토리가 53번 이슈를 시작하기 이전 모습으로 되돌려지기 때문에 새로운 문제에 집중할 수 있는 환경이 만들어진다.

이제 해결해야 할 핫픽스를 위해 hotfix라는 브랜치를 만들고 새로운 이슈를 해결할 때까지 사용한다.

```
git checkout -b hotfix
vim index.html  # Do Sth to Hotfix
git commit -a -m 'fixed the broken email address'
```

<figure class="center">
    <img width="98%" alt="" src="../figures/basic-branching-4.png">
    <figcaption>
        <span class="pretag">hotfix branch</span>
    </figcaption>
</figure>

운영 환경에 적용하려면 문제를 제대로 고쳤는지 테스트하고 master 브랜치에 merge해야 한다.
어떻게 실행되는지 보자.

```
$ git checkout master
$ git merge hotfix
Updating f42c576..3a0874c
Fast-forward
 index.html | 2 ++
 1 file changed, 2 insertions(+)
```

Merge 메시지에서 "fast-forward"가 보이는가.
Merge할 브랜치가 가리키는 커밋이 현 브랜치 커밋의 upstream branch이기 때문에 master 브랜치 포인터는 최신 커밋으로 이동한다.
이런 Merge 방식을 Fast forward라고 부른다.
즉, A 브랜치에서 다른 B 브랜치를 Merge 할 때 B가 A 이후의 커밋을 가리키고 있으면 그저 A가 B의 커밋을 가리키게 할 뿐이다.

<figure class="center">
    <img width="98%" alt="" src="../figures/basic-branching-5.png">
    <figcaption>
        <span class="pretag">After Merge</span>
    </figcaption>
</figure>

이제 더 이상 필요없는 hotfix 브랜치는 삭제하고
iss53을 처리하던 환경으로 되돌아가서 하던 일을 계속한다.

```
git branch -d hotfix
git checkout iss53
vim index.html
git commit -a -m 'finished the new footer [issue 53]'
```

<figure class="center">
    <img width="98%" alt="" src="../figures/basic-branching-6.png">
    <figcaption>
        <span class="pretag">Return to Last Issue</span>
    </figcaption>
</figure>

일시 작업한 hotfix가 iss53에 영향을 끼치지 않는다는 점을 이해하는 것이 중요하다.
`git merge master` 명령으로 master 브랜치를 iss53 브랜치에 Merge 해야 iss53 브랜치에 hotfix가 적용된다.
아니면 iss53 브랜치가 master에 Merge 할 수 있는 수준이 될 때까지 기다렸다가 Merge할 때 비로소 hotfix와 iss53 브랜치가 합쳐진다.

### Merging

Branch iss53 is ready to be merged into master branch.
Checkout the branch into which you wish merge,
and run the `git merge`[^merged]

[^merged]:(작업 전 상태였던) 붙을 브랜치로 가서 (작업해 놓은) 가져다 붙일 브랜치를 `git merge`로 가져온다.

```
$ git checkout master
Switched to branch 'master'
$ git merge iss53
Merge made by the 'recursive' strategy.
index.html |    1 +
1 file changed, 1 insertion(+)
```

붙을 커밋과 붙일 커밋이 parent-child 관계가 아닐 때, git은 두 브랜치의 common parent commit을 사용해서 3-way merge를 한다.
3-way Merge 의 결과는 별도의 커밋으로 만들어지며, 해당 브랜치가 그 커밋을 가리키도록 이동한다.
이렇게 만들어진 별도의 커밋은 부모가 여러개고 merge commit이라고 부른다.

<figure class="center">
    <img width="98%" alt="" src="../figures/basic-merging-1.png">
    <figcaption>
        <span class="pretag">3-way commit: 3개의 snapshot이 사용된다.</span>
    </figcaption>
</figure>

<figure class="center">
    <img width="98%" alt="" src="../figures/basic-merging-2.png">
    <figcaption>
        <span class="pretag">a merge commit</span>
    </figcaption>
</figure>

Git은 Merge 하는데 필요한 최적의 공통 조상을 자동으로 찾는다.
CVS나 Subversion은 개발자가 직접 공통 조상을 찾아서 Merge 해야 한다.

iss53 브랜치를 master에 Merge 하고 나면 더는 브랜치가 필요 없다.
브랜치를 삭제하고 이슈의 상태를 처리 완료로 표시한다.

```
git branch -d iss53
```

### Merge Conflicts

3-way Merge가 실패할 때가 있다.
충돌이 일어나면 새 커밋이 생기지 않는다.
충돌을 해결한 후 `git add`와 `git commit`을 별도로 거쳐야 한다.

Merge 하는 두 브랜치에서 같은 파일의 동일한 라인을 동시에 수정[^수정]하고 Merge 하면 Git은 해당 부분을 Merge 하지 못한다. 예를 들어, 53번 이슈와 hotfix가 같은 부분을 수정했다면 Git은 Merge 하지 못하고 아래와 같은 충돌(Conflict) 메시지를 출력한다.

```
$ git merge iss53
Auto-merging index.html
CONFLICT (content): Merge conflict in index.html
Automatic merge failed; fix conflicts and then commit the result.
```

[^수정]:수정이 라인의 삭제와 추가(delete line_from, add line_to concept)로 인식된다면, 실제로는 두 브랜치에서 동일한 라인을 삭제하면 충돌이 발생할 듯...
가져온 common parent의 snapshot애 대하여 서로 다른 두 스냅샷이 동시에 동일한 명령을 내리는 것. 동일한 라인에 대해 서로 다른 delete-add pair를 적용하려고 하는 것일 듯...

충돌을 개발자가 해결하지 않는 한 Merge 과정을 진행할 수 없다. Merge 충돌이 일어났을 때 `git status`로 어떤 파일이 문제를 일으키는지 볼 수 있다.

```
$ git status
On branch master
You have unmerged paths.
  (fix conflicts and run "git commit")

Unmerged paths:
  (use "git add <file>..." to mark resolution)

    both modified:      index.html

no changes added to commit (use "git add" and/or "git commit -a")
```

충돌이 일어난 파일은 unmerged 상태로 표시된다. Git은 충돌이 난 부분을 표준 형식에 따라 표시해준다. 그러면 개발자는 해당 부분을 수동으로 해결한다. 충돌 난 부분은 아래와 같이 표시된다.

```
<<<<<<< HEAD:index.html
<div id="footer">contact : email.support@github.com</div>
=======
<div id="footer">
 please contact us at support@github.com
</div>
>>>>>>> iss53:index.html
```

충돌의 해결은 위쪽이나 아래쪽 내용 중에서 고르거나 새로 작성하는 것이다.
그리고 <<<<<<<, =======, >>>>>>>가 포함된 행을 삭제한다.
충돌을 해결하고 `git add`하고 `git commit`한다.

다른 Merge 도구를 이용할 수도 있다.
`git mergetool` 명령으로 실행한다.

## Managing Branches

`git branch`
`git branch -v`
:`git branch`를 옵션 없이 실행하면 브랜치의 목록을 보여준다.
`-v` 옵션은 브랜치마다 마지막 커밋 메시지도 함께 보여준다.

`git branch --merged`
`git branch --no-merged`
:`--merged`와 `--no-merged` 옵션을 사용해서 현재 Checkout 한 브랜치에 merged into 된 브랜치인지, 현재 브랜치에 아직 merged into되지 않은 브랜치인지 필터링해 볼 수 있다.

```
$ git branch --merged
  iss53
* master
```

`*`가 붙어 있지 않은 브랜치는 `git branch -d`로 삭제해도 된다.
이미 다른 브랜치와 Merge 했기 때문에 삭제해도 정보를 잃지 않는다.

`git branch --no-merged`는 현재 Checkout 한 브랜치에 Merged into되지 않은 작업을 담은 브랜치를 보여준다.

```
$ git branch --no-merged
  testing
```

아직 Merge 하지 않은 작업을 담고 있는 브랜치는 `git branch -d`로 삭제되지 않는다.

```
$ git branch -d testing
error: The branch 'testing' is not fully merged.
If you are sure you want to delete it, run 'git branch -D testing'.
```

## Branch Workflow

### Long-Running Branches

Git은 3-way Merge를 사용하기 때문에 한 브랜치를 다른 브랜치와 여러 번 Merge 하는 것이 쉬운 편이다.
그래서 용도에 따라 브랜치를 만들어 두고 계속 사용할 수 있다.

이런 접근법에 따라서 Git 개발자가 많이 선호하는 Workflow가 하나 있다.
배포했거나 배포할 코드만 master 브랜치에 Merge 해서 안정 버전의 코드만 master 브랜치에 둔다.
개발을 진행하고 안정화하는 브랜치는 develop이나 next라는 이름으로 추가로 만들어 사용한다.
이 브랜치는 항상 안정 상태를 유지해야 하는 것이 아니다.
테스트를 거쳐서 안정적이라고 판단되면 master 브랜치에 Merge 한다.
토픽 브랜치(앞서 살펴본 iss53 브랜치 같은 짧은 호흡 브랜치)에도 적용할 수 있는데, 해당 토픽을 처리하고 테스트해서 버그도 없고 안정적이면 그때 Merge 한다.

사실 이것은 선형으로 진행하는 커밋 포인터를 말한다.
개발 브랜치는 공격적으로 히스토리를 만들어 나아가고 안정 브랜치는 이미 만든 히스토리를 뒤따르며 나아간다.

<figure class="center">
    <img width="98%" alt="" src="../figures/lr-branches-1.png">
    <figcaption>
        <span class="pretag">A linear view of progressive-stability branching</span>
    </figcaption>
</figure>

<figure class="center">
    <img width="98%" alt="" src="../figures/lr-branches-2.png">
    <figcaption>
        <span class="pretag">A “silo” view of progressive-stability branching</span>
    </figcaption>
</figure>

안정성 레벨을 여러개로 유지할 수도 있다.
proposed나 pu(proposed update) 브랜치를 별도로 두고 여기에 next나 master 브랜치로 갈 준비가 안돼있는 브랜치들을 모아둔다.[^integrated]

[^integrated]:여기에 merge해둔다는 뜻임?

### Topic Branches

토픽 브랜치는 어떤 한 가지 주제나 작업을 위해 만든 짧은 호흡의 브랜치다.
Git에서는 매우 일상적으로 브랜치를 만들고 Merge 하고 삭제한다.
보통 토픽별로 독립된 브랜치를 만든다.
묶음별로 나눠서 일하면 내용별로 검토하기에도, 테스트하기에도 더 편하다.
각각은 독립돼 있기 때문에 매우 쉽게 컨텍스트 사이를 옮겨 다닐 수 있다.
각각의 작업을 하루든 한 달이든 유지하다가 master 브랜치에 Merge 할 시점이 되면 순서에 관계없이 그때 Merge 하면 된다.

<figure class="center">
    <img width="98%" alt="" src="../figures/topic-branches-1.png">
    <figcaption>
        <span class="pretag">1. 여러개의 토픽브랜치를 유지하다가</span>
    </figcaption>
</figure>

<figure class="center">
    <img width="98%" alt="" src="../figures/topic-branches-2.png">
    <figcaption>
        <span class="pretag">2. master branch에 merge한다.</span>
    </figcaption>
</figure>

## Remote Branches

Remote References는 리모트 저장소에 있는 포인터인 레퍼런스다.
리모트 저장소에 있는 브랜치, 태그, 등등을 의미한다.

`git ls-remote`
`git ls-remote <remotename>`
`git remote show <remotename>`
:리모트의 모든 remote Refs를 조회할 수 있다.

그렇지만 보통은 remote-tracking branches를 사용한다.
이 브랜치는 로컬에 있지만 움직일 수 없다.
리모트 서버에 연결할 때마다 리모트 브랜치에 따라서 자동으로 욺직일 뿐이다.
리모트 트래킹 브랜치는 일종의 북마크라고 할 수 있다.
리모트 저장소가 지난번 연결했을 때 어떤 커밋을 가리키고 있었는지를 나타낸다.

리모트 브랜치의 이름은 `<remotename>/<branchname>`의 형식으로 되어 있다.
리모트 저장소 origin의 master 브랜치를 보고 싶다면 `origin/master`로 브랜치를 확인하면 된다. 다른 팀원과 함께 어떤 이슈를 구현할 때 그 팀원이 iss53 브랜치를 서버로 Push 했고 당신도 로컬에 iss53 브랜치가 있다고 가정하자.
이때 서버의 iss53 브랜치가 가리키는 커밋은 로컬의 origin/iss53이 가리키는 커밋이다.

`git clone`
:`git.ourcompany.com`이라는 Git 서버가 있고 이 서버의 저장소를 하나 Clone 하면 Git은 자동으로 `origin`이라는 이름을 붙인다.
`origin`으로부터 저장소 데이터를 모두 내려받고 `master` 브랜치를 가리키는 포인터를 만든다.
이 포인터는 `origin/master`라고 부르고 멋대로 조종할 수 없다.
그리고 Git은 로컬의 master 브랜치가 `origin/master`를 가리키게 한다.
이제 이 master 브랜치에서 작업을 시작할 수 있다.[^origin]

[^origin]:브랜치 이름으로 `master`가 특별한 의미를 가지는 게 아닌 것처럼 `origin`도 특별한 의미가 있는 것은 아니다.
`git init`이 자동으로 `master`를 만드는 것과 마찬가지로 `git clone`이 자동으로 `origin`이라는 리모트 이름을 만들어준다.
`git clone -o booyah` 라고 옵션을 주고 명령을 실행하면 `booyah/master` 라고 사용자가 정한 대로 리모트 이름을 생성해준다.


<figure class="center">
    <img width="98%" alt="" src="../figures/remote-branches-1.png">
    <figcaption>
        <span class="pretag">Clone 이후 서버와 로컬 저장소</span>
    </figcaption>
</figure>

Merging is NOT Automatic
:로컬 저장소에서 어떤 작업을 하고 있는데 다른 팀원이 `git.ourcompany.com` 서버에 push 하고 `master` 브랜치를 업데이트한다.
그러면 이제 팀원 간의 히스토리는 서로 달라진다.
서버 저장소로부터 어떤 데이터도 주고받지 않아서 `origin/master` 포인터는 그대로다.

<figure class="center">
    <img width="98%" alt="" src="../figures/remote-branches-2.png">
    <figcaption>
        <span class="pretag">로컬과 서버의 커밋 히스토리는 달라질 수 있다.</span>
    </figcaption>
</figure>

`git fetch` <--- syncing, not merging.
:리모트 서버로부터 저장소 정보를 동기화하려면 `git fetch origin` 명령을 사용한다.
명령을 실행하면,

1. 우선 `origin` 서버의 주소 정보(이 예에서는 git.ourcompany.com)를 찾아서,
2. 현재 로컬의 저장소가 갖고 있지 않은 새로운 정보가 있으면 모두 내려받고,
3. 받은 데이터를 로컬 저장소에 업데이트하고 나서,
4. `origin/master` 포인터를 이 최신 위치로이동시킨다.

<figure class="center">
    <img width="98%" alt="" src="../figures/remote-branches-3.png">
    <figcaption>
        <span class="pretag">`git fetch` 명령은 remote references를 업데이트한다.</span>
    </figcaption>
</figure>

`git add`
:리모트 저장소를 여러 개 운영하는 상황을 이해할 수 있도록 팀의 일부가 사용하는 또다른 리모트 Git 저장소가  `git.team1.ourcompany.com`에 있다고 가정하자.
`git remote add` 명령으로 현재 작업 중인 프로젝트에 이 저장소를 추가한다.
이름을 `teamone`으로 짓고 긴 서버 주소 대신 사용한다.

<figure class="center">
    <img width="98%" alt="" src="../figures/remote-branches-4.png">
    <figcaption>
        <span class="pretag">다른 서버를 리모트 저장소로 추가</span>
    </figcaption>
</figure>

`git fetch <added remote>`
:서버를 추가하고 나면 `git fetch teamone` 명령으로 teamone 서버의 데이터를 내려받는다.
명령을 실행해도 그림처럼 teamone 서버의 데이터는 모두 `origin` 서버의 subset이라서 당장은 아무것도 내려받지 않는다.
하지만, 이 명령은 리모트 트래킹 브랜치 `teamone/master`가 teamone 서버의 master 브랜치가 가리키는 커밋을 가리키게 한다.

<figure class="center">
    <img width="98%" alt="" src="../figures/remote-branches-5.png">
    <figcaption>
        <span class="pretag">`teamone/master`의 remote tracking branch</span>
    </figcaption>
</figure>

## Pushing

브랜치를 공유할 때, write access를 가진 리모트에 push한다.
로컬 브랜치는 자동으로 리모트로 전송되지 않는다.
명시적으로 브랜치를 Push 해야 한다. 따라서,

- 리모트 저장소에 전송하지 않고 로컬 브랜치에만 두는 비공개 브랜치를 만들 수 있다.
- 또 다른 사람과 협업하기 위해 토픽 브랜치만 전송할 수도 있다.

serverfix라는 브랜치를 다른 사람과 공유할 때, 브랜치를 처음 Push 하는 것과 같은 방법으로, `git push <remotename_to_update> <branch_to_be_pushed>`를 사용한다.

```
$ git push origin serverfix
Counting objects: 24, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (15/15), done.
Writing objects: 100% (24/24), 1.91 KiB | 0 bytes/s, done.
Total 24 (delta 2), reused 0 (delta 0)
To https://github.com/schacon/simplegit
 * [new branch]      serverfix -> serverfix
```

Git은 `serverfix`라는 브랜치 이름을 `refs/heads/serverfix:refs/heads/serverfix`로 확장한다.
이것은 __`serverfix` 로컬 브랜치 내용을 가져다 리모트의 serverfix 브랜치를 업데이트하라__ 는 의미다.

`git push origin serverfix:serverfix`라고 Push 하는 것도 같은 의미인데 이것은 __로컬의 serverfix 브랜치 내용을를 가져다 리모트의 serverfix 브랜치로 만들어라__ 라는 뜻이다. 로컬 브랜치의 이름과 리모트 서버의 브랜치 이름이 다를 때는 `git push origin serverfix:awesomebranch`처럼 사용한다.
이제 누군가 저장소를 fetch하면 이 서버 버전의 `serverfix`에 대한 레퍼런스를 `origin/serverfix`라는 이름으로 얻게 된다.

```
$ git fetch origin
remote: Counting objects: 7, done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 3 (delta 0)
Unpacking objects: 100% (3/3), done.
From https://github.com/schacon/simplegit
 * [new branch]      serverfix    -> origin/serverfix
```

fetch 명령은 remote-tracking branche를 가져다주는 것이다.
로컬 저장소에 수정할 수 있는 브랜치가 새로 생기는 것이 아니다.
다시 말해서 `serverfix`라는 브랜치가 생기는 것이 아니라 그저 수정 못 하는 `origin/serverfix` 브랜치 포인터가 생기는 것이다.

`git merge origin/serverfix`
:새로 받은 브랜치의 내용을 Merge 한다.

`git checkout -b serverfix origin/serverfix`
:Merge 하지 않고 리모트 트래킹 브랜치에서 시작하는 새 브랜치를 만들고 HEAD를 그리로 옮긴다.

```
$ git checkout -b serverfix origin/serverfix
Branch serverfix set up to track remote branch serverfix from origin.
Switched to a new branch 'serverfix'
```

### Tracking Branches

리모트 트래킹 브랜치를 로컬 브랜치로 Checkout 하면 자동으로 tracking branch가 만들어지며, 이 브랜치가 트래킹하는 브랜치를 upstream branch라고 한다.
트래킹 브랜치는 리모트 브랜치와 직접적인 연결고리가 있는 로컬 브랜치이다.
트래킹 브랜치에서 `git pull`하면 git은 어떤 서버의 어떤 브랜치에서 받아다 merge할 지를 자동으로 안다.

`git clone`
:서버로부터 저장소를 `git clone` 하면 Git은 자동으로 `master`를 `origin/master`의 트래킹 브랜치로 만든다.

다른 방식으로 트래킹 브랜치를 만들 수 있다.
origin이 아닌 다른 리모트로 할 수도 있고, master가 아닌 다른 브랜치로 할 수 있다.

`git checkout -b <branchname> <remotename>/<branchname>`
`git checkout --track <remotename>/<branchname>`
:리모트 브랜치와 다른 이름으로 브랜치를 만들려면 `git checkout -b`에 로컬 브랜치의 이름을 지정한다. `--track` 옵션을 사용하면 로컬 브랜치 이름은 자동으로 생성할 수 있다.

```
$ git checkout -b sf origin/serverfix
Branch sf set up to track remote branch serverfix from origin.
Switched to a new branch 'sf'
```

이제 `sf` 브랜치에서 Push 나 Pull 하면 자동으로 `origin/serverfix`로 데이터를 보내거나 가져온다.

`git branch -u <origin/serverfix>`
`git branch --set-upstream-to <origin/serverfix>`
:이미 로컬에 존재하는 브랜치가 리모트의 특정 브랜치를 추적하게 하려면 `git branch`에 `-u`나 `--set-upstream-to` 옵션을 붙여서 한다.

```
$ git branch -u origin/serverfix
Branch serverfix set up to track remote branch serverfix from origin.
```

upstream shorthand
:추적 브랜치를 설정했다면 추적 브랜치를 `@{upstream}`이나 `@{u}`로 짧게 대체하여 사용할 수 있다. `master` 브랜치가 `origin/master` 브랜치를 추적하는 경우라면 `git merge origin/master` 명령과 `git merge @{u}` 명령을 똑같이 사용할 수 있다.

`git branch -vv`
:추적 브랜치가 현재 어떻게 설정되어 있는지 보여준다.
로컬 브랜치 목록과 로컬 브랜치가 추적하고 있는 리모트 브랜치도 함께 보여준다.
로컬 브랜치가 앞서가는지 뒤쳐지는지에 대한 내용도 보여준다.

```
$ git branch -vv
  iss53     7e424c3 [origin/iss53: ahead 2] forgot the brackets
  master    1ae2a45 [origin/master] deploying index fix
* serverfix f8674d9 [teamone/server-fix-good: ahead 3, behind 1] this should do it
  testing   5ea463a trying something new
```

`ahead 2`는 리모트 브랜치에 없는 커밋이 로컬에 2개 존재한다는 것이고, `behind 1`은 리모트에만 있고 로컬에 없는 커밋이 1개라는 것을 의미한다.`testing` 브랜치는 추적하는 브랜치가 없는 상태이다.

여기서 중요한 점은 위의 명령은 모두 마지막 fetch할 때 로컬에 저장된 캐시 데이터를 사용한다는 점이다. 현재 시점에서 진짜 최신 데이터로 추적 상황을 알아보려면 먼저 서버로부터 최신 데이터를 받아온 후에 추적 상황을 확인해야 한다.

```
git fetch --all; git branch -vv
```

처럼 두 명령을 함께 사용하는 것이 적당하다.

### Pulling

`git pull`
:clone이나 checkout으로 명령을 실행하여 추적 브랜치가 설정되면  명령은 서버로부터 데이터를 가져와서 현재 로컬 브랜치와 서버의 추적 브랜치를 Merge 한다.

`git fetch` 명령을 실행하면 서버에는 존재하지만, 로컬에는 아직 없는 데이터를 받아와서 저장한다.
이 때 워킹 디렉토리의 파일 내용은 변경되지 않고 그대로 남는다.
서버로부터 데이터를 가져와서 저장해두고 사용자가 Merge 하도록 준비만 해둔다.
`git pull` 명령은 대부분 `git fetch`와 `git merge`를 연이어 수행하는 것과 같다.

일반적으로 `fetch`와 `merge` 명령을 명시적으로 사용하는 것이 `pull`하는 것 보다 좋다.

### 리모트 브랜치 삭제

`git push <remotename> --delete <branchname>`
:리모트 서버에서 브랜치를 삭제한다.
이 경우에도 가비지 컬렉터가 작동할 때 까지는 데이터가 남기 때문에 살리기는 쉽다.

```
$ git push origin --delete serverfix
To https://github.com/schacon/simplegit
 - [deleted]         serverfix
```

## Rebase

### Rebase Basic

보통의 3-way merge는 다음 그림과 같이 한다.

<figure class="center">
    <img width="98%" alt="" src="../figures/basic-rebase-1.png">
    <figcaption>
        <span class="pretag">커밋 히스토리가 두개의 브랜치로 나뉘어져 있다.</span>
    </figcaption>
</figure>

<figure class="center">
    <img width="98%" alt="" src="../figures/basic-rebase-2.png">
    <figcaption>
        <span class="pretag">보통의 3-way merge</span>
    </figcaption>
</figure>

이와 달리 C4에서 변경된 사항을 patch로 만들어 이를 C3에 적용시키는 방법으로 비슷한 결과를 얻을 수 있다.
이것을 __rebasing__ 이라고 한다.
`rebase` 명령으로 한 브랜치의 변경을 모두 다른 브랜치에 적용할 수 있다.

```
$ git checkout experiment
$ git rebase master
First, rewinding head to replay your work on top of it...
Applying: added staged command
```

It works by:

1. going to the common ancestor of the two branches (the one you’re on and the one you’re rebasing onto),
2. getting the diff introduced by each commit of the branch you’re on, saving those diffs to temporary files,
3. resetting the current branch to the same commit as the branch you are rebasing onto, and
4. finally applying each change in turn.

<figure class="center">
    <img width="98%" alt="" src="../figures/basic-rebase-3.png">
    <figcaption>
        <span class="pretag"></span>
    </figcaption>
</figure>

5. At this point, you can go back to the `master` and do a fast-forward merge.

```
$ git checkout master
$ git merge experiment
```

<figure class="center">
    <img width="98%" alt="" src="../figures/basic-rebase-4.png">
    <figcaption>
        <span class="pretag"></span>
    </figcaption>
</figure>

### More Interesting Rebase



<figure class="center">
    <img width="98%" alt="" src="../figures/interesting-rebase-1.png">
    <figcaption>
        <span class="pretag"></span>
    </figcaption>
</figure>

<figure class="center">
    <img width="98%" alt="" src="../figures/interesting-rebase-2.png">
    <figcaption>
        <span class="pretag"></span>
    </figcaption>
</figure>

<figure class="center">
    <img width="98%" alt="" src="../figures/interesting-rebase-3.png">
    <figcaption>
        <span class="pretag"></span>
    </figcaption>
</figure>

<figure class="center">
    <img width="98%" alt="" src="../figures/interesting-rebase-4.png">
    <figcaption>
        <span class="pretag"></span>
    </figcaption>
</figure>

<figure class="center">
    <img width="98%" alt="" src="../figures/interesting-rebase-5.png">
    <figcaption>
        <span class="pretag"></span>
    </figcaption>
</figure>

### Perils of Rebasing

<figure class="center">
    <img width="98%" alt="" src="../figures/perils-of-rebasing-1.png">
    <figcaption>
        <span class="pretag"></span>
    </figcaption>
</figure>

<figure class="center">
    <img width="98%" alt="" src="../figures/perils-of-rebasing-2.png">
    <figcaption>
        <span class="pretag"></span>
    </figcaption>
</figure>

<figure class="center">
    <img width="98%" alt="" src="../figures/perils-of-rebasing-3.png">
    <figcaption>
        <span class="pretag"></span>
    </figcaption>
</figure>

<figure class="center">
    <img width="98%" alt="" src="../figures/perils-of-rebasing-4.png">
    <figcaption>
        <span class="pretag"></span>
    </figcaption>
</figure>

### Rebase When You Rebase

<figure class="center">
    <img width="98%" alt="" src="../figures/perils-of-rebasing-5.png">
    <figcaption>
        <span class="pretag"></span>
    </figcaption>
</figure>

### Rebase vs. Merge


# 4. Git Server

# 5. 분산환경에서의 git

# 6. GitHub

별도의 topic branch로 관리함:
_gitman-ch6-github.md_

# 남은 내용들

# Git commands
