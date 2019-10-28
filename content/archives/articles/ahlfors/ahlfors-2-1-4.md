---
title: "2.1.4. 복소분수함수"
date: 2019-10-25T09:08:32+09:00
categories:
    - 방법
tags:
    - Ahlfors
keywords:
inspired:
motivation: ""
draft: true
---

## 분수함수의 위수(order)

복소분수함수는 기약인 두 복소 다항식의 비
\\[
R(z)=\frac{P(z)}{Q(z)}
\\]
이다.
\\(Q(z)\\)의 영점에서 \\(R(z)=\infty\\)이므로 복소분수함수는 확장평면에서 정의되는 함수라고 볼 수 있다.
\\(Q(z)\\)의 영점을 \\(R(z)\\)의 극pole이라고 하며, 극의 위수는 \\(Q(z)\\)의 영점의 위수와 같다.

도함수
\begin{equation}
R'(z)=\frac{P'(z)Q(z)-Q'(z)P(z)}{[Q(z)]^2}
\label{eq:11}
\end{equation}
는 \\(Q(z)\ne0\\)일 때만 정의된다.
그러나 \\(R'(z)\\)를 식 \eqref{eq:11}의 우변과 같은 방식으로 정의된 분수함수로 보면[^ratderiv] \\(R'(z)\\)는 \\(R(z)\\)와 같은 극을 갖고 그 위수는 각각 \\(1\\)만큼 크다.[^rpord]

[^ratderiv]: 정의식 자체는 기약이 아니므로 분수함수의 정의상 다시 약분해야 한다.

[^rpord]: \\(Q(z)=(z-\alpha\_j)^hQ\_h(z)\\)로부터 \\(Q'(z)=(z-\alpha\_j)^{h-1}\left[hQ\_h+(z-\alpha)Q\_h'(z)\right]\\)를 얻고, 이를 식 \eqref{eq:11}에 대입해서 약분하면 위수 \\(2h-(h-1)=h+1\\)를 얻는다.

정의역과 공역이 모두 확장평면이라고 하면 영점과 극에 관한 좋은 불변성을 얻을 수 있다.
분수함수 \\(R(z)\\)에 대하여 \\(R(1/z)\\)를 \\(R\_1(z)\\)라 하면,
이제
\\[
R(\infty)=R\_1(0)
\\]
라고 정의한다.
또 \\(R\_1(0)=0\\)일 때, 즉 원점이 \\(R\_1(z)\\)의 영점일 때 \\(R(z)\\)는 \\(\infty\\)에서 그와 같은 위수의 영점을 갖는다고 하고,
\\(R\_1(0)=\infty\\)일 때, 즉 원점이 \\(R\_1(z)\\)의 극일 때 \\(R(z)\\)는 \\(\infty\\)에서 그와 같은 위수를 갖는 극을 갖는다고 정의한다.

\\[
R(z)=\frac{a\_0+a\_1z+\cdots+a\_nz^n}{b\_0+b\_1z+\cdots+b\_mz^m}
\\]
라 하면
\\[
R\_1(z)=z^{m-n}\frac{a\_0z^n+a\_1z^{n-1}+\cdots+a\_n}{b\_0z^m+b\_1z^{m-1}+\cdots+b\_m}
\\]
이므로,

- \\(n\gt m\\)일 때, \\(R(z)\\)는 \\(\infty\\)에서 위수 \\(n-m\\)인 극을 갖고,[^nzpolonf1]
- \\(n\lt m\\)일 때, \\(R(z)\\)는 \\(\infty\\)에서 위수 \\(m-n\\)인 영점을 갖는다.[^nzpolonf2]

[^nzpolonf1]: \\(R(z)\\)의 유한한 극이 \\(m\\)개이므로, 이 경우 확장평면에서 \\(R(z)\\)는 모두 \\((n-m)+m=n\\)개의 극을 갖는다.
이는 영점의 수와 같다.
[^nzpolonf2]: \\(R(z)\\)의 유한한 영점이 \\(n\\)개이므로, 이 경우 확장평면에서 \\(R(z)\\)는 모두 \\((m-n)+n=m\\)개의 영점을 갖는다.
이는 극의 수와 같다.

따라서, 확장평면에서 분수함수의 영점의 갯수와 극의 갯수는 항상 같고, 그 값은 분자의 차수와 분모의 차수 중 큰 값이다. 이 값을 분수함수의 차수라고 한다.

