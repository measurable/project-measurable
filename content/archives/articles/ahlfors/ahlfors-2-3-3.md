---
title: "Ahlfors 2 3 3"
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


# 2.3.3. 주기성Periodicity

\\(e^{z+c}=e^z,\ \forall z\\)이면 \\(e^c=1\\)이므로 \\(c=i\omega,\ \omega\in\mathbb R\\)이다.
관례적으로, \\(\omega\\)가 \\(e^{iz}\\)의 주기라고 말한다.[^ezperi]
이제 지수함수의 주기가 존재하고, 그것이 어떤 양의 주기 \\(\omega_0\\)의 임의의 정수배임을 보일 것이다.[^periproc]

[^ezperi]:\\(e^{i(z+\omega)}=e^{iz}\implies e^{i\omega}=1\\)
[^periproc]: \\(e^{i\omega}=1\\)을 만족하는 \\(0\\) 아닌 실수 \\(\omega\\)가 존재함을 보이면 주기의 존재가 증명된다. 아래 증명에서 \\(\omega=4y_0\\)이다. 증명 과정에서 주기가 양수로 얻어지므로  \\(n\omega\\)도 주기임을 보이면 증명은 완성된다.

\\(D\sin y=\cos y\le1\\)과 \\(\sin0=0\\)으로부터
\\[
\sin y<y,\ \forall y
\\]
를 얻는다. 적분이나 중간값 정리를 쓰면 된다.[^periproc1]
같은 방법으로 \\(D\cos y=-\sin y>-y\\)와 \\(\cos0=1\\)이
\\[
\cos y>1-\frac{y^2}{2}
\\]
를 주고,[^periproc2] 이 결과로부터 다시
\\[
\sin y>y-\frac{y^3}{6}
\\]
를, 이로부터 최종적으로
\\[
\cos y<1-\frac{y^2}{2}+\frac{y^4}{24}
\\]
를 얻는다.
이 부등식은 \\(\cos\sqrt3<0\\)임을 의미하므로,[^getsqrt3]
\\[\cos y_0=0,\ 0<y_0<\sqrt3
\\]
을 만족하는 \\(y_0\\)가 존재한다. 이 때,
\\[
\cos^2y_0+\sin^2y_0=1
\\]
에서 \\(\sin y_0=\pm1\\)이므로 \\(e^{iy_0}=\pm i\\)이다.
그래서 \\(e^{4iy_0}=1\\)이다.
주기 \\(4y_0\\)가 존재한다는 사실을 보였다.\\(\Box\\)

[^periproc1]: \\(\cos y\le1\\)은 항등식 \\(\cos^2y+\sin^2=1\\)에서 얻는다.
적분을 사용하면
\\[\cos y\le1\implies\int_0^y\cos tdt\le\int_0^y1dt
\\]
로부터 \\(\sin y\le y,\ \forall y>0\\)을 얻는다.
평균값 정리를 사용하면,
\\[
\frac{\sin y-\sin0}{y-0}=\cos y'\le1
\\]
에서 같은 부등식을 얻는다.
부등식에서 등호를 제거하려면, 어떤 \\(y_0>0\\)에 대하여 등호가 성립하면 \\(\cos y>1\\)인 \\(0\le y<y_0\\)가 존재함을 보이면 된다.

[^periproc2]: 적분을 사용하면,
\\[
-\sin y>-y\implies\int_0^y(-\sin t)dt>\int_0^y(-y)dt
\\]
에서 첫번째 결과를 얻고 그로부터 다시,
\\[
\cos y>1-\frac{y^2}{2}\implies\int_0^y\cos tdt>\int_0^y\left(1-\frac{t^2}{2}\right)dt
\\]
에서 두번째 결과를 얻는다. 세번째 결과는,
\\[
\sin y>y-\frac{y^3}{6}\implies\int_0^y\sin tdt>\int_0^y\left(t-\frac{t^3}{6}\right)tdt
\\]
에서 얻는다.

