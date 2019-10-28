---
title: "1. From SR to Blackhole (1)"
date: 2019-09-22T01:01:26+09:00
categories:
    - 표현
tags:
    - 블랙홀
    - sr
    - gr
keywords:
inspired: https://horizon.kias.re.kr/archives/allarticles/mathematics/블랙홀-안에서는-어떤-일이-벌어질까/
motivation:
draft: true
---

<a href="https://horizon.kias.re.kr/wp-content/uploads/2019/09/main_rev.jpg" class="imglink"><img width="640" alt="" src="../figures/sr2bh-main.jpg" class="center"></a>

일반 상대성 이론에 따르면 블랙홀 내부에는 <em class="emkorean">일반 상대성 이론이 더 이상 타당하지 않은 "특이점''이 있다</em>고 예측된다. "우주 검열 가설''로 통칭되는 일반 상대성 이론의 여러 가설은 바로 블랙홀과 특이점의 구조에 관한 추측이다.

블랙홀에 관한 이런 질문은 수학적으로 잘 정의된, 매우 중요하고 흥미로운 문제이기도 하다.
일반 상대성 이론의 핵심 방정식인 아인슈타인 중력장 방정식은 편미분방정식의 일종으로, 일반 상대성 이론의 "특이점''은 결국 <em class="emkorean">아인슈타인 중력장 방정식에 대한 초기값 문제의 유일한 해를 더 이상 확장시킬 수 없는 경계</em>로 표현될 수 있다. "우주 검열 가설''은 결국 이 편미분방정식의 초기값 문제의 해의 성질에 관한 추측이다.

첫 번째 글에서는 특수 상대성 이론에서 시작해, 일반 상대성 이론과 블랙홀의 개념을 설명하고자 한다.

### 갈릴레이의 상대성 원리

상대성 원리는 다음과 같이 요약된다.

>**모든 "물리 법칙''은 모든 "등속으로 움직이는 관찰자''에 대해 동일하게 기술된다.**

이런 관찰자가 재는 시간 \\(t\\) 및 공간 좌표 \\((x,y,z)\\)
를 "관성계''라고 한다.

이 상대성원리를 뉴턴 역학에 적용한 것을 갈릴레이 상대성이라고 한다.
갈릴레이 상대성 원리에 따르면 한 관성계 \\((t,x,y,z)\\)와 이에 대해 속도 \\(V=(V_x, V_y, V_z)\\)로 움직이는 다른 관찰자에 의해 정의된 관성계 \\((t', x', y', z')\\) 사이에는 (\\((t, x, y, z)=(0, 0, 0, 0)\\)과 \\((t,, x,, y,, z,)=(0, 0, 0, 0)\\)에 해당하는 점이 같은 때) <em class="emkorean">갈릴레이 변환</em>이라고 불리는 간단한 관계가 있다:

\begin{equation}
t'=t, \quad x'=x-V\_x t, \quad y'=y-V\_y t, \quad z'=z-V\_y t.
\end{equation}
(수학에서는 그냥 \\(x-t\\)의 꼴로 쓰지만, 물리에서는 \\(x-vt\\)의 꼴로, 단위가 일치해야 함을 잘 보여준다...)

이에 따르면 관성계 \\((t, x, y, z)\\)에 대해 속도 \\(u\\)로 등속운동하는 물체는, 관성계 \\((t, x, y, z)\\)에 대해 속도 \\(V\\)로 움직이는 관성계 \\((t,, x,, y,, z,)\\)에서는 속도 \\(u-V\\)로 등속운동하는 것으로 보인다.([그림1] 참조) 이는 우리의 일상 생활에서(그리고 뉴턴 역학에서) 익숙한 상황이다.

<figure class="center">
    <a title="https://horizon.kias.re.kr/wp-content/uploads/2019/09/일반일러스트1.jpg" href="" target="_blank" class="imglink"><img width="640" alt="" src="../figures/1-fig1.jpg" class="center"></a>
    <figcaption><span class="pretag">그림 1</span>: 갈릴레이 상대성</figcaption>
