---
title: "My Approach to Math (mathjax example)"
date: 2019-09-19T22:22:14+09:00
categories:
    - 방법
tags:
    - math
keywords:
    - 서술방식
inspired:
motivation:
draft: true
---

\\[
\cos^2\theta+\sin^2\theta=1
\tag{피타고라스 정리}\label{eq:pyth}
\\]

\\[
e^{i\pi}+1=0
\tag{오일러 공식}\label{eq:euler}
\\]
\\[
\int\_{\Omega}d\omega=\int\_{\partial\Omega}\omega
\tag{일반화된 스토크스 정리}\label{eq:gstokes}
\\]

\\[
\partial\_{\sigma}\partial^{\sigma}A^\mu
-\partial^\mu\partial\_\nu A^\nu
=\beta J^\nu
\tag{맥스웰 방정식}\label{eq:maxwel}\\]

\\[
\left[-\frac{\hbar^2}{2m}\laplacian+V\right]\Psi=i\hbar\frac\partial{\partial t}\Psi
\tag{슈뢰딩어 방정식}\label{eq:schr}
\\]

\\[
R\_{\mu\nu}-\frac12Rg\_{\mu\nu}+\Lambda g\_{\mu\nu}
=\frac{8\pi G}{c^4} T\_{\mu\nu}
\tag{아인슈타인 장방정식}\label{eq:eins}
\\]

세 양수 \\(a\\), \\(b\\), \\(c\\)가 \\(a^2+b^2=c^2\\)를 만족시킬 때,
위의 \eqref{eq:pyth}를 만족시키고 \\(0\le\theta\le\pi/2\\)인 실수 \\(\theta\\)가 존재한다.
역으로 \eqref{eq:pyth}가 성립할 때, 임의의 실수 \\(c\\)에 대하여
\\(a^2=c^2\cos^2\theta\\), \\(b^2=c^2\cos^2\theta\\)라 놓으면
\\(a^2+b^2=c^2\\)을 얻는다.

\eqref{eq:euler}은 복소 지수의 다음 정의로부터 자명하다.
\begin{equation}
e^{i\theta}=\cos\theta+i\sin\theta
\label{eq:compower}
\end{equation}
<a href="https://en.wikipedia.org/wiki/Taylor%27s_theorem" target="_blank">테일러 정리</a>에서 다음 함수들의 급수 전개를 얻는다.
\begin{align}
e^x&=\sum\_{k=0}^\infty\frac{x^k}{k!}\notag
\newline
&=1+x+\frac{x^2}{2!}+\frac{x^3}{3!}+\frac{x^4}{4!}+\cdots
\label{eq:eseri}
\newline
\cos(x)&=\sum\_{k=0}^\infty\frac{(-1)^kx^{2k}}{(2k)!}\notag
\newline
&=1-\frac{x^2}{2!}+\frac{x^4}{4!}-\frac{x^6}{6!}+\cdots
\label{eq:coseri}
\newline
\sin(x)&=\sum\_{k=0}^\infty\frac{(-1)^kx^{2k+1}}{(2k+1)!}\notag
\newline
&=x-\frac{x^3}{3!}+\frac{x^5}{5!}-\frac{x^7}{7!}+\cdots
\label{eq:siseri}
\end{align}
\\(x=i\theta\\)일 때, \\(\eqref{eq:eseri}=\eqref{eq:coseri}+i\cdot\eqref{eq:siseri}\\)이므로 식 \eqref{eq:compower}을 얻는다.

\eqref{eq:gstokes}는 다음 미적분학의 기본정리를 가장 일반화된 형식으로 표현한 것이다.
\begin{equation}
\int\_a^bf(x)dx=F(b)-F(a)
\tag{미적분학의 기본정리}\label{eq:fundacal}
\end{equation}
<a href="https://en.wikipedia.org/wiki/Stokes%27_theorem" target="_blank">스토크스 정리</a>는 3차원 벡터장에서 다음과 같이 표현된다.
\\[
\oint\_\Gamma\vb F\cdot d\Gamma=\iint\_S\curl{\vb F}\cdot d\vb S
\tag{스토크스의 정리}\label{eq:stokes}
\\]
<a href="https://en.wikipedia.org/wiki/Green%27s_theorem" target="_blank">그린의 정리</a>와
<a href="https://en.wikipedia.org/wiki/Divergence_theorem" target="_blank">가우스의 발산 정리</a>는 모두
<a href="https://en.wikipedia.org/wiki/Stokes%27_theorem" target="_blank">스토크스 정리</a>의 특수한 경우이다.
\\[
\oint\_C(Ldx+Mdy)=\iint\_D\left(\frac{\partial M}{\partial x}-\frac{\partial L}{\partial y}\right)dxdy
\tag{그린의 정리}\label{eq:thgreen}
\\]
\\[
\iiint\_V\divergence{\vb F}dV=\oint\_S\vb F\cdot\vb ndS
\tag{발산정리}\label{eq:발산정리}
\\]

