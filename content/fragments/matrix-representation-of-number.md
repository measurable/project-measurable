---
title: "Matrix Representation of Number"
date: 2019-10-22T20:21:28+09:00
categories:
    - generic
tags:
    - generic
keywords:
inspired:
motivation: "실수와 복소수의 행렬 표현을 동형사상(이름바꾸기)의 예시로 사용하고, 수보다 행렬이 더 보편적인 객체 아닌가(김민형)를 생각해보자."
draft: true
---

비가환대수가 가환대수보다 더 보편적이라고 말할 수 있을까?
이런 말이 성립하려면 적어도 비가환대수가 자명하지 않은 가환 부분대수를 포함할 수 있는 조건이 정식화될 수 있는가가 문제될 것.

실수의 행렬 표현은 자명한 표현.
\\[
a\sim\begin{pmatrix}
a&0
\newline
0&a
\end{pmatrix}
\\]
그냥, \\(a\sim aI\\)이다.
복소수는 자명하지 않은 표현을 준다.
\\[
a+bi\sim\begin{pmatrix}
a&b
\newline
-b&a
\end{pmatrix}
\\]
두 행렬의 합과 곱을 통해 확인할 수 있다.
\begin{align\*}
(a+bi)+(c+di)&=(a+c)+(b+d)i
\newline
\newline
\begin{pmatrix}
a&b
\newline
-b&a
\end{pmatrix}
+
\begin{pmatrix}
c&d
\newline
-d&c
\end{pmatrix}&=
\begin{pmatrix}
a+c&b+d
\newline
-b-d&a+c
\end{pmatrix}
\end{align\*}
그리고,
\begin{align\*}
(a+bi)(c+di)&=(ac-bd)+(ad+bc)i
\newline
\newline
\begin{pmatrix}
a&b
\newline
-b&a
\end{pmatrix}
\begin{pmatrix}
c&d
\newline
-d&c
\end{pmatrix}&=
\begin{pmatrix}
ac-bd&ad+bc
\newline
-ad-bc&ac-bd
\end{pmatrix}
\end{align\*}

(행렬 표현은 행렬의 원소가 복소수일 경우에도 성립한다. 그게 무슨 의미가 있을지는 모르겠지만...)
이런 식으로---"곱을 통해 확인할 수 있다"는 식으로---설명해 가는 것은 가령, 복소수의 핵심이 무엇인가를 잘 알게 해준다.[^c1] 또, 수학적 개체와 표현의 차이, 결국 수학적 개체란 표현의 isomorphism이라는. 그리고 표현은 관계의 표현이라는 사실을 유도할 수 있는 직접적인 strand를 제공할 거 같다.
이 표현의 isomorphism을 데데킨트 절단이나 코시열로 실수를 컨스트럭션 하는 과정을 설명하는데 써먹어도 될까?

[^c1]: 관계라든지 구조라든지 하는 수학의 추상성이 가지는 위력을 설명하려면 자명하지 않은 단순 구조들을 여러 개 알고 있어야 한다.

## 복소수와 복소수의 표현

복소수는 실수 \\(a\\), \\(b\\)에 대하여 \\(a+bi\\)(단, \\(i^2=-1\\))의 꼴로 나타내어지는 수학적 대상이다.[^c2]
여기서 복소수를 나타내는 그 "꼴"을 복소수라는 수학적 대상의 "표현"이라고 이해하는 것이 좋다. 복소수는 어떤 특정한 뭔가를 나타내는 거지만 그 "표현"은 한 가지만 있는 것이 아니다.

[^c2]: 질문: 이걸 "수"라고 하는 이유는? 또, \\(i^2=-1\\)인 \\(i\\)는 잘 정의되는가? 즉, 존재하고 유일한가? 당연히 유일하지 않다(\\((-i)^2=-1\\)). 이런 식으로 가면 안된다. \\(i\ne j\\)이고 \\(j^2=-1\\)이면 \\(j=-i\\)임을 보이면 된다는 사실을 설명할 수 있으면 된다. 그럴러면 복소수에 관한 공리가 좀 더 정밀해야 한다. 실수가 가지는 특징들을 다 갖도록. 근데 실은 복소수를 정의하려면 순서를 포기해야 한다. 사원수를 정의하려면 교환법칙을 포기해야 한다... 참고: [복소수](https://ko.wikipedia.org/wiki/복소수)와 [사원수](https://ko.wikipedia.org/wiki/사원수).

그렇다면,
\begin{equation}
a+bi
\label{eq:orthorepre}
\end{equation}
또는
\begin{equation}
\begin{pmatrix}
a&b
\newline
-b&a
\end{pmatrix}
\label{eq:matrixrepre}
\end{equation}
로 표현되는 그것, 즉 "복소수"란 무엇일까?
결론부터 말한다면, 두 표현 \eqref{eq:orthorepre}와 \eqref{eq:matrixrepre} 사이의 isomorphism이다.
(합과 곱에 대한 isomorphism이라고 해도 될까? 그보다는 환이나 체로서의 동형이라고 하는 쪽이 좋을 듯.)
