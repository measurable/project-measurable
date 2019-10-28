---
title: "6. 진공에서의 맥스웰-헤르츠 방정식의 변환. 운동에 의해 자기장 안에서 발생하는 기전력의 본질에 관하여"
date: 2019-09-22T16:52:47+09:00
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


## &sect;6. 진공에서의 맥스웰-헤르츠 방정식의 변환. 운동에 의해 자기장 안에서 발생하는 기전력의 본질에 관하여



빈 공간에서의 맥스웰-헤르츠 방정식이 정지 좌표계 \\(K\\)에서 성립한다고 하자.
즉, 전기력 벡터를 \\((X,Y,Z)\\), 자기력 벡터를 \\((L,M,N)\\)로 나타내면 이들은 다음 관계를 가진다.
\begin{align\*}
\frac{1}{c}\frac{\partial X}{\partial t}&=\frac{\partial N}{\partial y}-\frac{\partial M}{\partial z},&\frac{1}{c}\frac{\partial L}{\partial t}&=\frac{\partial Y}{\partial z}-\frac{\partial Z}{\partial y},
\newline
\frac{1}{c}\frac{\partial Y}{\partial t}&=\frac{\partial L}{\partial z}-\frac{\partial N}{\partial x},&\frac{1}{c}\frac{\partial M}{\partial t}&=\frac{\partial Z}{\partial x}-\frac{\partial X}{\partial z},
\newline
\frac{1}{c}\frac{\partial Z}{\partial t}&=\frac{\partial M}{\partial x}-\frac{\partial L}{\partial y},&\frac{1}{c}\frac{\partial N}{\partial t}&=\frac{\partial X}{\partial y}-\frac{\partial Y}{\partial x}.
\end{align\*}

위의 전자기적 과정을 속도 \\(v\\)로 움직이는 좌표계를 기준으로 나타내자.
위의 방정식에 &sect;3.에서 얻은 변환을 적용하면 다음 방정식들을 얻는다.


\\[\begin{array}{lll}
\frac{1}{c}\frac{\partial}{\partial\tau}X&=\frac{\partial}{\partial\eta}\left\\{\beta\left(N-\frac vcY\right)\right\\}&-\frac{\partial}{\partial\zeta}\left\\{\beta\left(M+\frac vcZ\right)\right\\},
\newline
\frac{1}{c}\frac{\partial}{\partial\tau}\left\\{\beta\left(Y-\frac vcN\right)\right\\}&=\frac{\partial}{\partial\zeta}L&-\frac{\partial}{\partial\xi}\left\\{\beta\left(N-\frac vcY\right)\right\\},
\newline
\frac{1}{c}\frac{\partial}{\partial\tau}\left\\{\beta\left(Z+\frac vcM\right)\right\\}&=\frac{\partial}{\partial\xi}\left\\{\beta\left(M+\frac vcZ\right)\right\\}&-\frac{\partial}{\partial\eta}L,
\newline
\frac{1}{c}\frac{\partial}{\partial\tau}L&=\frac{\partial}{\partial\zeta}\left\\{\beta\left(Y-\frac vcN\right)\right\\}&-\frac{\partial}{\partial\eta}\left\\{\beta\left(Z+\frac vcM\right)\right\\},
\newline
\frac{1}{c}\frac{\partial}{\partial\tau}\left\\{\beta\left(M+\frac vcZ\right)\right\\}&=\frac{\partial}{\partial\xi}\left\\{\beta\left(Z+\frac vcM\right)\right\\}&-\frac{\partial}{\partial\zeta}X,
\newline
\frac{1}{c}\frac{\partial}{\partial\tau}\left\\{\beta\left(N-\frac vcY\right)\right\\}&=\frac{\partial}{\partial\eta}X&-\frac{\partial}{\partial\xi}\left\\{\beta\left(Y-\frac vcN\right)\right\\}.
\end{array}\\]
단,
\\[
\beta=\frac{1}{\sqrt{1-\left(\frac vc\right)^2}}
\\]
이다.

상대성 원리에 따르면 맥스웰-헤르츠 방정식이 좌표계 \\(K\\)에서 성립하면 좌표계 \\(k\\)에서도 성립해야 한다.
즉, 움직이는 좌표계 \\(k\\)의 전기력 및 자기력 벡터---\\((X',Y',Z')\\)와 \\((L',M',N')\\). 각각 전기적, 자기적 질량에 주는 판드로모티브 효과(ponderomotive effect)
로 정의된다---가 다음 방정식을 만족한다.
\begin{align\*}
\frac{1}{c}\frac{\partial X'}{\partial\tau}&=\frac{\partial N'}{\partial\eta}-\frac{\partial M'}{\partial\zeta},&\frac{1}{c}\frac{\partial L'}{\partial\tau}&=\frac{\partial Y'}{\partial\zeta}-\frac{\partial Z'}{\partial\eta},
\newline
\frac{1}{c}\frac{\partial Y'}{\partial\tau}&=\frac{\partial L'}{\partial\zeta}-\frac{\partial N'}{\partial\xi},&\frac{1}{c}\frac{\partial M'}{\partial\tau}&=\frac{\partial Z'}{\partial\xi}-\frac{\partial X'}{\partial\zeta},
\newline
\frac{1}{c}\frac{\partial Z'}{\partial\tau}&=\frac{\partial M'}{\partial\xi}-\frac{\partial L'}{\partial\eta},&\frac{1}{c}\frac{\partial N'}{\partial\tau}&=\frac{\partial X'}{\partial\eta}-\frac{\partial Y'}{\partial\xi}.
\end{align\*}

