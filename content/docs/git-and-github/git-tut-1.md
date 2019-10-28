---
title: "Git 튜토리얼 (1)"
date: 2019-10-24T20:30:08+09:00
categories:
    - generic
tags:
    - git
keywords:
inspired:
motivation: ""
draft: true
---

# 1. 시작하기

## 버전 관리란?

버전 관리 시스템은 파일의 변화를 시간에 따라 기록하여 과거 특정 시점의 버전을 다시 불러올 수 있는 시스템이다. 소스 코드 뿐만 아니라 모든 컴퓨터 파일이 버전 관리의 대상이 될 수 있다.

VCS를 사용하면 개별 파일 혹은 프로젝트 전체를 이전 상태로 되돌리거나 시간에 따른 변경 사항을 검토할 수 있으며, 문제가 되는 부분을 누가 마지막으로 수정했는지, 누가 언제 이슈를 만들어냈는지 등을 알 수 있다.

### 로컬 버전 관리 시스템

간단한 데이터베이스에 파일의 변경 사항을 기록하는 버전 관리 시스템이다.

![로컬 버전관리 다이어그램](../figures/localvcs.png)

예를 들면, 로컬 VCS인 RCS의 기본적인 동작 방식은 각 리비전들 간의 패치 세트(patch set)라고 하는 데이터의 차이점들을 특별한 형식의 파일에 저장, 특정 시점의 파일 내용을 보고 싶을 때 해당 시점까지의 패치들을 모두 더하여 파일을 만들어내는 것이다.

### 중앙집중식 버전 관리 시스템
중앙집중식 버전 관리 시스템(Centralized Version Control System; CVCS)은 시스템 외부의 개발자들과 함께 작업하는 문제를 위해 개발됐다.
CVS, Subversion, Perforce와 같은 시스템들이 여기에 속한다.
CVCS에서는 버전 관리되는 모든 파일을 저장하는 하나의 서버와, 이 중앙 서버에서 파일들을 가져오는(checkout) 다수의 클라이언트가 존재한다.
오랫동안 사용된 이 방식은 지금까지도 버전 관리의 대표적인 방식이다(그림 1-2 참조).


![중앙집중식 버전 관리 시스템](../figures/cvcs.png)

CVCS는 로컬 VCS에 비해 장점이 많다.
누구나 다른 사람들이 무엇을 하고 있는지 알 수 있고, 관리자는 누가 무엇을 할 수 있는지 꼼꼼하게 관리할 수 있다.
CVCS를 관리하는 것은 수많은 클라이언트의 로컬 데이터베이스를 관리하는 것보다 훨씬 쉽다.

그러나 CVCS는 심각한 단점이 있다.
중앙 서버가 잘못되면 모든 것이 잘못된다는 점이다.
로컬 VCS 시스템도 같은 문제가 있다.
프로젝트의 모든 이력이 한곳에만 있을 경우 이것은 피할 수 없는 문제다.

### 분산 버전 관리 시스템
분산 버전 관리 시스템(Distributed Version Control System; DVCS)은 앞서 말한 문제를 해결하기 위해 개발되었다.
Git, Mecurial, Bazaar, Darcs 등 DVCS에서는 클라이언트가 파일들의 마지막 스냅샷을 가져오는 대신 저장소(repository)를 통째로 복제한다.
따라서 서버에 문제가 생겨도 어느 클라이언트든 복제된 저장소를 다시 서버로 복사하면 서버가 복구된다.
체크아웃(checkout)을 할 때마다 전체 백업이 일어나는 셈이다.

![분산 버전 관리 시스템 다이어그램](../figures/dvcs.png)

게다가 대부분의 DVCS에서는 다수의 원격 저장소(remote repositor:wy)를 갖는 것이 가능하기 때문에 동시에 여러 그룹과 여러 방법으로 함께 작업할 수 있다.
이로 인해 계층 모델(hierarchical model) 등 중앙집중 시스템에서는 할 수 없는 다양한 작업 방식(workflow)들을 사용해볼 수 있다

## 짧게 보는 Git의 역사

리눅스 커널의 일생에서 대부분 시절은 패치와 단순 압축 파일로만 관리했다.
2002년에 리눅스 커널은 BitKeeper라고 불리는 상용 DVCS를 사용하기 시작했다.
2005년에 커뮤니티가 만드는 리눅스 커널과 이익을 추구하는 회사가 개발한 BitKeeper의 관계는 틀어졌다. 이 사건은 리눅스 개발 커뮤니티(특히 리눅스 창시자 리누스 토발즈)가 자체 도구를 만드는 계기가 됐다. Git은 BitKeeper를 사용하면서 배운 교훈을 기초로 아래와 같은 목표를 세웠다:

