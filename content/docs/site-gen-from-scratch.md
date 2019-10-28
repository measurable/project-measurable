---
title: "사이트 생성  및 포스트 작성"
date: 2019-08-25T22:31:58+09:00
categories:
    - sitedoc
tags:
    - hugo
keywords:
inspired: https://zwbetz.com/make-a-hugo-blog-from-scratch/
motivation:
draft: true
---

hugo로 프로젝트 사이트를 생성하고 hugo 서버를 실행하면 사이트가 빌드된다.

```bash
$ hugo new site site-name
$ cd site-name
$ hugo serve
```

브라우저에 주소 `localhost:1313`을 입력하면 텅 빈 페이지가 표시된다.
이게 새로 만든 사이트의 홈페이지다.

홈페이지에 뭔가를 표시하려면 홈페이지 템플릿이 있어야 한다.
다음 명령으로 홈페이지 템플릿 파일 `layouts/index.html`을 만든다.

```bash
site-name$ echo "Hello, World!" > layouts/index.html
```

이제 브라우저로 주소 `localhost:1313`에 들어가면 "Hello, World!"가 표시된 홈페이지 화면을 볼 수 있다.

포스트를 작성해서 홈페이지 이외의 컨텐트 페이지를 만들기 위해서는 hugo가 사용하는 페이지 템플릿에 관해 좀 더 공부해야 한다.
hugo가 사이트를 빌드하는데 사용하는 파일들은 크게 세 종류로 구분된다.
hugo는 프로젝트 사이트 폴더 아래에 종류 별로 별도의 하위 폴더를 만들어 관련 파일들을 생성, 저장하고 관리한다.

`site-name/content/`
: 페이지 컨텐트를 구성하는 마크다운 파일들

`site-name/layouts/`
: html 페이지를 빌드하기 위한 html 템플릿 파일들

`site-name/static/`
: 각종 static 파일들 (css, js, image 등)

