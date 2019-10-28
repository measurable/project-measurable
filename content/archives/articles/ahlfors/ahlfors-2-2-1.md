---
title: "2.2. 멱급수의 기초 이론"
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

## 2.2.1 수열 sequence

코시열은 수렴하고, 오직 코시열만 수렴한다.
코시열의 실수부와 허수부는 각각 코시열이다.
수열의 실수부와 허수부가 각각 수렴하면 원래의 수열도 수렴한다.

아래에서는 코시 기준을 전제로 급수의 수렴을 다룬다.

- 코시열의 contraction도 코시열이라는 것을 이용해서 절대수렴하는 급수가 수렴함을 보인다.
- 함수열의 균등수렴이 가지는 중요한 성질, 즉 균등수렴하는 연속함수열의 극한이 연속함수임을 보인다.
- 균등수렴의 중요한 판정기준으로, 수렴하는 상수열의 contraction인 함수열은 균등수렴한다는 사실이다. 코시조건의 직접적 결과이다.
- 급수의 majority--minority 개념을 정의하고, majorant가 수렴하면 minorant는 균등수렴한다는 사실을 보인다. 이것을 Weierstrass M test라고 하며, 절대수렴하는 급수에 적용할 수 있다.

## 2.2.2 급수 series

코시 조건을 이용하면 한 수열의 수렴으로부터 다른 수열의 수렴을 유도할 수 있다.
\\(|b\_m-b\_n|\le|a\_m-a\_n|,\ \forall m,n\\)일 때 수열 \\(\{b\_n\}\\)을 수열 \\(\{a\_n\}\\)의 contraction\\({}\\)이라고 한다.
\\(\{b\_n\}\\)이 \\(\{a\_n\}\\)의 contraction이고 \\(\{a\_n\}\\)이 코시열이면 \\(\{b\_n\}\\)도 코시열이다.
무한급수
\begin{equation}
a\_1+a\_2+\cdots+a\_n+\cdots
\label{15}
\end{equation}
의 부분합
\\[
s\_n=a\_1+a\_2+\cdots+a\_n
\\]
의 열 \\(\{s\_n\}\\)이 수렴할 때, 또 오직 그 때만 급수가 수렴한다. 이 경우 \\(\{s\_n\}\\)의 극한을 급수의 합이라고 한다.

코시 기준을 이용해서 급수가 수렴하기 위한 조건을 얻을 수 있다:
임의의 \\(\epsilon>0\\)에 대하여 어떤 양의 정수 \\(n\_0\\)가 존재해서 다음 조건
\\[
|a\_{n}+a\_{n+1}+\cdots+a\_{n+p}|< \epsilon,
\ \forall n\ge n\_0,\forall p\ge0
\\]
만족하는 것이다.[^cchserc] 이 때 \\(p=0\\)이면 \\(|a\_n|< \epsilon\\)을 얻는다.
수렴하는 급수의 일반항이 0으로 수렴한다는 의미다. 그러나 이 사실은 급수가 수렴하기 위한 필요조건이며 충분조건은 아니다:[^sqsrcv]

[^cchserc]: \\(|a\_{n}+a\_{n+1}+\cdots+a\_{n+p}|=s\_{n+p}-s\_{n-1}\\)이므로 주어진 조건은 \\(\{s\_n\}\\)이 코시열임을 의미한다.

[^sqsrcv]: 증명에서, 임의의 \\(p\ge0\\)에 대해 성립하는 것은 필요충분조건이지만, 주어진 명제는 \\(p=0\\)에서 성립하면 되므로 충분성을 만족하지 않는다.

다음 절대값 급수를 생각하자.
\begin{equation}
|a\_1|+|a\_2|+\cdots+|a\_n|+\cdots
\label{16}
\end{equation}
\eqref{15}의 부분합들의 수열은 \eqref{16}의 부분합 수열의 contraction이므로 \eqref{16}이 수렴하면 \eqref{15}도 수렴한다.[^sercont] 급수의 각 항의 절대값으로 이루어진 급수가 수렴하면 그 급수는 절대수렴한다고 말한다.
(즉, 급수가 절대수렴하면 원래의 급수도 수렴한다.)