</figure>

### 아인슈타인의 특수 상대성 이론

맥스웰 방정식에 따르면 진공에서의 빛의 속력이 모든 관성계에서 일정하다는 명제가 유도된다.
아인슈타인의 특수 상대성 이론은 상대성 원리의 "모든 물리 법칙''에 맥스웰 방정식을 포함시킨 것이다.

맥스웰 방정식에 따를 때, 한 관성계 \\((t, x, y, z)\\)에서 측정한 진공에서의 빛의 속력이 \\(c\\)이면 다른 모든 관성계 \\((t', x', y', z')\\)에서도 빛의 속력은 변함없이 \\(c\\)다. 상대성 원리에 모든 관성계에서 동일한 속력(즉, 진공에서의 빛의 속력)이 있다는 공리를 더 하면 아인슈타인의 특수 상대성 이론 (1905)에 다다른다.

<figure class="center">
    <a title="" href="https://horizon.kias.re.kr/wp-content/uploads/2019/09/일반일러스트2.jpg" target="_blank" class="imglink"><img width="640" alt="" src="../figures/1-fig2.jpg"></a>
    <figcaption><span class="pretag">그림 2</span>: 아인슈타인의 특수 상대성</figcaption>
</figure>

### 민코프스키 시공간과 아인슈타인 특수 상대성 이론의 기하학적 기술

아인슈타인의 특수 상대성 이론은 다음과 같은 기하학적 성질로 정리된다.

<em class="emkorean"><span class="pretag">명제:</span> 서로에 대해 등속으로 움직이는 두 관성계 \\((t, x, y, z)\\)와 \\((t', x', y', z')\\)에서 관측한 두 점 \\(P\\), \\(Q\\)를 관측한 좌표값을 각각 \\((t\_P,x\_P,y\_P,z\_P), (t\_Q, x\_Q, y\_Q, z\_Q)\\)와 \\((t'\_P,x'\_P,y'\_P,z'\_P), (t'\_Q, x'\_Q, y'\_Q, z'\_Q)\\)라고 할 때, 다음과 같은 등식이 성립한다:</em>
\begin{align}
\begin{split}
&c^2 (t\_Q-t\_P)^2-(x\_Q-x\_P)^2-(y\_Q-y\_P)^2-(z\_Q-z\_P)^2
\newline
=\,&c^2 (t'\_Q-t'\_P)^2-(x'\_Q-x'\_P)^2-(y'\_Q-y'\_P)^2-(z'\_Q-z'\_P)^2.
\end{split}
\label{eq:1.2}
\end{align}
이 명제는 상대성 원리와 광속 불변위 원리, 그리고 관성계에 대한 몇 가지 가정으로부터 유도할 수 있다. 이에 관해서는 란다우의 고전장론 &sect;1.2를 참고하라.

\eqref{eq:1.2}에서 정의된 양을 두 점 \\(P\\), \\(Q\\) 사이의 시공간 간격(spacetime interval)이라고 한다. 그래서 위 명제를 간단히 표현하면 <em class="emkorean">시공간 간격은 관성계의 변환에 불변</em>이라고 할 수 있다.
유클리드 기하학에서 두 점 \\(p=(x\_p, y\_p, z\_p)\\)와 \\(q=(x\_q, y\_q, z\_q)\\) 사이의 길이의 제곱
\begin{equation}
(x\_p-x\_q)^2 + (y\_p-y\_q)^2 + (z\_p-z\_q)^2
\label{eq:1.3}
\end{equation}
이 직교 좌표계의 변환에 불변인 것(피타고라스의 정리)과 유사하다.
그래서 위 명제는 "기하학적''이다.