`hugo new <site-name>` 명령으로 hugo 프로젝트를 생성할 때 이 하위 폴더들도 함께 만들어진다.
컨텐트와 템플릿에 대해서는 각각 hugo 문서 [Content Management](https://gohugo.io/content-management/)와 [Templates](https://gohugo.io/templates/) 항목을 참조하라.

## 사이트 생성 및 포스팅

### 1. 사이트 생성

다음 명령은 `site-name`이라는 이름을 갖는 사이트 프로젝트 폴더를 생성한다.

```
$ hugo new site site-name
```

`site-name` 폴더는 프로젝트의 루트 폴더가 되며, 다음과 같은 하위 폴더과 파일들이 만들어져 있다.
이제 홈페이지와 컨텐트 페이지를 만드는 과정을 단계 별로 살펴보자.\

```
site-name           # 프로젝트 루트 폴더
├── archetypes
│   └── default.md
├── config.toml
├── content         # 컨텐트 파일들(.md)을 담아 둘 폴더
├── data
├── layouts         # 페이지 템플릿들(.html)을 담아 둘 폴더
├── static          # static 파일들(.css, .js, etc.)
└── themes
```

설정 파일 `config.toml`과 다른 폴더에 관해서는 필요할 때 별도로 설명한다.
이제 사이트 구축 작업은 프로젝트 루트에 들어가서 진행하게 된다.

```
$ cd site-name
```

초기 상태의 프로젝트 루트에서 서버 `hugo serve -D`를 실행하면 사이트가 빌드된다.
이 사이트는 브라우저에서 주소 `localhost:1313`으로 액세스한다.
초기화 상태에서 사이트는 달랑 홈페이지 하나만 가지며, 그나마 텅 빈 페이지이다.
브라우저에 위 주소를 입력하면 텅 빈 화면을 볼 수 있다.

>이게 존재하지 않는 페이지가 아니라 존재하지만 텅 빈 페이지라는 것은 브라우저 화면에 404 에러가 뜨지 않는 것으로 확인할 수 있다.

### 2. 템플릿 작성

#### 컨텐트와 템플릿

포스트할 컨텐트는 마크다운 형식으로 작성한다.
hugo가 사이트를 빌드할 때는 이 마크다운 파일을 html 페이지 파일로 만든다.
이 때 hugo는 페이지 템플릿을 사용한다.
사이트를 빌드하려면 해당 컨텐트와 매치되는 페이지 템플릿 파일이 있어야 한다.

hugo가 페이지를 빌드할 때 템플릿을 사용한다는 말은,
주어진 컨텐트 파일에 매치되는 페이지 템플릿을 가져와서 여기에 컨텐트 파일에 있는 내용을 삽입한다는 의미다.
구체적으로는 다음과 같다.

- hugo는 `content` 폴더 아래에서 컨텐트 파일 위치하는 경로와 파일 이름을 가지고 컨텐트 파일의 종류를 판단한다. 이를 판단하는 규칙은 "content organization"이라고 한다. 따라서, 컨텐트 파일을 생성힐 때는 `content` 폴더 아래에 규칙에 맞는 경로와 이름을 가지도록 만들어야 한다. 이와 같이 만들어진 컨텐트 파일을 "[컨텍스트(context; 맥락)]()"이라고 부른다.

- hugo는 페이지를 빌드할 때 `layouts`와 그 하위 폴더에서 현재 컨텍스트에 맞는 템플릿 파일을 찾는다. 찾는 방법은 미리 정의된 규칙에 의한다. 이 규칙을 "[lookup order]()"라고 한다. 따리서, 템플릿 파일을 만들 때는 `layouts` 폴더 아래의 정해진 경로에 정해진 이름으로 만들어야 한다.

- 템플릿 파일은 html 파일이다. 이 파일에는 페이지 구성 요소들의 레이아웃을 지정하는 html 코드와, 삽입될 컨텐트의 요소와 삽입될 위치를 지정하는 hugo 템플릿 명령들로 이루어져 있다.

#### 홈페이지 템플릿과 컨텐트 페이지 템플릿

hugo가 사용하는 대표적인 페이지 템플릿은 홈페이지 템플릿과 컨텐트 페이지 템플릿이다.
홈페이지 템플릿이 없을 때, hugo는 비어있는 홈페이지를 만든다.
컨텐트 페이지 템플릿이 없을 때는 컨텐트 페이지를 만들지 않는다.
어느 경우든, 필요한 템플릿이 없으면 hugo는 사이트를 빌드할 때 경고를 발생시킨다.

- hugo 경고: 홈페이지 템플릿 `layouts/index.html`이 없을 때

```
WARN 2019/09/09 14:13:40 found no layout file for "HTML" for "home": You should create a template file which matches Hugo Layouts Lookup Rules for this combination.
```

- hugo 경고: 컨텐트 파일이 있고 `layouts/_default/single.html`이 없을 때

```
WARN 2019/09/09 14:13:40 found no layout file for "HTML" for "page": You should create a template file which matches Hugo Layouts Lookup Rules for this combination.
```

이 이외에도, hugo가 `taxonomyTerm` 또는 `section`을 위한 템플릿이 없다고 경고하는 경우가 있다.

```
WARN 2019/09/10 00:24:27 found no layout file for "HTML" for "taxonomyTerm": You should create a template file which matches Hugo Layouts Lookup Rules for this combination.
```

```
WARN 2019/09/10 00:32:34 found no layout file for "HTML" for "section": You should create a template file which matches Hugo Layouts Lookup Rules for this combination.
```

hugo가 생성하는 페이지는 크게 [list page](https://gohugo.io/templates/lists/)와 [content page]()로 나뉜다.
컨텐트 페이지는 사용자의 컨텐트 파일에 의해 생성되며, 리스트 페이지는 특정한 경우에 hugo가 디폴트로 생성하게 되어 있는 경우가 있다.
위의 두 경고는 모두 그와 같은 리스트 페이지에 해당하는 템플릿이 존재하지 않는다는 컴플레인이다.
리스트 페이지 템플릿이 존재하지 않는 경우에는 해당 페이지가 빈페이지로 생성된다.
리스트 페이지는 이 점에서 컨텐트 페이지와 다르다.
hugo 서버가 실행된 상태에서 다음 주소에 들어가보면 404 에러가 발생하지 않는 빈페이지를 볼 수 있다.

```
localhost:1313/tags
localhost:1313/categories
localhost:1313/posts       #<--- section 템풀릿 경고가 나온 경우
```

리스트 페이지와 달리, 컨텐트 페이지는 템플릿 없이 만들어지지 않는다.

hugo는 `content`에 있는 컨텐트 파일들의 경로를 반영하는 사이트 구조(페이지의 주소 체계)를 만든다. 파일 경로를 사이트 구조로 매핑하는 규칙은 hugo 문서 [Content Organization](https://gohugo.io/content-management/organization/)를 참조하라.
또, 주어진 맥락에 대응하는 템플릿은 `layouts` 폴더에 있는 템플릿 파일들의 경로에 반영되어 있다. 이 대응 규칙은 [Hugo's Lookup Order](https://gohugo.io/templates/lookup-order/)를 참조하라.
따라서, 컨텐트 파일과 마찬가지로 템플릿 파일도 지정된 위치에 지정된 이름의 html 파일로 만들어야 한다.
`layouts/index.html` 파일이 있으면 hugo는 이 파일을 홈페이지 템플릿으로 사용한다.
컨텐트 페이지 템플릿은 `layouts/_default/single.html`이다.[^1]

[^1]: `layouts/_default/` 폴더에 담기는 템플릿은 [`single.html`](https://gohugo.io/templates/single-page-templates/) 외에 [`list.html`](https://gohugo.io/templates/lists/), [`baseof.html`](https://gohugo.io/templates/base/) 등이다. 자세한 것은 해당 항목을 다룰 때 설명한다.

#### 홈페이지 컨텐츠와 템플릿

초기화 상태에서 홈페이지는 빈페이지로 만들어진다.
홈페이지 컨텐츠를 만들고 표시하기 위해서는 홈페이지 컨텐트 파일과 홈페이지 템플릿을 만들어야 한다.
홈페이지 컨텐트 파일은 `content/_index.md`,
홈페이지 템플릿은 `layouts/index.html`로 지정되어 있다.

사이트의 루트에서 다음 명령을 주자.[^2]

[^2]: 컨텐트 파일을 생성할 때 에디터로 직접 만들지 않고 hugo 명령을 사용할 것을 권장한다. [front-matter]() 등 hugo가 이용하는 파일 속성의 체계적 관리를 편리하게 하기 위해서다.

```
site-name$ hugo new _index.md
```

홈페이지 컨텐트 파일 `content/_index.md`이 만들어진다.
에디터로 열어보면 다음 내용이 담겨 있다.

```
---
title: ""
date: 2019-09-09T19:23:17+09:00
motivation:
draft: true
---

```

다음과 같이 홈페이지 `title`과 내용을 추가하고 저장한다.

```
---
title: "hugo로 사이트 만들기"
date: 2019-09-09T19:23:17+09:00
motivation:
draft: true
---

hugo로 사이트 구축하는 과정을 담은 블로그의 홈페이지입니다.
```

이제 홈페이지 템플릿을 만들자.
다음은 간단한 홈페이지 형식이다.[^3]

[^3]: 글의 맨 앞에서 우리는 이미 간단한 홈페이지 템플릿을 만들었다. 그러나 그 때는 홈페이지 컨텐트 파일과 관련 없이 미리 하드 코딩된 글귀를 표시하도록 했었다. 템플릿이라기 보다는 레이아웃과 컨텐츠를 모두 가진 홈페이지 파일이었다.]

```html
<!doctype html>
<html lang="ko">
  <head>
    <title>페이지 타이틀</title>
  </head>
  <body>
    <header>
          <h1>페이지 타이틀</h1>
    </header>
    <div>
      페이지에 표시될 내용(컨텐트)
    </div>
    <footer>
      저작권 표시(예시: (c) measurable, 2019.)
    </footer>
  </body>
</html>
```

페이지 타이틀은 페이지 컨텐트 파일의 front-matter에 `title` 변수로 지정되어 있다.
페이지 컨텐트는 페이지 컨텐트 파일에서 front-matter를 제외한 부분이다.
hugo는 템플릿 파일에서 이 값들을 미리 정해진 변수에 담아 불러오는 제공한다.
현재 작업하는 페이지의 타이틀을 가리키는 변수는 `.Title`이다.
현재 페이지의 컨텐트를 가리키는 변수는 `.Content`이다.
변수 이름을 `{{ }}`로 감싸면 각각의 변수 값을 불러오는 명령이 된다.

이제 홈페이지 템플릿을 다음과 같이 만들자.

`layouts/index.html`

```go-html-template
<!doctype html>
<html lang="ko">
  <head>
    <title>{{ .Title }}</title>
  </head>
  <body>
    <header>
          <h1>{{ .Title }}</h1>
    </header>
    <div>
      {{ .Content }}
    </div>
    <footer>
      저작권 표시(예시: measurable, 2019.)
    </footer>
  </body>
</html>
```

이 템플릿은 컨텐트 파일의 타이틀과 내용을 임의로 변경해도 그대로 사용할 수 있다.
모든 컨텐트 페이지는 페이지 .`Title`과 .`Content`를 가진다.
그래서 이 템플릿은 홈페이지 뿐만 아니라 모든 컨텐트 페이지에 사용해도 된다.
컨텐트 페이지를 위한 hugo의 디폴트 템플릿은 `layouts/_default/single.html`로 지정되어 있다.
hugo가 홈페이지 템플릿을 별도로 두는 이유는, 대부분 사이트가 홈페이지는 보통의 페이지와 다른 레이아웃을 갖기 때문이다.

이제 위의 템플릿을 그대로 복사해서 컨텐트 페이지 템플릿을 만들자.

```
site-name$ mkdir layouts/_default
site-name$ cp layouts/index.html layouts/_default/single.html
```

다른 페이지와 달리, 홈페이지에는 페이지 타이틀 대신 사이트 타이틀이 표시되도록 하자.
템플릿을 바꾼다.

```go-html-template
<!doctype html>
<html lang="ko">
  <head>
    <title>{{ .Site.Title }}</title>
  </head>
  <body>
    <header>
          <h1>{{ .Site.Title }}</h1>
    </header>
    <div>
      {{ .Content }}
    </div>
    <footer>
      저작권 표시, 기타.(예시: (c) measurable, 2019.)
    </footer>
  </body>
</html>
```

`.Site.Title`은 사이트 설정 파일 `config.toml`에 지정되어 있다.
이 파일은 `hugo new site ...`로 프로젝트를 생성할 때 자동으로 만들어져 있다.
에디터로 이 파일을 열어서 `title` 항목을 다음과 같이 수정하자.

```
title = "마이 휴고"
```

이제 `hugo serve -D`를 실행하고 브라우저로  `localhost:1313`을 열어서 표시되는 내용을 확인하자.

### 3. 포스트 작성 및 게시

컨텐트 페이지 템플릿을 만들었으므로,
이제 포스트를 작성하자.

hugo는 컨텐츠를 `section`으로 분류해서 관리한다.
컨텐트 파일은 다음과 같은 형식을 갖는 명령으로 생성한다.

```
hugo new <section-name>/<filename.md>
```

`posts` 섹션에 속한 컨텐트 파일을 하나 만들자.

```
hugo new posts/my-first-post.md
```

다음 명령은 `content` 폴더 아래에 섹션과 같은 이름의 폴더 `posts`를 만들고 그 안에 마크다운 형식의 컨텐트 파일 `my-first-post.md`을 만든다.
에디터로 열어 보면 다음과 같은 front-matter를 가지고 있다.

```
---
title: "My First Post"
date: 2019-08-25T22:31:58+09:00
motivation:
draft: true
---

```

`title`은 컨텐트 파일 이름으로부터 추출해서 자동으로 만들어져 있다.
페이지 타이틀을 임의로 변경하고 포스트 내용을 작성한다.

```
---
title: "드디어 포스트를!"
date: 2019-08-25T22:31:58+09:00
motivation:
draft: true
---

`posts` 섹션에 속한 첫번째 포스트입니다.
```

이제 `hugo serve -D`를 실행하고
브라우저로 주소 `localhost:1313/posts/my-first-post/`의 내용을 확인한다.
