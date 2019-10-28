---
title: "Hugo 메뉴"
date: 2019-09-10T15:30:45+09:00
categories:
    - sitedoc
tags:
    - hugo
keywords:
inspired: https://gohugo.io/content-management/organization/
motivation:
draft: true
---

## 컨텐츠 구조와 페이지 주소

`content`의 하위 폴더 구조는 다음 규칙에 의해 페이지 주소로 매핑된다.
이 주소를 이용해서 페이지에 접근할 수 있다.

```
.
└── content
    └── about
    |   └── index.md        // <- https://example.com/about/
    ├── posts
    |   ├── firstpost.md    // <- https://example.com/posts/firstpost/
    |   ├── happy
    |   |   └── ness.md     // <- https://example.com/posts/happy/ness/
    |   └── secondpost.md   // <- https://example.com/posts/secondpost/
    └── quote
        ├── first.md        // <- https://example.com/quote/first/
        └── second.md       // <- https://example.com/quote/second/
```

### 리스트 페이지의 매핑 예시

##### 섹션 폴더의 소스 파일 경로


```
.         url
.       ⊢--^-⊣
.        path    slug
.       ⊢--^-⊣⊢---^---⊣
.           filepath
.       ⊢------^------⊣
content/posts/_index.md
```

##### 섹션 페이지의 주소 매핑

```
                     url ("/posts/")
                    ⊢-^-⊣
       baseurl      section ("posts")
⊢--------^---------⊣⊢-^-⊣
        permalink
⊢----------^-------------⊣
https://example.com/posts/index.html
```

### 컨텐트 번들의 매핑 예시

##### 컨텐트 번들의 소스 파일 경로

```
                   path ("posts/my-first-hugo-post.md")
.       ⊢-----------^------------⊣
.      section        slug
.       ⊢-^-⊣⊢--------^----------⊣
content/posts/my-first-hugo-post.md
```

또는,

```
                  path ("posts/my-first-hugo-post/index.md")
.       ⊢----------^-----------⊣
.      section      slug
.       ⊢-^-⊣⊢-------^---------⊣
content/posts/my-first-hugo-post/index.md
```

##### 컨텐트 페이지의 주소 매핑

```
                               url ("/posts/my-first-hugo-post/")
                   ⊢------------^----------⊣
       baseurl     section     slug
⊢--------^--------⊣⊢-^--⊣⊢-------^---------⊣
                 permalink
⊢--------------------^---------------------⊣
https://example.com/posts/my-first-hugo-post/index.html
```