- 빠른 속도
- 단순한 구조
- 비선형적인 개발(수천 개의 동시 다발적인 브랜치)
- 완벽한 분산
- 리눅스 커널 같은 대형 프로젝트에도 유용할 것(속도나 데이터 크기 면에서)

Git은 2005년 탄생하고 나서 아직도 초기 목표를 그대로 유지하고 있다.
그러면서도 사용하기 쉽게 진화하고 성숙했다.
Git은 미친 듯이 빨라서 대형 프로젝트에 사용하기도 좋다.
Git은 동시다발적인 브랜치에도 끄떡없는 슈퍼 울트라 브랜칭 시스템이다(3장 참고).

## 시작하기 - Git 기초

### 차이가 아니라 스냅샷
CVS, Subversion, Perforce, Bazaar 등의 시스템은 각 파일의 변화를 시간순으로 관리하면서 파일들의 집합을 관리한다.

<figure class="center">
    <img width="98%" alt="" src="../figures/deltas.png">
    <figcaption>
        <span class="pretag">파일이 변화를 저장하는 시스템</span>
    </figcaption>
</figure>

반면, Git은 데이터를 파일 시스템 스냅샷으로 취급하고 크기가 아주 작다.
Git은 커밋하거나 프로젝트의 상태를 저장할 때마다 파일이 존재하는 그 순간을 중요하게 여긴다. 파일이 달라지지 않았으면 Git은 성능을 위해서 파일을 새로 저장하지 않는다. 단지 이전 상태의 파일에 대한 링크만 저장한다. Git은 데이터를 스냅샷의 스트림처럼 취급한다.

<figure class="center">
    <img width="98%" alt="" src="../figures/snapshots.png">
    <figcaption>
        <span class="pretag">스냅샷의 스트림</span>
    </figcaption>
</figure>

### 거의 모든 명령을 로컬에서 실행

### Git의 무결성

Git은 데이터를 저장하기 전에 항상 체크섬을 구하고 그 체크섬으로 데이터를 관리한다.
체크섬은 Git에서 사용하는 가장 기본적인(Atomic) 데이터 단위이자 Git의 기본 철학이다.
Git 없이는 체크섬을 다룰 수 없어서 파일의 상태도 알 수 없고 심지어 데이터를 잃어버릴 수도 없다.
Git은 모든 것을 해시로 식별하기 때문에 이런 값은 여기저기서 보인다. 실제로 Git은 파일을 이름으로 저장하지 않고 해당 파일의 해시로 저장한다.

### Git는 데이터를 추가할 뿐

Git으로 무얼 하든 Git 데이터베이스에 데이터가 추가된다. 되돌리거나 데이터를 삭제할 방법이 없다. 다른 VCS처럼 Git도 커밋하지 않으면 변경사항을 잃어버릴 수 있다. 하지만, 일단 스냅샷을 커밋하고 나면 데이터를 잃어버리기 어렵다.

Git을 사용하면 프로젝트가 심각하게 망가질 걱정 없이 매우 즐겁게 여러 가지 실험을 해 볼 수 있다.

### 세가지 상태

Git은 파일을 `Committed`, `Modified`, `Staged` 이렇게 세 가지 상태로 관리한다.

- `Committed`란 데이터가 로컬 데이터베이스에 안전하게 저장됐다는 것을 의미한다.
- `Modified`는 수정한 파일을 아직 로컬 데이터베이스에 커밋하지 않은 것을 말한다.
- `Staged`란 현재 수정한 파일을 곧 커밋할 것이라고 표시한 상태를 의미한다.

이 세 가지 상태는 Git 프로젝트의 세 가지 단계와 연결돼 있다. Git Directory, Working Diorectory, Staging Area 이렇게 세 가지 단계를 이해하고 넘어가자.

<figure class="center">
    <img width="98%" alt="" src="../figures/areas.png">
    <figcaption>
        <span class="pretag">Working direory, staging area, and Git directory</span>
    </figcaption>
</figure>

