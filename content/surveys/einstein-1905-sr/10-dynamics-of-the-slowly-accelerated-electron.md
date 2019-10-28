---
title: "10. 천천히 가속되는 전자의 동역학"
date: 2019-09-22T16:56:30+09:00
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


## &sect;10. 천천히 가속되는 전자의 동역학



하전된 입자(앞으로 "전자''라고 부르자)가 전자기장 안에서 움직이고 있다고 하고, 그 운동 법칙이 다음과 같다고 전제하자.

주어진 시점에 전자가 멈춰있었다면 그 직후의 운동은 다음 방정식을 따른다.
\\[
m\frac{d^2x}{dt^2}=\epsilon X,\quad
m\frac{d^2y}{dt^2}=\epsilon Y,\quad
m\frac{d^2z}{dt^2}=\epsilon Z.
\\]
단, \\(x,y,z\\)는 전자의 좌표를, 그리고 \\(m\\)은 전자가 천천히 움직이고 있을 때의 질량을 나타낸다.

이제 주어진 순간에 전자의 속도가 \\(v\\)라고 하고
그 직후의 운동을 결정하는 법칙을 구한다.

전자가 좌표계 \\(K\\)의 \\(X\\)축을 따라 움직이고 있으며, 현재 속도는 \\(v\\), 현재 위치는 원점이라고 놓아도 논의의 일반성을 잃지 않는다.
\\(X\\)축을 따라 속도 \\(v\\)로 평행하게 움직이는 좌표계를 기준으로 하면, 주어진 순간(\\(t=0\\))에 이 전자는 당연히 멈춰있다.

위의 전제에 상대성 원리를 적용하면, 그 직후에(\\(t\\)가 작은 값을 가질 때) 전자는 좌표계 \\(k\\)를 기준으로 다음 방정식을 따라 움직인다.
\\[
m\frac{d^2\xi}{d\tau^2}=\epsilon X',\quad
m\frac{d^2\eta}{d\tau^2}=\epsilon Y',\quad
m\frac{d^2\zeta}{d\tau^2}=\epsilon Z'.
\\]
여기서 기호 \\(\xi,\eta,\zeta\\), \\(X',Y',Z'\\)는 좌표계 \\(k\\)에서의 값들이다.
또, \\(t=x=y=z=0\\)일 때 \\(\tau=\xi=\eta=\zeta=0\\)이라 두면,
&sect;3.과 &sect;6.의 변환 공식에 따라 이들은 다음 관계를 갖는다.
\\[
\tau=\beta\left(t-\frac{v}{c^2}x\right),
\\]
\begin{align\*}
\xi&=\beta(x-vt),&X'&=X,
\newline
\eta&=y,&Y'&=\beta\left(Y-\frac vcN\right),
\newline
\zeta&=z,&Z'&=\beta\left(Z+\frac vcM\right).
\end{align\*}

이 관계들을 이용해서 좌표계 \\(k\\)에 관한 운동방정식을 좌표계 \\(K\\)로 변환하면 다음과 같다.
\\[\begin{aligned}
\frac{d^2x}{dt^2}&=\frac{\epsilon}{m}\frac{1}{\beta^3}X
\newline
\frac{d^2y}{dt^2}&=\frac{\epsilon}{m}\frac{1}{\beta}\left(Y-\frac vcN\right)
\newline
\frac{d^2z}{dt^2}&=\frac{\epsilon}{m}\frac{1}{\beta}\left(Z+\frac vcM\right).
\end{aligned}\tag{A}\label{eq:a}\\]


통상적인 관점대로, 움직이는 전자의 "종적(longitudinal)'', "횡적(transverse)'' 질량을 구해보자.
윗 식 \eqref{eq:a}를 다음과 같이 바꿔 쓸 수 있다.
\begin{alignat\*}{3}
m\beta^3\frac{d^2x}{dt^2}&=\epsilon X&=\epsilon X',
\newline
m\beta^2\frac{d^2y}{dt^2}&=\epsilon\beta\left(Y-\frac vcN\right)&=\epsilon Y',
\newline
m\beta^2\frac{d^2z}{dt^2}&=\epsilon\beta\left(Z+\frac vcM\right)&=\epsilon Z'
\end{alignat\*}
먼저, \\(\epsilon X',\epsilon Y',\epsilon Z'\\)가 전자에 작용하는 판드로모티브 힘의 성분들임을 알아두자. 측정 순간에 전자와 같은 속도인 좌표계에서 본 깂들이다.
(이 힘은 가령 그 좌표계에 대해 멈춰있는 용수철 저울을 써서 측정할 수 있을 것이다)
이제 이 힘을 간단히 "전자가 받는 힘''이라고 부르자.
위 방정식이 \\(질량\times가속도=힘\\)의 관계를 나타낸다고 하고, 정지 좌표계 \\(K\\)에서 측정된 가속도를 적용하면




다음 결과를 얻는다.
\begin{align\*}
종적\ 질량&=\frac{m}{\left(\sqrt{1-\left(\frac vc\right)^2}\right)^3},
\newline
횡적\ 질량&=\frac{m}{1-\left(\frac vc\right)^2}.
\end{align\*}

힘과 가속도가 다른 방식으로 정의되면 당연히 다른 질량 값을 얻는다.
이것은 전자 운동에 관한 서로 다른 이론들을 비교할 때 매우 주의 해야 한다는 것을 보여준다.

질량에 관한 이와 같은 결과가 다른 무게있는 질점(ponderable　material point)에 대해서도 항상 성립한다는 점을 알아두자.
무게있는 질점은 **아무리 작은 양이라도**\\(\\) 전하를 주기만 하면 (우리가 지금 사용하는 의미에서) 전자가 될 수 있기 때문이다.

이제 전자의 운동에너지를 구하자.
전자가 좌표계 \\(K\\)의 원점에 멈춰있다가 정전기력 \\(X\\)의 작용을 받아 \\(X\\)축을 따라 움직인다고 하자.
그러면 정전기장에서 감소되는 에너지는 당연히 \\(\int\epsilon Xdx\\)의 값을 갖는다.
전자가 느리게 가속돼서 복사 형태로 에너지를 방출하지 않는다면 정전기장에서 감소되는 에너지는 모두 전자의 운동에너지 \\(W\\)로 이전되어야 한다.
이 운동 전체가 \eqref{eq:a}의 첫번째 방정식을 따르는 과정이라는 것을 감안하면, 다음을 얻는다.
\begin{align\*}
W&=\int\epsilon Xdx=m\int\_{0}^{v}\beta^3v dv
\newline
&=mc^2\left\\{\frac{1}{\sqrt{1-\left(\frac vc\right)^2}}-1\right\\}.
\end{align\*}

그러므로,
\\(v=c\\)이면 \\(W\\)는 무한대가 된다.
광속보다 큰 속도는---앞에서 얻은 결과와 마찬가지로---존재할 수 없다.

앞에서와 같은 이유로, 운동에너지에 관한 이 식은 무게있는 다른 질점에도 적용된다.

이제 방정식 \eqref{eq:a}에서 도출되는 전자 운동의 속성으로서 실험으로 확인할 수 있는 것들을 열거해 보자.

1. \eqref{eq:a}의 두번째 방정식으로부터, \\(Y=Nv/c\\)일 때 전기력 \\(Y\\)와 자기력 \\(N\\)은 속도 \\(v\\)로 움직이는 전자에 대해 동일한 크기의 편향 작용(deflective action)을 준다.
따라서 우리 이론에 의하면 자기적 편향 능력(power of deflexion) \\(A\_m\\)의 전기적 편향 능력 \\(A\_e\\)에 대한 비를 이용해서 전자의 속도를 구할 수 있다는 것을 알 수 있다.
임의의 속도에 대하여
\\[
\frac{A\_m}{A\_e}=\frac{v}{c}
\\]
라는 법칙을 적용하면 된다.
전자의 속도는 가령 빠르게 진동하는 전기장과 자기장을 이용하면 직접 측정할 수 있으므로, 이 관계는 실험으로 검증할 수 있다.
2. 전자의 운동에너지를 도출한 위의 관계식에서, 전자가 가로지르는 퍼텐셜의 차 \\(P\\)와 전자가 얻은 속도 \\(v\\) 사이에 다음 관계가 얻어진다.
\\[
P=\int Xdx=\frac{m}{\epsilon}c^2\left\\{\frac{1}{\sqrt{1-\left(\frac vc\right)^2}}-1\right\\}.
\\]
3. 자기력 \\(N\\)이 (유일한 편향력으로) 존재해서 전자의 속도에 수직 방향으로 작용할 때 전자의 경로에 대한 곡률반경을 계산하자.
\eqref{eq:a}의 두번째 방정식으로부터,
\\[
-\frac{d^2y}{dt^2}=\frac{v^2}{R}=\frac{\epsilon}{m}\frac{v}{c}N\sqrt{1-\left(\frac vc\right)^2}
\\]
즉,
\\[
R=\frac{mc^2}{\epsilon}\frac{\frac vc}{\sqrt{1-\left(\frac vc\right)^2}}\frac{1}{N}
\\]
을 얻는다.

이 세가지 관계식들이 우리가 전개한 이론에 의한 전자의 운동 법칙을 완전하게 표현한다.

마치면서,
여기서 다룬 문제들과 관련된 작업에서 친구이자 동료인 베소(M.Besso)의 정성스런 도움을 받았으며, 그의 몇가지 귀중한 조언을 따랐다는 것을 밝혀둔다.
