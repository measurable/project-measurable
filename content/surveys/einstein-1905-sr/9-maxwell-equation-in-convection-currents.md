---
title: "9. 대류(Convection-Currents)를 감안한 맥스웰-헤르츠 방정식의 변환"
date: 2019-09-22T16:55:07+09:00
categories:
    - 표현
tags:
    - sr
    - Einstein
keywords:
inspired:
motivation:
draft: false
---

#### II. 전기동역학 (Electrodynamical Part)

## &sect;9. 대류(Convection-Currents)를 감안한 맥스웰-헤르츠 방정식의 변환



다음 방정식에서 시작하자.
\begin{align\*}
\frac{1}{c}\left\\{\frac{\partial X}{\partial t}+u\_x\rho\right\\}&=\frac{\partial N}{\partial y}-\frac{\partial M}{\partial z},&\frac{1}{c}\frac{\partial L}{\partial t}&=\frac{\partial Y}{\partial z}-\frac{\partial Z}{\partial y},
\newline
\frac{1}{c}\left\\{\frac{\partial Y}{\partial t}+u\_y\rho\right\\}&=\frac{\partial L}{\partial z}-\frac{\partial N}{\partial x},&\frac{1}{c}\frac{\partial M}{\partial t}&=\frac{\partial Z}{\partial x}-\frac{\partial X}{\partial z},
\newline
\frac{1}{c}\left\\{\frac{\partial Z}{\partial t}+u\_z\rho\right\\}&=\frac{\partial M}{\partial x}-\frac{\partial L}{\partial y},&\frac{1}{c}\frac{\partial N}{\partial t}&=\frac{\partial X}{\partial y}-\frac{\partial Y}{\partial x},
\end{align\*}
단,
\\[
\rho=\frac{\partial X}{\partial x}+\frac{\partial Y}{\partial y}+\frac{\partial Z}{\partial z}
\\]
는 전하밀도의 \\(4\pi\\)배를,
\\((u\_x,u\_y,u\_z)\\)는 전하의 속도벡터를 나타낸다.
전하가 항상 작은 강체(이온, 전자 등)와 결합돼 있다고 생각하면 이들 방정식은 로렌츠의 전기동역학 및 움직이는 물체에 대한 광학의 전자기학적 근거를 준다.

이들 방정식이 좌표계 \\(K\\)에서 성립한다고 하고,
&sect;3.과 &sect;6.에서 얻은 변환 공식을 이용해서 좌표계 \\(k\\)로 변환하자.
그러면 다음 방정식을 얻는다.
\begin{align\*}
\frac{1}{c}\left\\{\frac{\partial X'}{\partial\tau}+u\_\xi\rho'\right\\}&=\frac{\partial N'}{\partial\eta}-\frac{\partial M'}{\partial\zeta},&\frac{1}{c}\frac{\partial L'}{\partial\tau}&=\frac{\partial Y'}{\partial\zeta}-\frac{\partial Z'}{\partial\eta},
\newline
\frac{1}{c}\left\\{\frac{\partial Y'}{\partial\tau}+u\_\eta\rho'\right\\}&=\frac{\partial L'}{\partial\zeta}-\frac{\partial N'}{\partial\xi},&\frac{1}{c}\frac{\partial M'}{\partial\tau}&=\frac{\partial Z'}{\partial\xi}-\frac{\partial X'}{\partial\zeta},
\newline
\frac{1}{c}\left\\{\frac{\partial Z'}{\partial\tau}+u\_\zeta\rho'\right\\}&=\frac{\partial M'}{\partial\xi}-\frac{\partial L'}{\partial\eta},&\frac{1}{c}\frac{\partial N'}{\partial\tau}&=\frac{\partial X'}{\partial\eta}-\frac{\partial Y'}{\partial\xi}.
\end{align\*}
단,
\begin{align\*}
u\_\xi&=\frac{u\_x-v}{1-\frac{u\_xv}{c^2}},
\newline
u\_\eta&=\frac{u\_y}{\beta\left(1-\frac{u\_xv}{c^2}\right)},
\newline
u\_\zeta=\frac{u\_z}{\beta\left(1-\frac{u\_xv}{c^2}\right)},
\end{align\*}









그리고
\begin{align\*}
\rho'&=\frac{\partial X'}{\partial\xi}+\frac{\partial Y'}{\partial\eta}+\frac{\partial Z'}{\partial\zeta}=\beta\left(1-\frac{u\_xv}{c^2}\right)\rho.
\end{align\*}

벡터 \\((u\_\xi,u\_\eta,u\_\zeta)\\)는 바로---속도의 합성에 관한 정리(&sect;5.)에 따른---좌표계 \\(k\\) 기준의 전하 속도이다.
따라서 이제 우리의 운동학 원리에 근거해서, 움직이는 물체의 전기동역학에 관한 로렌츠 이론의 전기동역학적 기초가 상대성 원리와 일치한다는 사실이 증명됐다.

덧붙여, 우리가 얻은 이론으로터 다음과 같은 중요한 법칙이 쉽게 유도된다는 것을 간단히 언급해둔다.
전하를 띤 물체가 공간 속 임의의 위치에서 움직이고 있을 때, 그 물체와 함께 움직이는 좌표계를 기준으로 해서 전하량이 바뀌지 않는다면 "정지''좌표계 \\(K\\)를 기준으로 해도 전하량은 여전히 상수이다.