- Git Directory는 Git이 프로젝트의 메타데이터와 객체 데이터베이스를 저장하는 곳을 말한다. 이 Git 디렉토리가 Git의 핵심이다. 다른 컴퓨터에 있는 저장소를 Clone 할 때 Git 디렉토리가 만들어진다.

- Working Directory는 프로젝트의 특정 버전을 Checkout 한 것이다. Git 디렉토리는 지금 작업하는 디스크에 있고 그 디렉토리 안에 압축된 데이터베이스에서 파일을 가져와서 워킹 디렉토리를 만든다.

- Staging Area는 Git 디렉토리에 있다. 단순한 파일이고 곧 커밋할 파일에 대한 정보를 저장한다. 종종 Index라고 불리기도 하지만, Staging Area라는 명칭이 표준이 되어가고 있다.

Git으로 하는 일은 기본적으로 아래와 같다.

1. 워킹 디렉토리에서 파일을 수정한다.

2. 파일을 Staging Area로 Stage해서 commit할 스냅샷을 만든다.

3. Staging Area에 있는 파일들을 commit해서 Git 디렉토리에 영구적인 스냅샷으로 저장한다.

Git 디렉토리에 있는 파일들은 Committed 상태이다.
파일을 수정하고 Staging Area에 추가했다면 Staged이다.
Checkout 하고 나서 수정했지만, 아직 Staging Area에 추가하지 않았으면 Modified이다.

## Git 설치 및 최초 설정

### git 설치

OS X에서는 기본 설치되어 있으며, 최신 버전의 설치는 Homebrew를 이용한다.

### 최초 설정

`git config` 툴로 사용 환경을 설정하고 변경, 확인할 수 있다.
설정은 git 설치 후 한번만 해주면 되고, 설정 내용은 git을 업그레이드 해도 유지된다.
`git config --list` 명령을 실행하면 모든 설정 내용을 확인할 수 있다.

```
macmini:~ djlee$ git config --list
user.name=measurable
user.email=djleevina@gmail.com
core.excludesfile=/Users/djlee/.gitignore_global
difftool.sourcetree.cmd=opendiff "$LOCAL" "$REMOTE"
difftool.sourcetree.path=
mergetool.sourcetree.cmd=/Applications/SourceTree.app/Contents/Resources/opendiff-w.sh "$LOCAL" "$REMOTE" -ancestor "$BASE" -merge "$MERGED"
mergetool.sourcetree.trustexitcode=true
filter.lfs.smudge=git-lfs smudge %f
filter.lfs.required=true
filter.lfs.clean=git-lfs clean %f
```

git의 설정 파일은 다음 세가지이다.

`/etc/gitconfig`
:시스템의 모든 사용자와 모든 저장소에 적용되는 설정이다.
`git config --system`  옵션으로 이 파일을 읽고 쓸 수 있다.

`~/.gitconfig`
:현재 사용자에게만 적용되는 설정이다.
`git config --global` 옵션으로 이 파일을 읽고 쓸 수 있다.

`./.git/config`
:이 파일은 git directory에 있고, 현재 저장소에만 적용된다.

각 설정은 역순으로 우선시된다.

#### 사용자 정보

설치 후 가장 먼저 `user.name`과 `user.email`을 지정해 주어야 한다.
git은 commit할 때 마다 이 정보를 사용한다.
일단 commit한 후에는 이 정보를 변경할 수 없다.

```
git config --global user.name "djlee"
git config --global user.email djleevina@gmail.com
```

`--global` 옵션으로 설정한 것은 딱 한번만 하면 된다.
프로젝트마다 다른 이름과 주소를 사용하고 싶으면 `--global` 옵션을 빼면 된다.

#### 에디터

git은 기본적으로 시스템의 기본 편집기를 사용한다. 보통 vi나 vim이다.
다른 편집기를 지정하고 싶으면 다음과 같이 실행한다.

```
git config --global core.editor emacs
```

#### diff tool

diff tool은 merge conflicts를 해결하기 위해 사용한다.

```
git config --global merge.tool vimdiff
```

#### 설정 확인

git은 같은 키를 여러 파일에서 읽기 때문에 같은 키다 하나 이상 나올 수 있다.
`git config \<key\>` 명령으로 키 값을 확인할 수 있다.

```
git config user.name
```

### 도움말 보기
다음 세가지 방법으로 도움말을 볼 수 있다.

```
git help \<verb\>
git \<verb\> --help
man git-\<verb\>
```

# 2. git 기초

## Initialize git repo

