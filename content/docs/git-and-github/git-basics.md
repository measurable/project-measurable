---
title: "git basics"
date: 2019-09-29T01:32:05+09:00
categories:
    - guide
tags:
    - git
keywords:
inspired: https://nanite.tistory.com/39
motivation:
draft: true
---

- `git`을 설치한 후 `git config`를 해준다. 현재 설정은 `git config --list`로 볼 수 있다.

- 로컬 폴더를  `git` 저장소로 만들려면 `git init`한다.
`.gitignore` 파일을 작성해서 `git`의 관리에서 제외할 폴더와 파일을 지정한다.
원격 저장소를 로컬로 가져오는 명령은 `git clone <remote-repo>`이다.

- github 저장소를 동기화할 경우, github에 원격 저장소를 먼저 만들고 로컬에 `git clone`해온다. 이후 workflow는 staging&rarr;commit&rarr;push의 세 단계를 반복하게 된다.
    1. `git add`
    2. `git commit`
    3. `git push`

## 1. 기초 개념

### 용어

working space (작업공간)
: 로컬의 프로젝트 폴더

repository (저장소)
: 작업공간의 스냅샷(commit)들을 git의 자료구조로 저장, 관리하는 `.git` 폴더. `git init`로 로컬 작업공간에 repo를 생성하며, `git clone`으로 remote repo를 클론한 로컬 직업공간을 생성한다.

commit (변경 사항 이력, 스냅샷)
: 특정 시점에 찍은 작업공간의 스냅샷. '커밋한다'는 말은 커밋을 추가한다, 즉 작업공간의 현재 상태를 커밋으로 만들어서 저장소에 저장한다는 의미다. 추가된 커밋은 이전 커밋에 대한 변경만을 저장한다. 그래서 커밋은 서로 연결된 체인 구조를 가진다.

stage (추적)
: 생성 또는 변경된 파일을 다음 커밋에 포함되도록 예약하는 것. 작업 공간의 파일을 stage area에 등록한다. staged된 파일을 스테이지 영역에서 제거하는 것을 unstage (추적해제)라고 한다.

commit hash (커밋해시)
: 각각의 커밋을 구분하는 Extended SHA-1 형식의 식별자. `git log`로 조회한다.

branch (브랜치)
: 기존 커밋열에서 분기된 커밋열.

master/origin
: 기본 브랜치/기본 원격 주소

tag (태그)
: 알아보기 쉽게 하기 위해 커밋(commit)에 달아 주는 이름.

HEAD
: 작업 공간이 현재 위치한 브랜치를 가리키는 포인터.

`.gitignore`
: `.gitignore` 파일은 커밋되어 있어야 작동하기 시작한다. `.gitignore`된 파일들은 `git status` 목록에서 빨간색으로 나타지도 않고 `git add .`에서 제외된다.


### 기본 명령어

`git status`
: 마지막 커밋 이후 작업공간의 변경을 나열. stage된 파일은 초록색으로, 그렇지 않은 파일은 빨간색으로 나타낸다.

`git add <filename>`
: 파일을 stage시킨다. `git add .`하면 변경된 모든 파일을 stage한다.

`git rm <filename>`
: 파일을 unstage한다.

`git commit`
: 커밋 명령. `git commit -m "comment"`의 꼴로 사용된다. 메시지 입력 중 개행은 Shift+Enter로 한다.

`git log`
: 커밋 이력 열람.

`git checkout <commit hash>`
: 이전 커밋을 현재 작업공간에 불러오는 명령어. 커밋 해시는 다른 커밋 해시와 중복되지 않는 한 앞의 몇 자리만 기입해도 된다. `git checkout -- .`은 작업공간에서 발생한 변경을 모두 버리고 직전 커밋으로 되돌아간다.

`git diff`
: 커밋과 커밋 사이의 변경사항 확인.

`git remote`
: 원격과 로컬 저장소를 연결.

`git clone`
: 로컬의 `git init`에 해당. 원격에서 저장소를 최초로 가져올 때 `git pull`이 아니라 `git clone`한다.

`git fetch`
: 업데이트된 원격 저장소를 받아와서 로컬 저장소를 갱신.

`git pull`
: `git fetch`하고 작업공간 그걸로 갱신.

`git push`
: 로컬 저장소를 원격에 push.