당연히, 좌표계 \\(k\\)에서 얻은 이 두 벌의 연립방정식은 정확하게 같은 것을 나타낸다.
각각이 좌표계 \\(K\\)의 맥스웰-헤르츠 방정식과 동치(equivalent)이기 때문이다.
또 두 연립방정식이 벡터 기호만 다를 뿐 서로 일치하므로,
한 쪽 연립방정식에 포함된 모든 함수에 적당한 공통 인수 \\(\psi(v)\\)를 곱해서 서로 대응되는 자리에 있는 함수끼리 같게 놓을 수 있다.




이 인수는 \\(\xi,\eta,\zeta\\) 및 \\(\tau\\)와 독립이고 \\(v\\)에 의존한다.
그래서 다음 관계를 얻는다.
\begin{align\*}
X'&=\psi(v)X,&L'&=\psi(v)L,
\newline
Y'&=\psi(v)\beta\left(Y-\frac vcN\right),&M'&=\psi(v)\beta\left(M+\frac vcZ\right),
\newline
Z'&=\psi(v)\beta\left(Z+\frac vcM\right),&N'&=\psi(v)\beta\left(N-\frac vcY\right).
\end{align\*}

이제 이 연립방정식의 상반식(reciprocal)을 만들자.
먼저 바로 위에서 구한 관계식을 풀어서 구하고,
다음엔 연립방정식을 속도가 \\(-v\\)인 (\\(k\\)에서 \\(K\\)로의) 역변환 공식에 넣어서 구한다.
이렇게 얻어진 두 연립방정식이 항등이어야 하므로,
\\[
\psi(v)\psi(-v)=1
\\]
을 얻는다.
대칭성[^7]
때문에
\\[
\psi(v)=\psi(-v)
\\]
이어야 하므로
\\[
\phi(v)=1
\\]
이다. 결국 방정식은 다음 꼴이 된다.
\begin{align\*}
X'&=X,&L'&=L,
\newline
Y'&=\beta\left(Y-\frac vcN\right),&M'&=\beta\left(M+\frac vcZ\right),
\newline
Z'&=\beta\left(Z+\frac vcM\right),&N'&=\beta\left(N-\frac vcY\right).
\end{align\*}
이들 방정식의 해석과 관련해서는 다음과 같이 말할 수 있다.
한 점전하가 정지 좌표계 \\(K\\)에서 측정했을 때 "1''의 크기를 갖는다.
즉 정지 좌표계에 멈춰있을 때 1\\(\,\mathrm{cm}\\) 떨어져 있는 같은 크기의 전하량에 1\\(\,\mathrm{dyne}\\)의 힘을 준다.
상대성 원리에 의해, 움직이는 좌표계에서 측정했을 때도 이 점전하의 크기는 똑같이 "1''이다.
이 전하량이 정지 좌표계를 기준으로 멈춰있다면, 정의에 의해 벡터 \\((X,Y,Z)\\)에 해당하는 힘을 받는다.
이 전하량이 움직이는 좌표계를 기준으로 (적어도 측정 순간에는) 멈춰있을 때 받는 힘을 움직이는 좌표계에서 측정하면 벡터 \\((X',Y',Z')\\)이다.
그래서, 위의 왼쪽 세 방정식을 말로는 다음과 같이 두가지 방법으로 설명할 수 있다.


1. 단위 점전하가 전자기장 안에서 움직이고 있으면 전기력과 함께 "기전력(electromotive force)''도 받는다.
\\(v/c\\)에 관한 2차 이상의 거듭제곱이 곱해진 항을 버리면 이 기전력은 전하의 속도와 자기력의 벡터곱을 빛의 속도로 나눈 것과 같다(기존의 설명 방법).
2. 단위 점전하가 전자기장 안에서 움직일 때 받는 힘은 전하가 위치한 지점에 존재하는 전기력이다.
이 힘은 장을 전하에 대해 상대적으로 멈춰있는 좌표계로 변환해서 구한다(새로운 설명 방법).


[^7]:예를 들어, 만약 \\(X=Y=Z=L=M=0\\)이고 \\(L\ne0\\)이면, \\(v\\)가 절대값 변화 없이 부호만 바뀔 때 \\(Y'\\)도 역시 절대값 변화 없이 부호만 바뀐다. 대칭성에 의한 당연한 결과다.

동일한 논리가 "기자력(magnetomotive forces)''에 대해서도 적용된다.






우리 이론에서 기전력은 단지 보조적인 개념의 역할을 할 뿐이라는 것을 알 수 있다.
이 개념이 도입되는 것은 전기력과 자기력이 좌표계의 운동 상태와 무관하게 존재하는 것이 아니라는 사실 때문이다.

나아가, 자석과 도체의 상대 운동에 의해 발생하는 전류와 관련해서 도입부에서 언급했던 비대칭성도 이제 사라진다.
나아가, 전기동역학적 기전력의 (단극형 기계(unipolar machines)의) "자리''와 관련된 문제도 이제 의미를 잃는다.