### `git init` : 로컬 저장소 생성

기존 디렉토리를 git으로 관리하고 싶을 때,
`git init`로 현재 디렉토리에 git repo로 만든다
`.git` subdir가 만들어진다.
git가 현재 working dir의 특정 파일을 관리하게 하려면 그 파일을 add 해야 한다.

### `git clone` : 원격저장소 복사

다른 프로젝트에 참여(contribute)하거나 git repo를 복사하고 싶을 때,
`git clone`을 사용한다.
이 명령을 실행하면 프로젝트 히스토리를 전부 받아온다.
이 말은 서버의 디스크가 망가져도 클라이언트 저장소 중에서 아무거나 하나 가져다가 복구하면 된다는 의미다.

```
git clone https://github.com/libgit2/libgit2
```

이 명령은 현재 위치에 `libgit2`라는 하위디렉토리를 만들고 그 안에 `.git` 디렉토리를 만든 후 저장소의 모든 데이터를 가져와서 그 최신 버전을 checkout 해놓는다.
다음과 같이 다른 directory 이름으로 clone할 수도 있다.

```
git clone https://github.com/libgit2/libgit2 mylibgit
```

git은 다양한 프로토콜을 지원한다.
`https://` 뿐만 아니라 `git://`나 `user@server:path/to/repo.git` 처럼 SSH 프로토콜을 사용할 수도 있다.

## 변경 사항을 저장소에 기록하기

### 파일 상태 확인

`git status`로 워킹디렉토리의 현재 상태를 확인할 수 있다.

Working dir의 파일은 tracked와 untracked로 나뉘며, commit된 후 Modified된 tracked 파일은 Staged되었거나 그렇지 않은 상태에 있다.


<figure class="center">
    <img width="98%" alt="" src="../figures/lifecycle.png">
    <figcaption>
        <span class="pretag">파일의 라이프사이클</span>
    </figcaption>
</figure>


### 새 파일을 트래킹 / 변경된 파일을 Staging

`git add <filename>`
:파일을 Staging한다.
Untracked 파일의 경우 Tracked됨과 동시에 Staged 상태가 된다.
파일이름 대신 디렉토리명을 주면 해당 디렉토리 안의 모든 파일에 적용된다.

### short status

`git status -s`로 보다 간단한 상태 정보를 볼 수 있다.

### 파일 무시

Working dir에 `.gitignore` 파일을 만들어 git이 ignore할 파일 패턴을 표준 Glob 형식으로 등록해 놓는다.
파일 등록은 다음과 같은 규칙을 따른다.

- 아무것도 없는 라인이나, #로 시작하는 라인은 무시한다.
- 표준 Glob 패턴을 사용한다.
- 슬래시(/)로 시작하면 하위 디렉토리에 적용되지(Recursivity) 않는다.
- 디렉토리는 슬래시(/)를 끝에 사용하는 것으로 표현한다.
- 느낌표(!)로 시작하는 패턴의 파일은 무시하지 않는다.

Glob 패턴은 다음과 같다.

- 애스터리스크(\*)는 문자가 하나도 없거나 하나 이상을 의미하고,
- [abc]는 중괄호 안에 있는 문자 중 하나를 의미한다(그러니까 이 경우에는 a, b, c).
- 물음표(?)는 문자 하나를 말하고,
- [0-9]처럼 중괄호 안의 캐릭터 사이에 하이픈(-)을 사용하면 그 캐릭터 사이에 있는 문자 하나를 말한다.
- 애스터리스크 2개를 사용하여 디렉토리 안의 디렉토리 까지 지정할 수 있다. a/\*\*/z 패턴은 a/z, a/b/z, a/b/c/z 디렉토리에 사용할 수 있다.

아래는 .gitignore 파일의 예이다.

```
# 확장자가 .a인 파일 무시
*.a
# 윗 라인에서 확장자가 .a인 파일은 무시하게 했지만 lib.a는 무시하지 않음
!lib.a
# 현재 디렉토리에 있는 TODO파일은 무시하고 subdir/TODO처럼 하위디렉토리에 있는 파일은 무시하지 않음
/TODO
# build/ 디렉토리에 있는 모든 파일은 무시
build/
# doc/notes.txt 파일은 무시하고 doc/server/arch.txt 파일은 무시하지 않음
doc/*.txt
# doc 디렉토리 아래의 모든 .txt 파일을 무시
doc/**/*.txt
```

