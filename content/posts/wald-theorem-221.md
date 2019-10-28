---
title: "Wald Theorem 221"
date: 2019-09-22T01:37:15+09:00
categories:
    - 방법
tags:
    - gr
    - wald
keywords:
inspired:
motivation:
draft: true
---


\\(M\\)이 다양체이고
\\(\mathscr F\\)가 \\(M\\)에서
\\(\mathbf R\\)로 가는 \\(C^\infty\\) 함수의 모임이라 하자.
\\(p\in M\\)에서의 접벡터 \\(v\\)를, 사상 \\(v:\mathscr F\to\mathbf R\\)로서 모든 \\(f,g\in\mathscr F\\)와 \\(a,b\in\mathbf R\\)에 대하여 다음 성질을 만족하는 것이라고 정의한다.

\begin{align\*}
&v(af+bg)=av(f)+bv(g),
\newline
&v(fg)=f(p)v(g)+v(f)g(p).
\end{align\*}

이 정의는 "미소 변위infinitesimal displacement"의 개념에 관해 precise하고 intrinsic한 의미를 준다.
이 때, 점 \\(p\\)에서의 모든 접벡터의 모임을 \\(V\_p\\)라 하면,
\begin{align\*}
(v\_1+v\_2)(f)\in V\_p,&\quad\text{ where }\quad(v\_1+v\_2)(f)=v\_1(f)+v\_2(f),
\newline
(av)(f)\in V\_p,&\quad\text{ where }\quad(av)(f)=av(f)
\end{align\*}
임은 쉽게 보일 수 있다.
그래서 \\(V\_p\\)는 벡터공간이다.

\\(V\_p\\)는 다음과 같은 중요한 성질을 가진다:

<div class="theorem">
\(M\)이 \(n\)차원 다양체이고 \(V_p\)가 \(p\in M\)의 접공간이라고 하면,
\(\dim V_p=n\)이다.
</div>

\\(V\_p\\)에 일차독립인 \\(n\\)개의 접벡터가 존재하고, 이것이 \\(V\_p\\)를 span함을 보일 것이다.

차트
\\[
\psi:O\to U,\quad\text{where }\ p\in O\subset M,\ U\subset\mathbf R^n
\\]
를 생각하자.

만약 \\(f\in\mathscr F\\)이면 정의에 의해 \\(f\circ\psi^{-1}:U\to\mathbf R\\)은 \\(C^{\infty}\\)이다.
이제 \\((x^1,\cdots,x^n)\\)가 \\(\mathbf R^n\\)의 직교좌표라 하고, \\(\mu=1,\cdots,n\\)에 대하여 \\(X\_\mu:\mathscr F\to\mathbf R\\)을 다음과 같이 정의한다.
\\[
X\_\mu(f)=\left.\frac{\partial}{\partial x^\mu}\left(f\circ\psi^{-1}\right)\right\vert\_{\psi(p)}
\\]
\\(X\_1,\cdots,X\_n\\)가 서로 일차독립인 접벡터들이라는 사실은 쉽게 보일 수 있다.

이제 이 벡터들이 \\(V\_p\\)를 span한다는 것을 보이기 위해 다음 사실을 이용한다.

만약 \\(F:\mathbf R^n\to\mathbf R\\)이 \\(C^\infty\\)이면 임의의 \\(a=\left(a^1,\cdots,c^n\right)\\)에 대하여 다음 관계를 만족하는 \\(C^\infty\\) 함수 \\(H\_\mu\\)가 존재한다.
\\[
F(x)=F(a)+\sum\_{\mu=1}^n\left(x^\mu-a^\mu\right)H\_\mu(x)
\\]
또,
\begin{equation}
\left.
H\_\mu(a)=\frac{\partial F}{\partial x^\mu}\right\vert\_{x=a}
\label{eq:2.2.3}
\end{equation}
이다.
\\(F=f\circ\psi^{-1}\\), \\(a=\psi(p)\\)라 놓으면, 위의 사실로부터 임의의 \\(q\in O\\)에 대하여 다음 결과를 얻는다.
\begin{equation}
f(q)=f(p)+\sum\_{\mu=1}^n\left[x^\mu\circ\psi(q)-x^\mu\circ\psi(p)\right]H\_\mu\left(\psi(q)\right).
\label{eq:2.2.4}
\end{equation}

이제 임의의 \\(v\in V\_p\\)가 \\(X\_1,\cdots,X\_n\\)의 일차결합임을 보인다.
위의 \\(f\\)에 \\(v\\)를 적용하고 식 \eqref{eq:2.2.4}와 \\(v\\)의 선형성 및 라이프니츠 성질, 그리고 상수에 \\(v\\)를 적용하면 \\(0\\)이 된다는 사실을 이용하면 다음 결과를 얻는다:

\begin{align\*}
v\left(f\right)&=v\left(f(p)\right)+\sum\_{\mu=1}^n\left\\{
\left[x^\mu\circ\psi(q)-x^\mu\circ\psi(p)\right]\Big\vert\_{q=p}v\left(H\_\mu\circ\psi\right)
\right.
\newline
&\phantom{=}\left.+\left(H\_\mu\circ\psi\right)\Big\vert\_pv\left(x^\mu\circ\psi-x^\mu\circ\psi(p)\right)\right\\}
\newline
&=\sum\_{\mu=1}^n\left(H\_\mu\circ\psi(p)\right)v\left(x^\mu\circ\psi\right).
\end{align\*}

식 \eqref{eq:2.2.3}에 의해 \\(H\_\mu\circ\psi(p)\\)는 \\(X\_\mu(f)\\)와 같으므로, 모든 \\(f\in\mathscr F\\)에 대하여
\\[
v\left(f\right)=\sum\_{\mu=1}^nv^\mu X\_\mu\left(f\right),
\quad\text{ where }\ v^\mu=v\left(x^\mu\circ\psi\right)
\\]
이다.
그래서 임의의 접벡터 \\(v\\)는 다음과 같이 \\(X\_\mu\\)의 합으로 나타낼 수 있다.
\\[
v=\sum\_{\mu=1}^nv^\mu X\_\mu
\\]