\\(a\\)가 상수일 때, \\(R(z)-a\\)의 극은 \\(R(z)\\)의 극과 같으므로 차수도 같다. \\(R(z)-a\\)의 영점은 방정식 \\(R(z)=a\\)의 근이므로 다중근의 갯수를 고려하면 다음 결과를 얻는다:

차수가 \\(p\\)인 분수함수 \\(R(z)\\)는 \\(p\\)개의 영점과 \\(p\\)개의 극을 갖고, 임의의 상수 \\(a\\)에 대해 방정식 \\(R(z)=a\\)는 꼭 \\(p\\)개의 근을 갖는다.

## 분수함수와 일차변환

1차 분수함수
\\[
S(z)=\frac{\alpha z+\beta}{\gamma z+\delta}
,\ \text{ where }\ \alpha\delta-\beta\gamma\ne0
\\]
를 일차변환 이라고 한다.
방정식 \\(w=S(z)\\)는 다음과 같이 꼭 한개의 근을 가진다.
\\[
z=S^{-1}(w)=\frac{\delta w-\beta}{=\gamma w+\alpha}
\\]

일차변환 \\(z-a\\)를 평행이동이라고 하며 \\(1/z\\)를 역inversion이라고 한다.
평행이동은 \\(\infty\\)에서 고정점을 가지며 역은 \\(0\\)과 \\(\infty\\)를 교환한다.

## 부분분수

모든 분수함수는 부분분수 표현을 갖는다.
이 표현을 찾기 위해, 일단 \\(R(z)\\)가 \\(\infty\\)에서 극을 같는다고 하자.
분자를 분모로 나누어 나머지의 차수가 분모의 차수보다 크지 않도록 하고 그 결과를 다음과 같이 나타내자.
\begin{equation}
R(z)=G(z)+H(z)
\label{eq:12}
\end{equation}
이 때 \\(G(z)\\)는 상수항을 갖지 않는 다항식이고,
\\(H(z)\\)는 \\(\infty\\)에서 유한한 값을 갖는다.
\\(G(z)\\)의 차수는 \\(R(z)\\)의 극 \\(\infty\\)의 위수와 같다. 이 \\(G(z)\\)를 \\(\infty\\)에서 \\(R(z)\\)의 특이부분singular part라고 한다.[^quotsgl]

[^quotsgl]: \\(G(z)\\)가 상수항을 갖지 않는 다항식이므로 \\(\infty\\)에서 그 착수와 같은 위수의 극을 갖는다.

\\(R(z)\\)가 가지는 서로 다른 극들을 \\(\beta\_1,\cdots,\beta\_q\\)라고 하자.
함수  \\(R\left(\beta\_j+\frac{1}{\zeta}\right)\\)는 \\(\zeta=\infty\\)에서 극을 가지는 \\(\zeta\\)의 분수함수다.[^zetaord]
\eqref{eq:12}와 같이
\\[
R\left(\beta\_j+\frac{1}{\zeta}\right)=G\_j(\zeta)+H\_j(\zeta)
\\]
로 분해할 수 있고, 변수 변환으로
\\[
R\left(z\right)=G\_j\left(\frac{1}{z-\beta\_j}\right)+H\_j\left(\frac{1}{z-\beta\_j}\right)
\\]
를 얻는다.
\\(\displaystyle G\_j\left(\frac{1}{z-\beta\_j}\right)\\)는 \\(\displaystyle \frac{1}{z-\beta\_j}\\)의 상수항 없는 다항식이고, \\(\beta\_j\\)에서 \\(R(z)\\)의 특이부분이라고 한다.
\\(\displaystyle H\_j\left(\frac{1}{z-\beta\_j}\right)\\)는 \\(z=\beta\_j\\)에서 유한한 값을 갖는다.[^hjbeta]