## 맥스웰 방정식: 전자기장의 수학적 기술

전자기장을 기술하는
<a href="https://en.wikipedia.org/wiki/Mathematical_descriptions_of_the_electromagnetic_field" target="_blank">맥스웰 방정식의 수학적 기술</a>은 여러 가지가 있다.
전형적인 표현은 벡터장에서의 기술이다.
\begin{align}
\begin{split}
\divergence{\vb E}&=\frac{\rho}{\varepsilon\_0},\quad
&\curl{\vb E}&=-\frac{\partial\vb B}{\partial t}
\newline
\divergence{\vb B}&=0,
&\curl{\vb B}&=\mu\_0\left(\vb J+\varepsilon\_0\frac{\partial \vb E}{\partial t}\right)
\end{split}
\label{eq:maxwell}
\end{align}

### 전자기파의 발견

\\(\rho\\)와 \\(\vb J\\)가 없는 진공에서 패러데이의 유도법칙과 앙페르 법칙의 curl을 취하여 컬의 컬에 관한 다음 항등식
\\[
\curl{(\curl{\vb A})}=\grad(\divergence{\vb A})-\laplacian\vb A
\\]
을 이용하면 다음과 같은
<a href="https://en.wikipedia.org/wiki/Wave_equation" target="_blank">파동방정식</a>을 얻는다.

\begin{align\*}
\begin{split}
\mu\_0\varepsilon\_0
\frac{\partial^2\vb E}{\partial t^2}-\laplacian\vb E=0
\newline
\mu\_0\varepsilon\_0
\frac{\partial^2\vb B}{\partial t^2}-\laplacian\vb B=0
\end{split}
\tag{전자기파}\label{eq:emw}
\end{align\*}

\\(\mu\_0\\), \\(\varepsilon\_0\\)는 실험적으로 결정되는 값으로.
그 곱은 (시간/거리)<sup>2</sup>의 차원을 가지므로,
\\((\mu\_0\varepsilon\_0)^{-1/ 2}\\)가 위 \eqref{eq:emw}의 속도이다. 이 값은 당시 이미 알려져 있던 빛의 속도(약 \\(3\times10^8\,\mathrm{m/sec^2}\\))과 일치했다.

### 적분 표현

위의 미분방정식은 다음과 같이 적분 형식으로 나타낼 수 있다.

\\[
\oint\_{\partial\Omega}\vb E\cdot d\vb S
=\frac1{\varepsilon_0}\iiint\_\Omega\rho dV
\tag{가우스 법칙}
\\]
\\[
\oint\_{\partial\Omega}\vb B\cdot d\vb S=0
\tag{가우스의 자기법칙}
\\]
\\[
\oint\_{\partial\Sigma}\vb E\cdot d\vi l
=-\frac{d}{dt}\iint\_\Sigma\vb B\cdot d\vb S
\tag{패러데이 법칙}
\\]
\\[
\oint\_{\partial\Sigma}\vb B\cdot d\vi l
=\mu\_0\left(
\iint\_\Sigma\vb J\cdot d\vb S
+\varepsilon\_0\frac{d}{dt}\iint\_\Sigma\vb E\cdot d\vb S
\right)
\tag{앙페르 법칙}
\\]

### 퍼텐셜 표현(potential formulation)

스칼라장 \\(\varphi\\)와 벡터장 \\(\vb A\\)에 대하여,

\begin{align\*}
\vb E&=-\grad\varphi-\frac{\partial \vb A}{\partial t}
\newline
\vb B&=\curl{\vb A}
\end{align\*}

라 하자.
이 \\(\varphi\\)와 \\(\vb A\\)를 각각 전기퍼텐셜, 자기퍼텐셜이라고 한다.
이 관계를 시스템 \eqref{eq:maxwell}에 넣어서 다음과 같이 퍼텐셜로 나타내어지는 맥스웰 방정식을 얻는다.

\begin{equation}
\begin{split}
&\ \ \ \laplacian\varphi+\frac\partial{\partial t}(\divergence{\vb A})=-\frac\rho{\varepsilon\_0}
\newline
&\left(\laplacian\vb A-\frac1{c^2}\frac{\partial^2\vb A}{\partial t^2}\right)-\grad\left(\divergence{\vb A}+\frac1{c^2}\frac{\partial \varphi}{\partial t}\right)
=-\mu\_0\vb J
\end{split}
\label{eq:potemax}
\end{equation}


### 게이지 불변

