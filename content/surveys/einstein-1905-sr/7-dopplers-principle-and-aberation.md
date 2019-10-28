---
title: "7. 도플러 원리 및 광행차에 관한 이론"
date: 2019-09-22T16:53:29+09:00
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

## &sect;7. 도플러 원리 및 광행차에 관한 이론


전기동역학적 파원이 좌표계 \\(K\\)의 원점에서 아주 멀리 떨어진 곳에 있다면,
원점 근방에서 그 파동은 다음 방정식으로 충분히 근사시킬 수 있다.
\begin{align\*}
X&=X\_0\sin\Phi,&L&=L\_0\sin\Phi,
\newline
Y&=Y\_0\sin\Phi,&M&=M\_0\sin\Phi,
\newline
Z&=Z\_0\sin\Phi,&N&=N\_0\sin\Phi,
\end{align\*}
단,
\\[
\Phi=\omega\left\\{t-\frac{1}{c}(lx+my+nz)\right\\}.
\\]
여기서 \\((X\_0,Y\_0,Z\_0)\\)과 \\((L\_0,M\_0,N\_0)\\)은 파열(wave train)의 진폭을 정의하는 벡터이고 \\(l,m,n\\)은 파의 법선(wave-normals)의 방향코사인들이다.

이제 움직이는 좌표계 \\(k\\)에 대해 멈춰있는 관찰자를 기준으로 해서 파동의 구성을 알아보자.
&sect;6.에서 얻은 전기력 및 자기력의 변환 공식과 &sect;3.에서 얻은 좌표 및 시간의 변환 공식을 사용하면 다음 관계를 바로 얻는다.
\begin{align\*}
X'&=X\_0\sin\Phi',&L'&=L\_0\sin\Phi',
\newline
Y'&=\beta\left(Y\_0-\frac vcN\_0\right)\sin\Phi',&M'&=\beta\left(M\_0+\frac vcZ\_0\right)\sin\Phi',
\newline
Z'&=\beta\left(Z\_0+\frac vcM\_0\right)\sin\Phi',&N'&=\beta\left(N\_0-\frac vcY\_0\right)\sin\Phi'.
\end{align\*}
단,
\\[
\Phi'=\omega'\left\\{\tau-\frac{1}{c}\left(l'\xi+m'\eta+n'\zeta\right)\right\\},
\\]
그리고



















\begin{align\*}
\omega'&=\omega\beta(1-l\frac vc),
\newline
l'&=\frac{l-\frac vc}{1-l\frac vc},
\newline
m'&=\frac{m}{\beta\left(1-l\frac vc\right)},
\newline
n'&=\frac{n}{\beta\left(1-l\frac vc\right)}.
\end{align\*}

\\(\omega'\\)에 관한 방정식에서 다음 결과를 얻는다.
무한히 멀리 있고 주파수가 \\(\nu\\)인 광원에 대해 관찰자가 속도 \\(v\\)로 상대 운동 하고,
이 광원에 대해 멈춰있는 좌표계를 기준으로 한 관찰자의 상대속도와 "광원-관찰자'' 연결선이 이루는 각이 \\(\phi\\)라고 하자.
그러면 관찰자가 보는 빛의 주파수 \\(\nu'\\)는 다음 식으로 주어진다:
\\[
\nu'=\nu\frac{1-\cos\phi\,\frac vc}{\sqrt{1-\left(\frac vc\right)^2}}
\\]
이것은 임의의 속도에 관한 도플러 원리(Doppler's principle)다.
\\(\phi=0\\)이면 방정식은 간결한 꼴을 갖게 된다.
\\[
\nu'=\nu\sqrt{\frac{1-\frac vc}{1+\frac vc}}.
\\]
통상적인 견해와 달리 \\(v=-c\\)일 때 \\(\nu'=\infty\\)임을 알 수 있다.

움직이는 좌표계를 기준으로 한 빛 파동의 법선과 "광원-관찰자'' 연결선 사이의 각을 \\(\phi'\\)라고 하면, \\(l'\\)의 방정식은 다음과 같다.
\\[
\cos\phi'=\frac{\cos\phi-\frac vc}{1-\frac vc\cos\phi}.
\\]
이 식은 광행차의 법칙을 가장 일반적인 형식으로 표현한다.
만약 \\(\phi=\frac{1}{2}\pi\\)이면 방정식은 다음과 같이 간단해진다.
\\[
\cos\phi'=-\frac vc.
\\]

이제 움직이는 좌표계에서 파의 진폭을 구해야 한다.
전기력 또는 자기력의 진폭을 정지 좌표계와 움직이는 좌표계에서 측정한 값을 각각 \\(A\\), \\(A'\\)이라 두면 다음 관계를 얻는다.




\\[
A'^2=A^2\frac{\left(1-\frac vc\cos\phi\right)^2}{1-\left(\frac vc\right)^2}.
\\]
\\(\phi=0\\)이면 식이 간단해진다.
\\[
A'^2=A^2\frac{1-\frac vc}{1+\frac vc}.
\\]

이로부터, 속도 \\(c\\)로 광원에 접근하는
관찰자에게는 이 광원의 세기가 무한히 크게 보인다는 결론을 얻는다.