GitHub은 다양한 프로젝트에서 자주 사용하는 .gitignore 예제를 관리하고 있다.
https://github.com/github/gitignore 사이트에서 적당한 예제를 찾을 수 있다.

### staged와 unstaged change 조회

`git status`는 파일의 Staging 상태를 보여준다.
`git diff`를 사용하면 Tracking하는 파일의 변경 내용을 patch 형태로 보여준다.

`get diff`
:`git diff --staged`와 같으며, Staged된 것과 Unstaged인 변경 사이에 삭제된 라인과 추가된 라인을 보여준다.
Staging한 후 변경이 없으면 아무것도 출력하지 않는다.

`get diff --cached`
:commited인 것과 Staged된 것 사이의 차이를 보여준다.

### 변경을 commit

`git commit`
:Staged된 변경을 commit한다.
Staged되지 않은 변경은 commit되지 않고 여전히 Modified 상태로 남아 있다.
:이 명령은 commit message를 등록하기 위한 editor를 실행시킨다.
메시지를 인라인으로 첨부하려면 `git commit -m "<commit message>"`와 같이 `-m` 옵션을 사용한다.

`git commit -a `
:`-a` 옵션을 사용하면 commit하기 전에 먼저  모든 Tracked 파일의 Unstaged인 변경을 Staging한다.

다음과 같이 사용한다.

```
git commit -a -m "<commit message>"
```

### 파일 제거

`git rm <filename>`
:파일을 현재 디렉토리에서 삭제하고 Staging Area에서도 제거하여 해당 파일에 대한 tracking을 종료한다.
해당 파일이 `AM` 또는 `MM`이면 `git rm -f`와 같이 강제 옵션을 주어야 한다.

`git rm --cached <filename>`
:파일을 Staging Area에서만 제거하고 working dir에서 삭제하지는 않는다.

Tracked 파일을 쉘 명령으로 `rm`하면 이 파일의 `git status`는 (`modified`라는 변경이 아니라) `deleted`라는 변경이 unstaged인 상태로 된다.
이 파일을 `git add`해주면  `deleted`가 staged되고 더이상 tracking되지 않는다. `deleted`된 파일을 `git add`할 때는 파일이름을 직접 지정해 주어야 하며, `git add *` 명령으로는 `deleted` 변경이 staging되지 않는다.[^deladd]
`git rm`은 이 과정을 한번에 처리한다.

[^deladd]:파일 tracking은 해당 파일을 staging area에 `git add`하는 것으로부터 시작되기 때문에 `deleted`를 staging하는 것은 tracking을 종료하는 것과 같다.
이 점이 `modified`를 staging하는 것과 다르다.
Glob \*는 현재 디렉토리에 존재하는 모든 파일을 찾아서 리턴하는데, 지워진 파일은 현재 디렉토리에 존재하지 않으므로 결과적으로 지워진 파일을 제외한 파일들만 전달된다.
반면, 지워진 파일 이름을 직접 지정하면 현재 디렉토리에 존재하는 파일을 찾지 않고 git이 tracking하고 있는 파일 목록을 찾는 걸로 보인다.

`git rm`에 file-glob 패턴을 사용할 때는 패턴을 escape시켜 패턴 탐색을 shell이 아니라 git에서 하도록 해야 한다.

```
git rm log/\*.log
git rm \*~
```

### 파일 이름 변경

`git mv <filename_from> <filename_to>`
:Woiking dir에 있는 Tracked 파일의 이름을 변경하고 이 변경사항을 Staging한다.

다음 명령을 한번에 수행하는 일종의 단축명령어다.

```
$ mv filename_from filename_to
$ git rm filename_from
$ git add filename_to
```

## 커밋 히스토리 조회

`git log -p -<n> --stat --graph --pretty=...`
:특별한 아규먼트 없이 `git log`하면 저장소의 커밋 히스토리를 FILO 순으로 보여준다.
:`-p` 옵션은 각 commit의 diff 결과를 보여준다.
:`-<n>` 옵션은 최근 <n>개의 커밋 내용만 보여준다.
:`--stat` 옵션은 어떤 파일이 수정됐는지, 몇개의 파일이 수정됐는지, 파일 별로 몇개의 라인이 삭제 또는 추가됐는지를 보여준다.

