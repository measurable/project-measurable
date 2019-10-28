---
title: "Ahlfors 2 2 4"
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


# 2.2.4 멱급수

멱급수의 일반적인 꼴은 다음과 같다.
\\[
\sum_{n=0}^\infty a_n(z-z_0)^n
\\]
이를 \\(z_0\\)을 중심으로 하는 멱급수라고 한다. 모든 멱급수는 수렴원을 가진다. 수렴원 안에서 멱급수는 수렴하고 그 바깥에서는 발산한다.
수렴원 위에서의 수렴 여부는 일반적으로 말할 수 없다.
이하, 원점을 중심으로 하는 멱급수를 다룬다.

>(정리 2).
임의의 멱급수
\\[
a_0+a_1z+a_2z^2+\cdots+a_nz^n+\cdots
\tag{17}\\]
에 대하여, 다음 성질을 만족하는 수렴반경 \\(R\\) (단, \\(0\le R\le\infty\\))가 존재한다:
>
1. \\(|z|<R\\)인 임의의 \\(z\\)에 대하여 절대수렴한다. 만약 \\(0\le\rho<R\\)이면 \\(|z|\le\rho\\)에서 균등수렴한다.[^rhoR]
2. \\(|z|>R\\)이면 발산한다.
3. \\(|z|<R\\)에서 급수의 합은 해석함수이다. 그 도함수는 항별 미분으로 얻을 수 있으며, 원시 급수와 같은 수렴반경을 갖는다.

위의 결과로부터 해석함수가 멱급수 표현을 가지면 \\(C^\infty\\)급 함수이고 그 표현은 유일하다는 사실을 얻는다.

[^rhoR]: 수렴원 안에서 점별로 절대수렴하고, 수렴원 안의 동심원판 위에서는 균등수렴한다는 의미다.

## Hadamard's Formular

수렴원의 반경 \\(R\\)이 다음 공식
\\[
\frac{1}{R}=\lim_{n\to\infty}\sup|a_n|^{\frac{1}{n}}
\\]
으로 주어질 때, 위의 정리가 참임을 보일 수 있다.
이것을 Hadamard 공식이라고 한다.

먼저 수렴원 안에서 점별수렴을 보인다.
주어진 임의의 \\(|z|<R\\)에 대해 \\(|z|<\rho<R\\)인 \\(\rho\\)가 존재한다.
이 때 \\(1/R<1/\rho\\) 즉
\\[
\lim_{n\to\infty}\sup|a_n|^{\frac{1}{n}}<\frac{1}{\rho}
\\]
이므로 limes superior의 정의에 의해 다음 조건
\\[
|a_n|^{\frac{1}{n}}<\frac{1}{\rho}\quad\text{ or }\quad|a_n|<\left(\frac{1}{\rho}\right)^n,\ \forall n\ge n_0
\\]
을 만족하는 \\(n_0\\)가 존재한다.
이로부터, 충분히 큰 \\(n\\)에 대해
\\[
|a_nz^n|<\left(\frac{|z|}{\rho}\right)^n
\\]
가 성립한다는 결과를 얻는다. 즉, 위 \\((17)\\)의 멱급수는 수렴하는 기하급수[^abzprrho]를 majorant로 갖는다. 그래서 \\((17)\\)은 수렴한다.\\(\Box\\)

[^abzprrho]: 주어진 \\(z\\)에 대하여 \\(|z|/\rho<1\\)이므로 수렴하는 기하급수지만 \\(\rho\\)가 \\(z\\)에 의존하므로 이로 부터 균등수렴을 보일 수는 없다.