전자기 퍼텐셜은 물리적 의미를 갖지 않는다.
오직 전기장과 자기장 만이 측정 가능한 물리량이다.
그러므로 방정식이 동일한 전기장과 자기장을 준다면 퍼텐셜 함수는 어떤 것을 선택해도 된다.
만약 \\(\varphi\\)와 \\(\vb A\\)가 위 시스템 \eqref{eq:potemax}의 해이면
임의의 스칼라 함수 \\(\lambda\\)에 대하여 다음 조건을 만족시키는 \\(\varphi'\\)과 \\(\vb A'\\)도 해가 된다.
이러한 성질을 맥스웰 방정식의 게이지 불변성이라고 한다.

\begin{align}
\varphi'&=\varphi-\frac{\partial\lambda}{\partial t}
\newline
\vb A'&=\vb A+\grad\lambda
\end{align}
이와 같은 게이지 성질을 이용하면 적당한 스칼라 함수 \\(\lambda\\)를 선택해서 퍼텐셜 표현을 단순화할 수 있다.
이렇게 선택된 \\(\lambda\\)를 게이지라고 한다.
쿨롱 게이지와 로런츠 게이지가 많이 쓰인다.

### 로런츠 게이지

다음 조건을
<a href="https://en.wikipedia.org/wiki/Lorenz_gauge_condition" target="_blank">로런츠 게이지 조건</a>이라고 한다.
\\[
\partial\_\mu\vb A^\mu=0
\\]
이 조건을 만족키는 전자기 벡터 퍼텐셜을 로런츠 게이지라고 한다.
이 조건을 사용하는 게이지 선택을 <a href="https://en.wikipedia.org/wiki/Gauge_fixing" target="_blank">게이지 고정</a>이라고 한다.
이 조건이 게이지를 유일하게 결정하지는 않는다.
\\(\vb A\\)가 로런츠 게이지이면 맥스웰 방정식은 조화 스칼라 함수 \\(f\\)에 대하여 다음과 같은 게이지 변환에 불변이다.
\\[
\vb A^\mu\longrightarrow\vb A^\mu+\partial^\mu f
\\]
조화 스칼라 함수는 질량 없는 스칼라장의 방정식 \\(\partial\_\mu\partial^\mu f=0\\)를 만족시키는 스칼라 함수를 말한다.

로런츠 게이지 조건은 다음 조건을 만족시키는 스칼라 함수 \\(\lambda\\)를 선태하는 것을 의미한다.
\\[
\divergence{\vb A'}=-\mu\_0\varepsilon\_0\frac{\partial\varphi'}{\partial t}
\\]
\\(\lambda\\)는 다음 방정식을 만족시켜야 한다.
\\[
\laplacian\lambda-\mu\_0\varepsilon\_0\frac{\partial^2\lambda}{\partial t^2}
=-\divergence{\vb A}-\mu\_0\varepsilon\_0\frac{\partial \varphi}{\partial t}
\\]
로런츠 게이지 고정된 맥스웰 방정식은 다음과 같은 꼴로 표현된다.
\begin{align\*}
\dalambert\varphi^\prime&=-\frac\rho{\varepsilon\_0}
\newline
\dalambert\vb A^\prime&=-\mu\_0\vb J
\end{align\*}
단, \\(\dalambert\\)는 달랑베르 작용소이다.
### 달랑베르 작용소

<a href="https://en.wikipedia.org/wiki/D%27Alembert_operator" target="_blank">달랑베르 작용소</a> \\(\dalambert\\)는
파동 작용소, 박스 작용소라고도 하며,
민코프스키 공간의 라플라시안이다.
민코프스키 계량을 \\(g\_{\mu\nu}=\diag{1,-1,-1,-1}\\)이라고 하면 민코프스키 공간의 표준좌표계 \\((t,x,y,z)\\)에서 달랑베르 연산자는 다음과 같은 의미를 가진다.
\begin{align\*}
\dalambert&=\partial^\mu\partial\_\nu=g^{\mu\nu}\partial\_\nu\partial\_\mu
\newline
&=\frac1{c^2}\frac{\partial^2}{\partial t^2}-\laplacian
=\frac1{c^2}\frac{\partial^2}{\partial t^2}-\frac{\partial^2}{\partial x^2}-\frac{\partial^2}{\partial y^2}-\frac{\partial^2}{\partial z^2}
\end{align\*}
\\(\dalambert\\)는 다음과 같은 곳에서 나타난다.

- 파동방정식:
\\(\dalambert\_cU(x,t)=0\\)
- 진공 속 전자기장의 파동방정식:
\\(A^{\mu}\\)가 전자기 4-퍼텐셜일 때,
\\(\dalambert A^{\mu}=0\\)
- 클라인 고든 방정식:
\\(\left(\dalambert+m^2\right)\psi=0\\)