`git log --pretty=...`
:보여주는 형식을 직접 지정한다.
`oneline`, `short`, `full`, `fuller` 등의 pre-defined 형식이 있다.
`oneline`은 `--graph` 옵션과 함께 사용할 때 매우 유용하다.

`got log --pretty=format: ...` 을 통해 항목을 직접 지정할 수도 있다.
다음은 지정 가능한 포맷 항목들이다.

```
%H      # 커밋 해시
%h      # 짧은 길이 커밋 해시
%T      # 트리 해시
%t      # 짧은 길이 트리 해시
%P      # 부모 해시
%p      # 짧은 길이 부모 해시
%an     # 저자 이름
%ae     # 저자 메일
%ad     # 저자 시각 (형식은 –date= 옵션 참고)
%ar     # 저자 상대적 시각
%cn     # 커미터 이름
%ce     # 커미터 메일
%cd     # 커미터 시각
%cr     # 커미터 상대적 시각
%s      # 요약
```

다음은 `git log`의 주요 옵션들을 정리한 것이다.

```
-p                  # 각 커밋에 적용된 패치를 보여준다.
--stat              # 각 커밋에서 변경된 파일의 통계정보를 보여준다.
--shortstat         # --stat 중에서 변경한 파일, 추가된 라인, 삭제된 라인만.
--name-only         # 변경된 파일의 목록만 보여준다.
--name-status       # 변경된 파일의 목록과 변경 내용(added, modified, delted).
--abbrev-commit     # SHA-1 체크섬의 처음 몇 자만 보여준다.
--relative-date     # “2 weeks ago”처럼 상대적인 형식으로 보여준다.
--graph             # Branch와  Merge 히스토리 정보까지 아스키 그래프로 보여준다.
--pretty            # 지정한 형식으로 보여준다.
```

### log 조회 범위의 제한

`git log --since=...`
`git log --until=...`
`git log --after=...`
`git log --before=...`
:시간 범위로 검색을 제한한다.

`git log --author= ...`
`git log --committer=...`
:authoer/committer의 이름으로 필터링한다.

`git log --grep=...`
:commit msg에서 특정 스트링을 필터링한다.

`git log --S<string>`
:추가하거나 제거한 내용 중에 특정 스트링이 포함되어 있는 것을 필터링한다.

`git log -- path1 path2 ...`
:디렉토리나 파일 이름을 사용해서 그 파일이 변경된 결과만 필터링한다.
옵션의 마지막에 써야 한다.
이 옵션 이후의 것들은 무시된다.

## Undoing Things

`git commit --amend`
:이 커밋으로 직전의 커밋을 덮어쓴다.
직전 커밋 이후에 변경이 없다면 Staging Area가 비어있으므로 커밋 시각 이외에 아무런 변동이 없다.

### Unstaging a Staged File

`git reset HEAD <filename>`
:Staged인 파일을 unstaging한다.
즉, 단순히 파일의 Staging 상태를 staging 이전의 상태로 돌려놓는다.
Staging Area의 내용만 변경하고 working dir의 파일은 건드리지 않는다.

- staged인 변경이 없으면 아무 것도 하지 않는다.
- `MM`이나 `M_`는 `_M`으로 만든다.
- `AM`이나 `A_`는 `??`로 만든다.

For example,

```
$ git status -s
M  RMTEST
M  gitman.md
$ cat RMTEST
test file initialed
modified: test file initiated.
a line appended after staging...
modified after commt...
$ echo 'corrected after staging:modified after commit.' >> RMTEST
$ git status -s
MM RMTEST
M  gitman.md
$ git reset HEAD RMTEST
Unstaged changes after reset:
M   RMTEST
$ git status -s
 M RMTEST
M  gitman.md
$ cat RMTEST
test file initialed
modified: test file initiated.
a line appended after staging...
modified after commt...
corrected after staging:modified after commit.
$
```

While,

```
$ cat RMTEST
test file initialed
modified: test file initiated.
$ git status -s
MM gitman.md
?? RMTEST
$ git add RMTEST
$ git status -s
A  RMTEST
MM gitman.md
$ echo 'a line appended after staging...' >> RMTEST
$ git status -s
AM RMTEST
MM gitman.md
$ git reset HEAD RMTEST
Unstaged changes after reset:
M   gitman.md
$ git status -s
MM gitman.md
?? RMTEST
$ cat RMTEST
test file initialed
modified: test file initiated.
a line appended after staging...
$
```

### Unmodifying a Modified File