[^zetaord]: \\(\beta\_j\\)가 \\(R(z)\\)의 극이고 \\(\zeta=\infty\\)에서 \\(\beta\_j+1/\zeta=\beta\_j\\)이기 때문이다. \\(R\left(\beta\_j+\frac{1}{\zeta}\right)\\)의 극 \\(\zeta=\infty\\)의 위수는 \\(R(z)\\)의 극 \\(\infty\\)의 위수 \\(n-m\\)과 \\(\beta\_j\\)의 위수의 합과 같다. 실제로 (잠정적으로 \\(R(z)\\)의 모든 극을 \\(\beta\_1,\cdots,\beta\_m\\)이라 하면),
\\[
R\left(\beta\_j+\frac{1}{\zeta}\right)=\frac{1}{\zeta^{n-m}}\frac{a\_n\prod\_{i=1}^n\left((\beta\_j-\alpha\_i)\zeta+1\right)}{b\_m\prod\_{k=1}^m\left((\beta\_j-\beta\_k)\zeta+1\right)}
\\]
를 약분하면 \\(\beta\_k=\beta\_j\\)인 분모의 인수는 모두 소거된다.
한편, 모든 \\(i,k\\)에 대해서 \\(\alpha\_i\ne\beta\_k\\)이므로
\\(\beta\_j-\alpha\_i\ne\beta\_j-\beta\_k\\)이고, 그래서 분모, 분자의 다른 인수는 소거되지 않는다.

[^hjbeta]: \\(H\_j(\zeta)\\)가 \\(\zeta=\infty\\)에서 finite이다.

이제 다음 식을 생각하자.
\begin{equation}
R(z)-G(z)-\sum\_{j=1}^q G\_j\left(\frac{1}{z-\beta\_j}\right)
\label{eq:13}
\end{equation}
이것은 \\(\beta\_1,\cdots,\beta\_q\\) 및 \\(\infty\\) 이외의 극을 갖지 않는 분수함수다.[^uqpole]
\\(z=\beta\_j\\)에서 무한대가 되는 두 항의 차는 \\(\displaystyle H\_j\left(\frac{1}{z-\beta\_j}\right)\\)이고, 이 사실은 \\(\infty\\)에서도 성립한다.[^betajdiff]
따라서 \eqref{eq:13}은 확장복소평면에서 극을 갖지 않는다.
극을 갖지 않는 분수함수는 상수로 약분된다.
이 상수를 \\(G(z)\\)의 항으로 하면 다음
\\[
R(z)=G(z)+\sum\_{j=1}^q G\_j\left(\frac{1}{z-\beta\_j}\right)
\\]
를 얻는다.[^ptfrac]

[^uqpole]: \\(z\\)가 \\(\beta\_j\\)가 아닌 유한한 값을 가지면 모든 항이 유한이다.

[^betajdiff]: \\(z=\beta\_j\\)일 때 \eqref{eq:13}의 항 중에서 \\(R(z)\\)와 \\(\displaystyle G\_j\left(\frac{1}{z-\beta\_j}\right)\\)만 무한대로 간다. 그런데,
\\[
R\left(z\right)-G\_j\left(\frac{1}{z-\beta\_j}\right)=H\_j\left(\frac{1}{z-\beta\_j}\right)
\\]
이므로 식 \eqref{eq:13}을
\\[\begin{align}
&R(z)-G(z)-\sum\_{j=1}^q G\_j\left(\frac{1}{z-\beta\_j}\right)\newline
=&H\_j\left(\frac{1}{z-\beta\_j}\right)-G(z)-\sum\_{i\ne j}G\_i\left(\frac{1}{z-\beta\_i}\right)
\end{align}\\]
로 나타내면, \\(z=\beta\_j\\)에서 모든 항이 유한이다.
한편, \\(z=\infty\\)에서는 \\(R(z)\\)와 \\(G(z)\\)만 무한대로 가고 \\(R(z)-G(z)=H(z)\\)이므로
식 \eqref{eq:13}을
\\[\begin{align}
&R(z)-G(z)-\sum\_{j=1}^q G\_j\left(\frac{1}{z-\beta\_j}\right)\newline
=&H(z)-\sum\_{j=1}^qG\_j\left(\frac{1}{z-\beta\_j}\right)
\end{align}\\]
로 나타내면 이 경우에도 \\(z=\infty\\)에서 모든 항이 유한이다.

[^ptfrac]: 결과적으로, 분수함수 \\(R(z)\\)를 나누어 나머지가 분모의 차수보다 낮게 만들면 이 나머지는 항상 \\(\displaystyle \sum\_{j=1}^qG\_j\left(\frac{1}{z-\beta\_j}\right)\\)라는 부분분수 표현을 갖는다. 이것은 임의의 분수함수의 적분이 다항식과 로그의 합으로 나타내어진다는 것을 의미한다. 실변수와 달리 적분 결과가 삼각함수로 나타나지 않는다는 것에 주의하자.

이 표현은 미적분학에서 적분 기법으로 흔히 사용되는데, 복소수를 도입하면 모든 분수함수에 대해 항상 가능하게 된다.