<figure class="center">
    <a title="" href="https://horizon.kias.re.kr/wp-content/uploads/2019/09/일반일러스트3.jpg" target="_blank" class="imglink"><img width="640" alt="" src="../figures/1-fig3.jpg"></a>
    <figcaption>
        <span class="pretag">그림 3</span>: 시공간 간격
    </figcaption>
</figure>

유클리드 기하학에서는 위의 성질을 뒤집어서, 3차원 공간과 두 점 사이의 길이의 개념에서 시작해서, 이 3차원 공간을 기술하는 모든 좌표계 \\((x,y,z)\\) 중 길이의 제곱이 \eqref{eq:1.3} 으로 표현되는 좌표계를 직교 좌표계라고 정의해도 무방하다.
마찬가지로 (3+1)--차원 시공간과 두 (시공간) 점 사이의 시공간 간격에서 시작하여, 이 (3+1)--차원 시공간을 기술하는 모든 좌표계 \\((t,x,y,z)\\) 중 시공간 간격이 \eqref{eq:1.2}처럼 표현되는 좌표계를 관성계로 정의할 수 있다. 이것이 바로 민코프스키 시공간의 개념이다.

민코프스키 시공간과 시공간 간격의 개념에서 시작하면 특수 상대성 이론 전체를 유도해낼 수 있다. 예를 들면,

1. 속력 \\(c\\)의 등속으로 움직이는 시공간 궤적 위 두 점의 시공간 간격은 항상 0
인데, 이로부터 모든 관성계에서의 속력 \\(c\\)의 불변성을 간단히 볼 수 있다.
2. 특수 상대성 이론 하에서 (시공간 원점이 같은) 두 관성계 사이의 관계인 로렌츠 변환 또한 시공간 간격이 \eqref{eq:1.2}의 형태로 불변인 모든 선형 변환을 구함으로써 유도할 수 있다.
3. 또한, 서로 다른 관성계에서의 시간과 공간 변화의 관계를 살펴보면 동시성의 상대성, 시간 팽창과 길이 수축 등 특수 상대성 이론의 다른 잘 알려진 결과도 읽어낼 수 있다.

### 쌍둥이 역설, 고유 시간과 민코프스키 계량

시공간 간격의 불변성을 사용해 (특수 상대성 이론이 적용 가능하도록 설계된) "쌍둥이 역설''이라는 예제를 다룬다.
이로부터 고유 시간(proper time)과 민코프스키 계량M(inkowski metric)의 개념이 유도된다.

<em class="emkorean"><span class="pretag">예제</span>: (쌍둥이 역설) 같은 시간에 태어난 쌍둥이 형과 동생을 각각 우주선 \\(A\\), \\(B\\)에 태운다. 우주선 \\(A\\)
는 등속 운동을 하고 있고, 우주선 \\(B\\)가 우주선 \\(A\\)에 대해 등속으로 거리 \\(L\\) 만큼 날아갔다가 다시 등속으로 돌아와 우주선 \\(A\\)와 다시 만났다고 하자. 이때, 두 쌍둥이 중 누가 나이가 더 적은가?</em>

쌍둥이의 상황은 완전히 대칭적이지 않다.
형제가 헤어진 시공간 점을 \\(P\\), 다시 만난 시공간 점을 \\(Q\\), 우주선 \\(B\\)가 회항한 시공간 점을 \\(R\\)이라고 하자.
또, 우주선 \\(A\\)에 탄 형의 입장에서 경과된 시간을 \\(\tau\_A\\),
우주선 \\(B\\)에 탄 동생의 입장에서 경과된 시간을 \\(\tau\_B\\)라 하자.
\\(\tau\_A\\)는 관성계 \\((t, x, y, z)\\)에서 경과된 시간인 \\(t\_Q-t\_P\\)이다.
반면 \\(\tau\_B\\)는 우주선 \\(B\\)가 \\(P\\)에서 \\(R\\)까지 가는 등속운동에 해당하는 관성계 \\((t', x', y', z')\\)에서 경과된 시간 \\(t'\_R-t'\_P\\)와 \\(R\\)에서 \\(Q\\)까지 등속운동에 해당하는 관성계
\\((t^{\prime\prime}, x^{\prime\prime}, y^{\prime\prime}, z^{\prime\prime})\\)에서
경과된 시간 \\(t^{\prime\prime}\_Q-t^{\prime\prime}\_R\\)의 합이다.

