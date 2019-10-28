---
title: "1.2.4. 리만구면(The Spherical Representation)"
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


# 1.2.4. 리만구면(The Spherical Representation)

복소평면에 무한원점(無限遠點, point at infinity)을 추가해서 확장복소평면을 만든다.
무한원점을 추가함으로써 확장평면은 닫힌 면이 된다. 반평면은 열린 면이므로 무한원점을 포함하지 않는다. 구면 표현에서도 반구면은 대원을 가지지 않는다. 부등식 \\(|z-a|\lt r\\)이 원의 내부를 기술하는 것과 마찬가지로, 유향직선 \\(z=a+bt\\)는 복소평면을 분할한다. \\(\Im\frac{z-a}{b}\lt0\\)는 이 유향직선의 오른쪽 반평면을, \\(\Im\frac{z-a}{b}\gt0\\)는 왼쪽 반평면을 나타낸다.
모든 직선은 무한원점을 지나지만 반평면(half plane)은 무한원점을 포함하지 않는다.

구면은 확장평면의 모든 점을 나타내기 위해 좋은 기하학적 모형을 제공한다.
구면 \\(x_1^2+x_2^2+x_3^2=1\\) 위의 \\((0,0,1)\\)을 제외한 모든 점에 복소수
\begin{equation}
z=\frac{x_1+ix_2}{1-x^3}
\label{eq:24}
\end{equation}
를 주는 일대일대응이 존재한다.
그래서 주어진 복소수에 대응하는 구면좌표는 \eqref{eq:24}로부터 얻을 수 있다.
\\[
|z|^2=\frac{x_1^2+x_2^2}{(1-x_3)^2}=\frac{1+x_3}{1-x^3}
\\]
이므로
\begin{equation}
x_3=\frac{|z|^2-1}{|z|^2+1}
\label{eq:25}
\end{equation}
이고,
\begin{align}\label{eq:26}
\begin{split}
x_1&=\phantom{-i}\frac{z+\bar z}{1+|z|^2}
\newline\newline
x_2&=-i\frac{z-\bar z}{1+|z|^2}
\end{split}
\end{align}
와 같이 나타낼 수 있다.
무한원점은 구면 위의 점 \\((0,0,1)\\)에 대응시킨다.
이 구면을 리만구면이라고 한다.
또, 평면과 구면을 이와 같이 대응시키는 방법을 극사영 또는 입체사영 stereographic projection\\({}\\)이라고 한다.

![](../figures/ahlf124.jpg)

무한원점을 finite한 점과 다름없이 나타낼 수 있다는 것이 구면 표현의 장점이지만, 여기서는 덧셈과 곱셈에 대한 간단한 기하학적 해석이 없다.

\\(z\\)-평면의 직선은 극사영에 의해 극 (0,0,1)을 지나는 \\(S\\) 위의 원으로 옮겨진다. 그 역도 참이다. 보다 일반적으로, \\(S\\) 위의 모든 원은 \\(z\\)-평면 위의 원이나 직선에 대응한다.
\\(S\\) 위의 원이 평면 \\(\alpha_1x_1+\alpha_2x_2+\alpha_3x_3=\alpha_0\\)위에 있다고 하자.
\\(\alpha_1^2+\alpha_2^2+\alpha_3^2=1\\)이라 하면 \\(0\le\alpha_0<1\\)라고 놓을 수 있다(평면의 법선벡터를 정규화하면 상수항 \\(|\alpha_0|\\)가 원점에서 평면 까지의 거리를 나타낸다).
\\[
\alpha_1\left(z+\bar z\right)-\alpha_2i\left(z-\bar z\right)+\alpha_3\left(|z|^2-1\right)=\alpha_0\left(|z|^2+1\right)
\\]
즉,
\\[
(\alpha_0-\alpha_3)(x^2+y^2)-2\alpha_1x-2\alpha_2y+\alpha_0+\alpha_3=0
\\]
이 방정식은 \\(\alpha_0\ne\alpha_3\\)일 때 원이고,
\\(\alpha_0=\alpha_3\\)일 때 직선을 나타낸다.
역으로, \\(z)-평면 위의 임의의 원이나 직선의 방정식을 위와 같은 꼴로 나타낼 수 있다. 그래서 대응은 일대일이다.

\\(z\\)-평면 위의 두 복소수 \\(z\\)와 \\(z'\\)의 극사영 사이의 거리 \\(d(z,z')\\)는 다음과 같이 구할 수 있다:
구면 위의 점을 \\((x_1,x_2,x_3),(x_1',x_2',x_3')\\)로 나타내면
\\[
\left(x_1-x_1'\right)^2+\left(x_2-x_2'\right)^2+\left(x_3-x_3'\right)^2=2-2\left(x_1x_1'+x_2x_2'+x_3x_3'\right)
\\]
이고, 식 \eqref{eq:25}, \eqref{eq:26}으로부터
\begin{align\*}
&x_1x_1'+x_2x_2'+x_3x_3'
\newline\newline
=&\frac{(z+\bar z)(z'+\bar z')-(z-\bar z)(z'-\bar z')+\left(|z|^2-1\right)\left(|z'|^2-1\right)}{\left(1+|z|^2\right)\left(1+|z'|^2\right)}
\newline\newline
=&\frac{\left(1+|z|^2\right)\left(1+|z'|^2\right)-2|z-z'|^2}{\left(1+|z|^2\right)\left(1+|z'|^2\right)}
\newline\newline
=&1-\frac{2|z-z'|^2}{\left(1+|z|^2\right)\left(1+|z'|^2\right)}
\end{align\*}
을 얻는다.
따라서,
\begin{align\*}
d^2(z,z')&=\left(x_1-x_1'\right)^2+\left(x_2-x_2'\right)^2+\left(x_3-x_3'\right)^2
\newline\newline
&=2\left[1-\left(x_1x_1'+x_2x_2'+x_3x_3'\right)\right]
\newline\newline
&=\frac{4|z-z'|^2}{\left(1+|z|^2\right)\left(1+|z'|^2\right)}
\end{align\*}
이므로
\begin{equation}
d(z,z')=\frac{2|z-z'|}{\sqrt{\left(1+|z|^2\right)\left(1+|z'|^2\right)}}
\label{eq:28}
\end{equation}
이다. \\(z'=\infty\\)일 때는
\\[
d(z,\infty)=\frac{2}{\sqrt{1+|z|^2}}
\\]
이다.

>연습문제

1. \\(z\\)와 \\(z'\\)이 리만구면 위에서 지름의 양 끝점에 대응하기 위한 필요충분조건이 \\(z\bar z'=-1\\)임을 보여라.
2. 꼭지점이 모두 구면 \\(S\\) 위에 있고 모서리가 모두 좌표축에 평행한 정육면체에 대하여, 그 꼭지점들의 극사영을 구하라.
3. 임의의 내접 정사면체에 대하여 그 꼭지점들의 극사영을 구하라.
4. \\(z,z'\\)의 극사영을 각각 \\(Z,Z'\\), 북극을  \\(N\\)라 하자. 삼각형 \\(NZZ'\\)와 \\(Nzz'\\)가 닮았음을 보이고, 그 결과를 이용해서 \eqref{eq:28}을 유도하라.
5. 평면 위에서 중심이 \\(a\\)이고 반지름이 \\(R\\)인 원이 극사영된 상의 반지름을 구하라.
