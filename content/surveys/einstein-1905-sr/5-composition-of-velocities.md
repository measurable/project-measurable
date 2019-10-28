---
title: "5. 속도의 합성"
date: 2019-09-22T16:52:02+09:00
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

#### I. 운동학 (Kinematic Part)

## &sect;5. 속도의 합성



좌표계 \\(k\\)가 좌표계 \\(K\\)의 \\(X\\)축을 따라 속도 \\(v\\)로 움직이고 있다.
한 점이 \\(k\\)를 기준으로 다음 방정식에 따라 상대 운동 한다고 하자.
\\[
\xi=w\_\xi\tau,\quad\eta=w\_\eta\tau,\quad\zeta=0,
\\]
단, \\(w\_\xi\\)와 \\(w\_\eta\\)는 상수이다.

문제: 이 점의 좌표계 \\(K\\)에 대한 상대 운동을 구하라.
&sect;3.에서 얻은 변환 공식을 이용해서 위의 운동방정식을 좌표 \\(x,y,z,t\\)로 나타내면 다음과 같다.
\\[\begin{aligned}
x&=\frac{w\_\xi+v}{1+\frac{vw\_\xi}{c^2}}t,
\newline
y&=\frac{\sqrt{1-\left(\frac vc\right)^2}}{1+\frac{vw\_\xi}{c^2}}w\_\eta t,
\newline
z&=0.
\end{aligned}\\]

그래서 우리 이론에서는 속도 합성에 관한 평행사변형 법칙이 단지 1차 근사로만 성립한다.
이제
\\[\begin{aligned}
V^2&=\left(\frac{dx}{dt}\right)^2+\left(\frac{dy}{dt}\right)^2,
\newline
w^2&=w\_\xi^2+w\_\eta^2,
\newline
a&=\tan^{-1}\frac{w\_\eta}{w\_\xi}
\end{aligned}\\]
라 놓자.
여기서 \\(a\\)는 속도 \\(v\\)와 \\(w\\)의 사잇각이라고 할 수 있다.

간단한 계산을 통해 다음을 얻는다.
\\[
V=\frac{\sqrt{\left(v^2+w^2+2vw\cos a\right)-\left(\frac{vw\sin a}{c}\right)^2}}{1+\frac{vw\cos a}{c^2}}
\\]
위 식은 합성된 속도를 나타낸다. 여기에 \\(v\\)와 \\(w\\)가 대칭꼴로 포함되어 있다는 것도 알아두자.




만약 \\(w\\)도 \\(X\\)축 방향이면,
\\[
V=\frac{v+w}{1+\frac{vw}{c^2}}
\\]
이다.
이 방정식으로부터, \\(c\\)보다 작은 두 속도를 합성하면 그 결과도 항상 \\(c\\)보다 작다는 사실을 알 수 있다.
만약 \\(v=c-\kappa\\), \\(w=c-\lambda\\)이고 \\(\kappa\\)와 \\(\lambda\\)가 \\(c\\)보다 작은 양수라고 하면,
\\[
V=c\frac{2c-\kappa-\lambda}{2c-\kappa-\lambda+\frac{\kappa\lambda}{c}} < c.
\\]
이기 때문이다.

또한, 광속 \\(c\\)를 이보다 작은 속도와 합성한다고 해도 그 값은 변하지 않는다는 사실도 알 수 있다.
이 경우엔,
\\[
V=\frac{c+w}{1+\frac{w}{c}}=c
\\]
이다.

\\(v\\)와 \\(w\\)가 같은 방향일 경우에는 &sect;3.에 따라 두 변환 공식을 합성해서 \\(V\\)의 공식을 얻을 수도 있다.
&sect;3.에서 다뤘던 두 좌표계 \\(K\\)와 \\(k\\)에 또다른 좌표계 \\(k'\\)을 추가한다.
그것이 원점을 \\(X\\)축에 둔 채 \\(k\\)에 대해 \\(w\\)의 속도로 병진운동한다고 하면,
좌표 \\(x,y,z,t\\)와 그에 대응하는 \\(k'\\)의 좌표들 사이의 관계식을 얻는다.
이 관계식은 &sect;3.에서 얻은 방정식의 "\\(v\\)'' 자리에
\\[
\frac{v+w}{1+\frac{vw}{c^2}}
\\]
를 넣은 것과 같다.
이로부터, 이렇게 평행한 변환들이---반드시---군(group)을 이룬다는 사실을 알 수 있다.

이제 우리의 두 원리에 상응하는 운동학 이론의 법칙들을 얻었다.
이를 전기동역학에 적용해 보자.