[^getsqrt3]: 바로 위 부등식의 우변, \\(\displaystyle 1-\frac{y^2}{2}+\frac{y^4}{24}=0\\)의 해가 \\(\sqrt3\\)이다.
\\(\cos y_0=0\\)을 만족하는 \\(y_0\in\left(0,\sqrt3\right)\\)의 존재는 \\(\cos\sqrt3<0\\)과 \\(\cos0=1>0\\)에 중간값 정리를 적용해서 얻은 결과다.

사실 이 \\(4y_0\\)는 양의 최소 주기다.
\\(0<y<y_0\\)이면
\\[
\sin y>y\left(1-\frac{y^2}{6}\right)>\frac{y}{2}
\\]
이므로[^pfmin] \\(\cos y\\)는 순감소한다.
한편 \\(\cos^2y+\sin^2y=1\\)이고 \\(\sin y\\)는 양이므로 순증가하며, 그래서 이 구간에서 \\(\sin y<\sin y_0=1\\)이다.
즉, \\(0<\sin y<1\\)이다. 그래서 \\(e^{iy}\\)는 \\(\pm1\\)도 아니고 \\(\pm i\\)도 아니다.
그래서 \\(0<y<y_0\\)이면 \\(e^{4iy}\ne1\\)이다.
\\(4y_0\\)가 양의 최소 주기임을 보였다.\\(\Box\\)

[^pfmin]: \\(0<y<y_0<\sqrt3\\)이므로
\\[
\sin y>y\left(1-\frac{y^2}{6}\right)>y\left(1-\frac{\left(\sqrt3\right)^2}{6}\right)=\frac{y}{2}>0
\\]
이고 \\(D\cos y=-\sin y<0\\)이다.

이제 양의 최소 주기를 \\(\omega_0\\)라 하고, \\(\omega\\)가 임의의 주기라 하면, \\(n\omega_0\le\omega<(n+1)\omega_0\\)를 만족하는 정수 \\(n\\)이 존재한다.
만약 \\(\omega\ne n\omega_0\\)이면 \\(\omega-n\omega_0\\)는 \\(\omega_0\\)보다 작은 양의 주기가 되므로[^w-nw0] 모순이다.
그래서 \\(\omega=n\omega_0\\)이다.\\(\Box\\)

[^w-nw0]: \\(n\omega_0<\omega<(n+1)\omega_0\\)에서 \\(0<\omega-n\omega_0<\omega_0\\)이고,
\\[
\exp{i(\omega-n\omega_0)}=\frac{\exp{i\omega}}{\exp{in\omega_0}}=\frac{1}{1^n}=1
\\]

\\(e^{iz}\\)의 양의 최소 주기를 \\(2\pi\\)로 나타낸다.

증명 과정에서 다음 사실을 이미 보였다.
\\[
e^{i\frac{\pi}{2}}=i,\quad e^{i\pi}=-1,\quad e^{2\pi i}=1
\\]
이 등식들은 \\(e\\)와 \\(\pi\\)의 밀접한 관계를 보여준다.[^enpi]

[^enpi]: 그래서 \\(\pi\\)의 연구에 이 관계가 중요하게 사용된다는...?

\\(y\\)가 \\(0\\)에서 \\(2\pi\\)까지 증가할 때 점 \\(w=e^{iy}\\)는 양의 방향으로의 단위원 \\(|w|=1\\)의 자취를 기술한다.
\\(|w|=1\\)인 모든 \\(w\\)에 대하여 \\(w=e^{iy}\\)를 만족하는 \\(y\\)가 반열린구간 \\(0\le y<2\pi\\)에 꼭 한개 존재한다.
All this follows readily from the extablished fact that \\(\cos y\\) is strictly decreasing in the "first quadrant," that is, between \\(0\\) and \\(\pi/2\\).[^1quadr]

[^1quadr]: 이게 무슨 뜻?

대수적 관점에서 보면 사상 \\(w=e^{iy}\\)는 실수의 덧셈군과 절대값 \\(1\\)인 복소수의 곱셈군 사이의 준동형사상homomorphism\\({}\\)을 만든다.
이 준동형사상의 핵kernel\\({}\\)은 임의의 정수배 \\(2\pi n\\)으로 만들어지는 부분군이다.