<figure class="center">
    <a title="" href="https://horizon.kias.re.kr/wp-content/uploads/2019/09/일반일러스트4.jpg" target="_blank" class="imglink"><img width="640" alt="" src="../figures/1-fig4.jpg"></a>
    <figcaption>
        <span class="pretag"></span>
    </figcaption>
</figure>

이제 우주선 \\(B\\)에서 측정된 시간을 우주선 \\(A\\)에서 측정된 양으로 변환해서 비교한다.
이 변환에 불변량인 시공간 간격 \eqref{eq:1.2}를 이용한다.
\begin{align\*}
c^2 (t^{\prime\prime}\_Q-t^{\prime\prime}\_R)^2&=c^2 (t\_Q-t\_R)^2-L^2,
\newline
c^2 (t'\_R-t'\_P)^2&=c^2 (t\_R-t\_P)^2-L^2.
\end{align\*}

우주선 \\(A\\)와 \\(B\\) 입장에서 경과된 시간은 각각
\\[\tau\_A=t\_Q-t\_P,\quad\tau\_B=(t^{\prime\prime}\_Q-t^{\prime\prime}\_R) + (t'\_R-t'\_P)\\]
이므로, 이를 정리하면:
\begin{align\*}
\tau\_A
&=\sqrt{(t^{\prime\prime}\_Q-t^{\prime\prime}\_R)^2 + \frac{L^2}{c^2}}+ \sqrt{(t'\_R-t'\_P)^2 + \frac{L^2}{c^2}}
\newline
\newline
\tau\_B
&=(t^{\prime\prime}\_Q-t^{\prime\prime}\_R) + (t'\_R-t'\_P)
\end{align\*}

\\(\tau\_A>\tau\_B\\), 즉 우주선 \\(B\\)를 타고 왕복한 쪽이 더 나이가 적다.

이 아이디어를 조금 일반화시키면 여러 가지 의미 있는 결과들을 도출해낼 수 있다. 시공간의 두 점 \\(P\\), \\(Q\\)를 잇는 궤적 \\(\Gamma\\)에 대해, 그 궤적의 입장에서 경과된 시간을 \\(\Gamma\\)의 고유시간(proper time)이라 한다. 쌍둥이 역설의 문제는 결국 \\(P\\), \\(Q\\)를 잇는 직선 궤적 \\(\Gamma\_A\\)와 선분 \\(\overline{PR}\\)과 \\(\overline{RQ}\\) 두 개로 이루어진 궤적 \\(\Gamma\_B\\)의 고유시간을 계산하는 문제다.

위의 접근 방식에 따르면, 점 \\(P\\), \\(Q\\)를 잇는 직선 궤적 \\(\Gamma\_A\\)의 고유시간은 정확히 \\(P\\), \\(Q\\) 사이 시공간 간격의 제곱근이다. 이때 이 제곱근이 양수로 잘 정의되려면 시공간 간격이 양수여야 하는데, 이는 <em class="emkorean">\\(\Gamma\_A\\)의 속력이 \\(c\\)보다 작아야 한다</em>는 자연스런 제한과 동치다. 같은 논리로 모든 관성계는 서로에 대해 \\(c\\)보다 작은 속력으로 운동해야 함을 유도할 수 있다.

<figure class="center">
    <a title="" href="https://horizon.kias.re.kr/wp-content/uploads/2019/09/일반일러스트5_rev.jpg" target="_blank" class="imglink"><img width="640" alt="" src="../figures/1-fig5.jpg"></a>
    <figcaption>
        <span class="pretag">그림 5</span>: 임의의 시간꼴 곡선의 고유시간
    </figcaption>