[^sercont]: \\(s\_n=a\_1+\cdots+a\_n\\), \\(\sigma\_n=|a\_1|+\cdots+|a\_n|\\)이고 \\(m>n\\)이라 하면,
\\[\begin{align}
&|s\_m-s\_n|=|a\_{n+1}+\cdots+a\_m|,\newline
&|\sigma\_m-\sigma\_n|=|a\_{n+1}|+\cdots+|a\_m|
\end{align}\\]
이므로
\\[
|s\_m-s\_n|\le|\sigma\_m-\sigma\_n|
\\]
이다. 코시 기준에 의해 \\(\{\sigma\_n\}\\)이 수렴하면 \\(\{s\_n\}\\)도 수렴한다.
그래서 절대수렴하는 급수는 수렴한다.

## 2.2.3 균등수렴uniform convergence

집합 \\(E\\)에서 정의된 함수열 \\(\{f\_n(x)\}\\)를 생각하자.

주어진 임의의 \\(x\in E\\)에 대하여 \\(\{f\_n(x)\}\\)이 수렴할 때, 극한 \\(f(x)\\)도 \\(E\\) 위의 함수다.
이 경우, 점별 수렴과 균등수렴을 구별해야 한다.

함수열 \\(f\_n(x)=\left(1+1/n\right)x\\)를 생각하자.
\\[
\lim\_{n\to\infty}f\_n(x)=x,\ \forall x
\\]
이다. 그런데 주어진 \\(\epsilon>0\\)에 대하여
\\[
\left|\left(1+\frac{1}{n}\right)x-x\right|< \epsilon,\ n\ge n\_0
\\]
을 만족하려면
\\[
n\_0>\frac{|x|}{\epsilon}
\\]
이어야 한다.
즉, 주어진 임의의 \\(x\\)에 대하여 \\(n\_0\\)는 항상 존재하지만, 모든 \\(x\\)에 대한 수렴 조건을 동시에 만족시키는 \\(n\_0\\)는 존재하지 않는다.
이와 같은 경우, 함수열 \\(\{f\_n(x)\}\\)는 \\(f(x)\\)에 점별수렴하고 균등수렴하지는 않는다.

<em class="strongkorean">정의 (균등수렴)</em>
<em class="emkorean">
임의의 \\(\epsilon>0\\)마다 \\(n\_0\\)가 존재해서 모든 \\(n\ge n\_0\\)과 모든 \\(x\in E\\)에 대하여 \\(|f\_n(x)-f(x)|< \epsilon\\)을 만족할 때, \\(\{f\_n(x)\}\\)은 \\(E\\) 위에서 \\(f(x)\\)에 균등수렴한다고 말한다.

</em>

다음 사실은 균등수렴의 가장 중요한 결과다:

<em class="strongkorean">정리 (연속함수열의 극한)</em>
<em class="emkorean">
균등수렴하는 연속함수열의 극한은 연속함수이다.
</em>

<em class="emkorean">(증명)</em>
\\(\{f\_n(x)\}\\)이 \\(E\\) 위에서 \\(f(x)\\)로 균등수렴하는 연속함수열이라고 하면,
임의의 \\(\epsilon>0\\)에 대하여
\\[
\left|f\_n(x)-f(x)\right|< \frac{\epsilon}{3},\ \forall x\in E
\\]
를 만족하는 \\(n\\)이 존재한다.
이 \\(f\_n(x)\\)는 임의의 \\(x\_0\in E\\)에서 연속이므로 다음 조건을 만족하는 \\(\delta>0\\)이 존재한다.
\\[
\left|x-x\_0\right|< \delta\implies\left|f\_n(x)-f\_n(x\_0)\right|< \frac{\epsilon}{3}
,\ x\in E
\\]
이 \\(x\\)에 대하여 다음 결과를 얻는다.
\\[
\left|f(x)-f(x\_0)\right|\le
\left|f(x)-f\_n(x)\right|+\left|f\_n(x)-f\_n(x\_0)\right|+\left|f\_n(x\_0)-f(x\_0)\right|
< \epsilon
\\]
그래서 \\(f(x)\\)는 \\(x\_0\\)에서 연속이다. (증명끝)

해석함수에 관한 이론에서는 점별수렴보다 균등수렴이 훨씬 더 중요하다. 단, 대부분의 함수는 정의역의 일부분에서만 균등수렴한다.
코시 조건에 대응하는 균등수렴의 필요충분조건은 다음과 같다:


