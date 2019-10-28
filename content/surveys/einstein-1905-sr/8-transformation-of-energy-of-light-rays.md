---
title: "8. 광선 에너지의 변환. 복사가 완전반사체에 주는 압력에 관한 이론"
date: 2019-09-22T16:54:00+09:00
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

## &sect;8. 광선 에너지의 변환. 복사가 완전반사체에 주는 압력에 관한 이론



단위 부피당 빛에너지가 \\(A^2/8\pi\\)이므로,
상대성 원리에 따르면 움직이는 좌표계에서의 빛에너지는 \\(A'^2/8\pi\\)라고 보아야 한다.
그래서 만약 빛덩어리(light complex)의 부피가 \\(K\\)와 \\(k\\) 어떤 좌표계에서 측정하든 같다면, \\(A'^2/A^2\\)가 그 에너지를 "움직일 때 측정한 값''의 "멈춰있을 때 측정한 값''에 대한 비가 될 것이다.
그러나 실제로는 그렇지 않다.
정지 좌표계에서 빛 파동의 법선의 방향코사인을 \\(l,m,n\\)이라고 하자.
광속으로 움직이는 구면
\\[
(x-lct)^2+(y-mct)^2+(z-nct)^2=R^2
\\]
의 표면요소를 에너지가 빠져나갈 수 없다.
따라서 이 표면이 빛덩어리를 영구히 봉인(enclose)한다고도 말할 수 있다.
이 표면에 봉인되어 있는 에너지량을 좌표계 \\(k\\)를 기준으로 구하자. 즉, 빛덩어리의 좌표계 \\(k\\)에 대한 상대적 에너지이다.

이 구면은 움직이는 좌표계를 기준으로 하면 타원면이고, \\(\tau=0\\)에서 그 방정식은 다음과 같다.
\\[
\left(\beta\xi-l\beta\frac vc\xi\right)^2+\left(\eta-m\beta\frac vc\xi\right)^2+\left(\zeta-n\beta\frac vc\xi\right)^2=R^2
\\]

구의 부피를 \\(S\\), 타원체의 부피를 \\(S'\\)이라 하면 간단한 계산
으로 다음을 얻는다.
\\[
\frac{S'}{S}=\frac{\sqrt{1-\left(\frac vc\right)^2}}{1-\frac vc\cos\phi}.
\\]
따라서, 이 표면에 의해 봉인된 빛에너지를 정지 좌표계에서 측정할 때 \\(E\\)라고 하고 움직이는 좌표계에서 측정할 때 \\(E'\\)이라고 하면
\\[
\frac{E'}{E}=\frac{A'^2S'}{A^2S}=\frac{1-\frac vc\cos\phi}{\sqrt{1-\left(\frac vc\right)^2}}
\\]
이고,
\\(\phi=0\\)일 때 이 공식은 간단히
\\[
\frac{E'}{E}=\sqrt{\frac{1-\frac vc}{1+\frac vc}}
\\]
가 된다.








관찰자가 동일한 법칙에 따라 운동해도 빛덩어리의 에너지와 주파수는 그 운동 상태에 따라 달라진다는 점은 주목할 만하다.

이제 좌표평면 \\(\xi=0\\)이 완전한 반사면이라고 하고, &sect;7.에서 다뤘던 평면파가 거기서 반사된다고 하자.
이 반사면에 주는 빛의 압력과 반사된 후의 빛의 방향, 주파수 및 강도를 구한다.

입사광이 (좌표계 \\(K\\) 기준으로) 값 \\(A\\), \\(\cos\phi\\), \\(\nu\\)로 정의된다고 하자.
이 값들을 \\(k\\)에서 보면 다음과 같다.









\begin{align\*}
A'&=A\frac{1-\frac vc\cos\phi}{\sqrt{1-\left(\frac vc\right)^2}},
\newline
\cos\phi'&=\frac{\cos\phi-\frac vc}{1-\frac vc\cos\phi},
\newline
\nu'&=\nu\frac{1-\frac vc\cos\phi}{\sqrt{1-\left(\frac vc\right)^2}}.
\end{align\*}

반사광에 대해서는 좌표계 \\(k\\) 기준으로 다음 식을 얻는다.
\begin{align\*}
A''&=A',
\newline
\cos\phi''&=-\cos\phi',
\newline
\nu''&=\nu'.
\end{align\*}
끝으로,
정지 좌표계 \\(K\\)로 역변환하면 반사광에 대하여 다음 식을 얻는다.
\begin{align\*}
A'''
&=A''\frac{1+\frac vc\cos\phi''}{\sqrt{1-\left(\frac vc\right)^2}}
\newline
&=A\frac{1-2\frac vc\cos\phi+\left(\frac vc\right)^2}{1-\left(\frac vc\right)^2},
\end{align\*}
\begin{align\*}
\cos\phi'''
&=\frac{\cos\phi''+\frac vc}{1+\frac vc\cos\phi''}
\newline
&=-\frac{\left(1+\left(\frac vc\right)^2\right)\cos\phi-2\frac vc}{1-2\frac vc\cos\phi+\left(\frac vc\right)^2},
\end{align\*}
\begin{align\*}
\nu'''
&=\nu''\frac{1+\frac vc\cos\phi''}{\sqrt{1-\left(\frac vc\right)^2}}
\newline
&=\nu\frac{1-2\frac vc\cos\phi+\left(\frac vc\right)^2}{1-\left(\frac vc\right)^2}.
\end{align\*}













단위 시간동안 거울의 단위 면적으로 입사하는 에너지를 (정지 좌표계에서) 구하면, \\(A^2/8\pi\,(c\cos\phi-v)\\)이다.
단위 시간동안 거울의 단위 면적당 반사되는 에너지는 \\(A'''^2/8\pi\,\left(c\cos\phi'''+v\right)\\)이다.
에너지의 원리에 의해 이 두 식의 차는 단위 시간 동안 빛의 압력이 준 일이다.
빛의 압력을 \\(P\\)라 하고 이 일을 곱 \\(Pv\\)와 같다고 두면,
\\[
P=2\frac{A^2}{8\pi}\frac{\left(\cos\phi-\frac vc\right)^2}{1-\left(\frac vc\right)^2}
\\]
을 얻는다.
1차 근사하면 실험 및 기존의 여러 이론과 일치하는 결과를 얻는다.
\\[
P=2\frac{A^2}{8\pi}\cos^2\phi.
\\]

움직이는 물체의 광학과 관련된 모든 문제는 여기서 사용한 방법으로 풀 수 있다.
움직이는 물체에 의한 영향을 받을 때는 빛을 이루는 전기력 및 자기력을 물체에 대해 상대적으로 멈춰있는 좌표계로 변환한다는 것이 핵심이다.
이 방법에 의해, 움직이는 물체의 광학과 관련된 모든 문제가 정지한 물체의 광학에 관한 일련의 문제로 환원된다.