</figure>

두 개의 선분 \\(\overline{PR}\\)과 \\(\overline{RQ}\\)로 이루어진 궤적 \\(\Gamma\_B\\)의 고유시간은 선분 \\(\overline{PR}\\)과 \\(\overline{RQ}\\)에 해당하는 고유시간의 합이다.
어느 관성계에서나 \\(\Gamma\_B\\)의 고유시간을 간단히 계산할 수 있다.

이 아이디어를 확장하면 유한 개의 선분으로 이루어진 궤적 \\(\Gamma\\)의 고유시간을 계산할 수 있다. 또, 미적분학에서 일반적인 곡선의 길이를 유한 개의 선분으로 근사하여 계산하는 과정을 따라가면 일반적인 시공간의 궤적 \\(\Gamma\\)의 고유시간 \\(\tau\\)도 유한 개의 선분으로 이루어진 궤적 \\(\Gamma'\\)으로 근사하여 계산할 수 있다.(<span class="pretag">그림 5</span> 참조)

이렇게 얻어진 \\(\Gamma\\)의 고유시간 공식은 다음과 같다:
\begin{equation}
\tau=\int\_0^1 \sqrt{-\eta(\dot{\gamma}(s), \dot{\gamma}(s))}\,ds.
\label{eq:1.4}
\end{equation}

이 때 \\(\gamma(s)\\) (\\(s\in[0, 1]\\))은 궤적 \\(\Gamma\\)의 매개변수화이며, \\(\dot{\gamma}\\)은 이를 \\(s\\)로 미분해 얻은 접벡터<sup>tangent vector</sup>이다. 그리고 \\(\eta(\vi v,\vi v)\\)는 민코프스키 계량<sup>Minkowski metric</sup>이라고 불리며, 접벡터 \\(\vi v=(\vi v^0, \vi v^1, \vi v^2, \vi v^3)\\)에 대해 다음과 같이 주어지는 양이다:

\begin{equation}
\eta(\vi v, \vi w) =-c^2 \vi v^0 \vi w^0 + \vi v^1 \vi w^1 + \vi v^2 \vi w^2 + \vi v^3 \vi w^3.
\label{eq:1.5}
\end{equation}

\\(\vi v=\vi w=(t\_{Q}-t\_{P}, x\_{Q}-x\_{P}, y\_{Q}-y\_{P}, z\_{Q}-z\_{P})\\)로 주어질 때, \\(-\eta(\vi v, \vi w)\\)는 점 \\(P\\), \\(Q\\) 사이의 시공간 간격이다.
민코프스키 계량의 중요한 성질이다.

식 \\((1.4)\\)에서 \\(\sqrt{-\eta(\dot{\gamma}(s), \dot{\gamma}(s))}\\)이 양수로 잘 정의되기 위한 조건은 전처럼 \\(\Gamma\\) 위의 각 점에서 순간 속력이 \\(c\\)보다 작아야한다는 자연스런 조건이다. 이런 조건을 만족하는 궤적을 각각 시간꼴 궤적<sup>timelike trajectory</sup>이라고 한다.
이제 식 \\((1.4)\\)를 통해 임의의 (충분히 매끈한) 시간꼴궤적의 고유시간을 계산할 수 있다.

마지막으로, 쌍둥이 역설을 푼 결론 부분의 계산을 일반화하면 점 \\(P\\), \\(Q\\)를 잇는 모든 시간꼴 궤적 중 가장 고유시간이 긴(즉, 나이가 많이 드는) 궤적은 등속 궤적(즉, 직선 궤적)임을 알 수 있다. 이는 유클리드 공간에서 두 점을 최소 길이로 잇는 방법이 직선이라는 명제와 대응되는 민코프스키 시공간의 기하학적 성질이다.