<em class="strongkorean">정리 (균등수렴의 필요충분조건)</em>
<em class="emkorean">
임의의 \\(\epsilon>0\\)마다 \\(n\_0\\)가 존재해서 모든 \\(n\ge n\_0\\)과 모든 \\(x\in E\\)에 대하여 \\(|f\_m(x)-f\_n(x)|< \epsilon\\)을 만족한다.
</em>

<em class="emkorean">(증명)</em>
위의 조건이 만족되면 코시조건에 의해 극한 \\(f(x)\\)가 존재한다.
이제 조건의 부등식 \\(|f\_m(x)-f\_n(x)|< \epsilon\\)에서 \\(m\to\infty\\)라 하면 \\(|f(x)-f\_n(x)|\le\epsilon\\)를 얻는다.
그래서 위 조건은 균등수렴의 충분조건이다. 필요조건임은 균등수렴의 정의에 의해 자명하다. (증명끝)

실제 테스트를 위해서는 다음 방법이 더 실용적이다:

<em class="strongkorean">정리 </em>
<em class="emkorean">
함수열 \\(\{f\_n(x)\}\\)이 수렴하는 상수열 \\(\{a\_n\}\\)의 contraction이면 \\(\{f\_n(x)\}\\)은 균등수렴한다.
</em>

즉, \\(E\\) 위에서 \\(|f\_m(x)-f\_n(x)|\le|a\_m-a\_n|\\)이면 균등수렴한다는 의미다. 코시 조건에서 도출할 수 있는 결과다.

### 바이어슈트라스 \\(M\\) 검정Weierstrass M Test

급수의 경우에는 더 약한 형태이긴 하지만 아주 간단한 기준을 준다.
가변항으로 이루어진 급수
\\[
f\_1(x)+f\_2(x)+\cdots+f\_n(x)+
\\]
에 대하여 양항급수
\\[
a\_1+a\_2+\cdots+a\_n+
\\]
가 존재해서,
\\(n\\)이 충분히 클 때 어떤 상수 \\(M\\)에 대하여 \\(|f\_n(x)|\le Ma\_n\\), \\(\forall x\\)를 만족하면 이 양항급수를 그 가변급수의 majorant라고 하고, 가변급수는 이 양항급수의 minorant라고 한다.
이 때,
\\[
\left|f\_n(x)+f\_{n+1}(x)+\cdots+f\_{n+p}(x)\right|\le M\left(a\_n+a\_{n+1}+\cdots+a\_{n+p}\right)
\\]
이므로 majorant가 수렴하면 minorant는 균등수렴한다.[^majmino]
이 조건을 바이어슈트라스 M 검정이라고 한다. 이 검정은 절대수렴하는 급수에만 적용된다는 점에서 좀 더 약한 방법이다.

[^majmino]: 테스트 부등식은 minorant의 부분열이 majorant 부분열의 contraction임을 의미한다. 그래서 수열의 균등수렴 조건을 부분열에 적용하여 급수인 majorant가 수렴하면 급수인 minorant도 균등 수렴한다는 결과를 얻는다. 테스트 부등식 자체는 모든 급수에 적용되지만 우변의 \\(M\\)과 급수가 majorant-minorant 관계에서 유도되므로 우변의 급수가 수렴하면 좌변의 급수는 절대수렴한다.
\\(\{f\_n(x)\}\\)의 부분합의 열을  \\(\{s\_n\}\\), \\(\{|f\_n(x)|\}\\)의 부분합의 열을  \\(\{\sigma\_n\}\\)이라 하고, \\(\{a\_n\}\\)의 부분합의 열을 \\(\{A\_n\}\\)이라 하자.
majorant-minorant 관계 \\(|f\_n(x)|\le Ma\_n\\)으로부터
\\[
\left|f\_n(x)\right|+\left|f\_{n+1}(x)\right|+\cdots+\left|f\_{n+p}(x)\right|
\le M\left(a\_n+a\_{n+1}+\cdots+a\_{n+p}\right)
\\]
이고,
\\[
\left|f\_n(x)+f\_{n+1}(x)+\cdots+f\_{n+p}(x)\right|
\le \left|f\_n(x)\right|+\left|f\_{n+1}(x)\right|+\cdots+\left|f\_{n+p}(x)\right|\\]
이므로 이로부터 검정 부등식
\\[
\left|f\_n(x)+f\_{n+1}(x)+\cdots+f\_{n+p}(x)\right|\le M\left(a\_n+a\_{n+1}+\cdots+a\_{n+p}\right)
\\]
을 얻는다.