`git add <filename>`
`git checkout -- <filename>`
:둘 다 `MM` 상태의 파일을 `M_`상태로 만든다.
`git add`는 working dir의 modification을 staging하고,
`git checkout`은 staged된 내용으로 working dir의 modification을 덮어써서 working dir의 modification을 discard한다.

```
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

    modified:   gitman.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)

    RMTEST

$ cat RMTEST
test file initialed
modified: test file initiated.
$ git add RMTEST
$ echo 'this line added after staging...' >> RMTEST
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

    new file:   RMTEST
    modified:   gitman.md

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

    modified:   RMTEST

$ git checkout -- RMTEST
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

    new file:   RMTEST
    modified:   gitman.md

$ cat RMTEST
test file initialed
modified: test file initiated.$
```

`git checkout -- <filename>` 명령은 staging 이후 수정한 내용을 전부 discarg한다.  변경한 내용을 쉽게 버릴수는 없지만 당장은 되돌려야만 하는 상황이라면 Stash와 Branch를 사용한다.

단, Git으로 커밋한 모든 것은 언제나 복구할 수 있다. 삭제한 브랜치에 있었던 것도, --amend 옵션으로 다시 커밋한 것도 복구할 수 있다.
하지만 커밋하지 않고 잃어버린 것은 절대로 되돌릴 수 없다.

## 원격저장소

### `show` remore repos

`git remote`
`git remote -v`
:로컬에 등록된 리모트를 보여준다.
여기 등록된 리모트가 진짜로 존재하는지의 여부와는 관계 없다.
리모트가 여러개 등록되어 있으면 다른 사람의 contributions를 쉽게 가져올 수 있다.

### `add` remotes

`git remote add <shortname> <url>`
:<url>이 사전이 이미 존재해야 한다.

### `fetch` or `pull` remotes

`git fetch <remotname>`
:로컬에는 아직 없는 리모트 데이터를 모두 가져온다.

예를 들어 리모트 저장소를 `git clone`하면  git은 자동으로 그 리모트를 `origin`이라는 이름으로 추가하고 파일들을 `checkout`해놓는다.
나중에 `git fetch origin`하면 지난번  `git fetch`이후의 변경 사항을 모두 가져온다.
그러나 자동으로 merge하지는 않는다.
로컬에서 하던 작업을 정리하고 나서 수동으로 merge해야 한다.

```
git pull <remotename>
```

은 리모트 저장소의 지정된 브랜치에서 데이터를 가져오면서 동시에 로컬 브랜치와 merge한다.

### `push` remotes

`git push <remotename> <branchname>`
:공유하고자 하는 프로젝트를 upstream repo에 push한다.
리모트에 쓰기 권한이 있어야 한다.
다른 사람이 push한 이후에는 그것을 가져와서 merge한 후에만 push할 수 있다.

### Inspecting a remote

`git remote show <remotename>`
:아래와 같은 정보를 볼 수 있다.

```
$ git remote show gittut
* remote gittut
  Fetch URL: https://github.com/measurable/gittut
  Push  URL: https://github.com/measurable/gittut
  HEAD branch: master
  Remote branch:
    master tracked
  Local branch configured for 'git pull':
    master merges with remote master
  Local ref configured for 'git push':
    master pushes to master (up to date)
```

여러개의 브랜치가 있으면 메시지도 좀 더 복잡해진다.

- 브랜치명을 생략하고 git push 명령을 실행할 때 어떤 브랜치가 어떤 브랜치로 Push 되는지,
- 리모트의 브랜치 중 아직 로컬로 가져오지 않은 것들은 어떤 것이 있는지,
- 서버에서는 삭제됐지만 아직 가지고 있는 브랜치는 어떤 것인지,
- git pull 명령을 실행했을 때 자동으로 Merge 할 브랜치는 어떤 것이 있는지 등.

### `rm` or `mv` remotes

`git remote rename <oldname> <newname>`
`git remote rm <remotename>`
:로컬이 등록된 리모트 이름을 바꾸거나 리모트 저장소를 제거한다.
리모트 저장소 자체에는 아무런 변동이 없다.

## Tagging

`git tag`는 히스토리의 특정 부분을 북마크하는 기능이다.
일반적으로 배포할 때 사용한다.

### Listing Tags

### Ceating Tags

### Annotating Tags

### Lightweight Tags

### Tagging Later

### Sharing Tags

### Checking Out Tags

## git alias

## 요약
