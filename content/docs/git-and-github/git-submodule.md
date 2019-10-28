---
title: "git submodule"
date: 2019-09-29T19:06:22+09:00
categories:
    - guide
tags:
    - git
keywords:
inspired:
motivation:
draft: true
---

프로젝트 아래에 독립적으로 버전 관리되는 하위 프로젝트를 사용하고 싶을 때가 있다.
사이트 개발 프로젝트에서 별도로 관리되는 외부 테마 프로젝트를 가져다 사용하려고 하는 경우를 예로 들 수 있다.
submodule은 이를 위해 git이 제공하는 기능이다.

생성된 submodule의 작업공간과 repo는 마스터 프로젝트의 하위 폴더로 위치한다.
마스터 프로젝트 내에는 섭모듈의 루트 폴더 경로와 원격 저장소의 주소를 담은 `.gitmodules` 피일이 생성된다.
섭모듈의 루트 경로는 마스터 repo의 루트에서 시작하는 상대 경로이다.
마스터 프로젝트 내에서 `git submodule` 명령어들을 이용해서 이 파일을 관리한다.

## submodule의 생성 및 업데이트

다음 명령을 주면 섭모듈 루트가 생성되고, 마스터에서 커밋하면 등록된 섭모듈이 마스터에서 tracking된다.

```
master$ git submodule add <remote url> <submodule root path>
```

이렇게 생성된 sub repo는 비어있다. submodule을 가진 remote repo를 clone해 오는 경우에도 sub repo는 비어있다. 이것은 master/sub repo사이의 독립성을 반영힌다.
sub repo를 가져오려면 마스터에서 다음 명령을 주면 된다.

```
master$ git submodule init
master$ git submodule update
```