이제 주어진 \\(\rho<R\\)에 대하여 \\(|z|\le\rho\\)에서 균등수렴한다는 것을 보이자.
\\(\rho<\rho'<R\\)을 만족하는 상수 \\(\rho'\\)과 \\(n_0\\)가 존재해서
\\[
|a_nz^n|\le\left(\frac{\rho}{\rho'}\right)^n,\ \forall n\ge n_0
\\]
을 만족한다.
이제 멱급수 \\((17)\\)은 수렴하는 상수열의 급수를 majorant로 가지므로 균등수렴한다.\\(\Box\\)

수렴원 밖에서 발산한다는 것을 보이려면
\\(|z|>R\\)에 대하여 \\(R<\rho<|z|\\)인  \\(\rho\\)를 잡는다.
이 때 \\(1/R>1/\rho\\) 즉
\\[
\lim_{n\to\infty}\sup|a_n|>\left(\frac{1}{\rho}\right)^n
\\]
이므로 충분히 큰 \\(n\\)에 대하여
\\[
|a_nz^n|>\left(\frac{|z|}{\rho}\right)^n
\\]
이 성립한다.
즉, 멱급수의 항은 유계가 아니다.\\(\Box\\)

도함수의 급수 \\(\displaystyle \sum_1^\infty na_nz^{n-1}\\)은 원래의 급수와 같은 수렴반경을 갖는다:

우선, \\(n^{1/n}\to1\\)이다. (증명): \\(n^{1/n}=1+\delta_n\\)이라고 놓으면 \\(\delta_n>0\\)이고, 이항정리에 의해
\\[
n=(1+\delta_n)^n>1+\frac{1}{2}n(n-1)\delta_n^2
\\]
을 얻는다.
따라서 \\(\delta_n^2<2/n\\)이고, 그래서 \\(\delta_n\to0\\)이다.
이제 \\(\displaystyle \sum_1^\infty na_nz^{n-1}\\)의 수렴반경을 \\(R'\\)이라 하면 Hadamard 공식에서
\\[
\frac{1}{R'}=\lim_{n\to\infty}\sup|na_n|^\frac{1}{n}
=\lim_{n\to\infty}\sup n^\frac{1}{n}|a_n|^\frac{1}{n}=\frac{1}{R}
\\]
을 얻는다.\\(\Box\\)

이제 수렴원 안에서 멱급수가 해석함수이고 그 도함수는 항별 미분에 의해 얻어진다는 것을 증명하자.
\\(|z|<R\\)에서 멱급수 \\((17)\\)을 다음과 같이 나타내자.
\\[
f(z)=\sum_0^\infty a_nz^n=s(z)+R_n(z)
\\]
단,
\\[\begin{align}
s_n(z)&=a_0+a_1z+\cdots+a_{n-1}z^{n-1},\newline
R_n(z)&=\sum_{k=n}^\infty a_kz^k
\end{align}\\]
또,
\\[
f_1(z)=\sum_1^\infty na_nz^{n-1}=\lim_{n\to\infty}s_n'(z)
\\]
라 하자.
이제 \\(f'(z)=f_1(z)\\)임을 증명하면 된다.
\\(z\ne z_0\\)이고 \\(|z|,|z_0|<\rho<R\\)일 때 다음 항등식을 생각하자.
\\[\begin{align}
&\frac{f(z)-f(z_0)}{z-z_0}-f_1(z_0)\newline
=&\left[\frac{s_n(z)-s_n(z_0)}{z-z_0}-s_n'(z_0)\right]+\left[s_n'(z_0)-f_1(z_0)\right]+\left[\frac{R_n(z)-R_n(z_0)}{z-z_0}\right]
\tag{19}\end{align}\\]
\\(\epsilon\\)를 주어진 임의의 양수라고 하자.
우변의 첫째항의 \\(s_n(z)\\)는 해석함수이므로 도함수의 정의에 의해 \\(\delta>0\\)가 존재해서
\\[
|z-z_0|<\delta\implies\left|\frac{s_n(z)-s_n(z_0)}{z-z_0}-s_n'(z_0)\right|<\frac{\epsilon}{3}
\\]
을 만족한다.
둘째항의 경우,
\\[
\left|s_n'(z_0)-f_1(z_0)\right|=\sum_{k=n}^\infty k\left|a_kz^{k-1}\right|
\\]
이고, 이 급수는 수렴하므로[^deriabs],
\\[
\left|s_n'(z_0)-f_1(z_0)\right|<\frac{\epsilon}{3},\ \forall n\ge n_1
\\]
를 만족하는 \\(n_1\\)가 존재한다.
마지막으로, 세째항은 다음과 같이 쓸 수 있다.
\\[
\frac{R_n(z)-R_n(z_0)}{z-z_0}=\sum_{k=n}^\infty\left(a_k\sum_{j=1}^{k}z^{k-j}z_0^{j-1}\right)
\\]
\\(|z|,|z_0|<\rho\\)이므로 \\(\displaystyle\sum_{j=1}^{k}z^{k-j}z_0^{j-1}<k\rho^{k-1}\\)이고, 그래서 다음 결과를 얻는다.
\\[
\left|\frac{R_n(z)-R_n(z_0)}{z-z_0}\right|\le\sum_{k=n}^\infty k|a_k|\rho^{k-1}
\\]
이 부등식의 우변이 수렴하므로,
\\[
\left|\frac{R_n(z)-R_n(z_0)}{z-z_0}\right|<\frac{\epsilon}{3},\ \forall n\ge n_2
\\]
을 만족하는 \\(n_2\\)이 존재한다.
부등식 \\((19)\\)에 관한 이상의 결과를 종합해서 다음 결과를 얻는다.
임의의 \\(\epsilon>0\\)에 대하여 다음 조건을 만족하는 \\(\delta>0\\)이 존재한다.
\\[
|z-z_0|<\delta\implies\left|\frac{f(z)-f(z_0)}{z-z_0}-f_1(z_0)\right|<\epsilon,\ n\ge\forall n_0
\\]
그래서 \\(f'(z_0)\\)가 존재하고 그 값은 \\(f_1(z_0)\\)와 같다.\\(\Box\\)

이상의 논의는 도함수에 대해서도 적용되므로 무한히 반복될 수 있다:
양의 수렴반경을 갖는 멱급수는 모든 차수의 도함수를 갖는다.
그 도함수는 다음과 같이 명시적인 공식을 갖는다.
\\[\begin{align}
f(z)&=a_0+a_1z+a_2z^2+\cdots\newline
f'(z)&=1a_1+2a_2z+3a_3z^2+\cdots\newline
f''(z)&=2\cdot1a_2+3\cdot2a_3z+4\cdot3a_4z^2+\cdots\newline
\cdots\newline
f^{(k)}(z)&=k!a_k+\frac{(k+1)!}{1!}a_{k+1}z+\frac{(k+2)!}{2!}a_{k+2}z^2+\cdots\newline
\end{align}\\]

이 때, \\(a_k=\frac{f^{(k)}(0)}{k!}\\)이므로 주어진 멱급수는 다음과 같이 나타내어진다.
\\[
f(z)=f(0)+f'(0)z+\frac{f''(0)}{2!}z^2+\cdots+\frac{f^{(n)}(0)}{n!}z^n+\cdots
\\]
이렇게 해서 Taylor-Macclaurin 전개를 얻는다.
즉, \\(f(z)\\)가 멱급수 표현을 가지면 그 전개는 위의 공식에 의해 유일하게 결정된다.
그러나 모든 해석함수가 테일러 전개를 갖는다는 사실\\({}\\)은 아직 증명되지 않았다.

[^deriabs]: 수렴반경 안에 있으므로 절대수렴한다.
