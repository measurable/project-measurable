---
title: "IIT 3.0 - Supplemetary Methods (mathjax example)"
date: 2019-09-11T18:33:46+09:00
categories:
    - 표현
tags:
    - neuro
    - paper
    - Dehane
    - iit
    - construction
keywords:
inspired: https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1003588
motivation:
draft: true
---

## Cause-Effect Repatoire, Unconditioned Repatoire, and Partitions

### 결과분포 Effect Repatoire

결과분포 \\(p(ABC^f\mid A^C=1)\\)는 \\(A\\)의 현재 상태를 \\(1\\)로 고정하고 나머지 요소 \\(B\\)와 \\(C\\)를 가능한 모든 상태로 섭동해서 계산한다. 즉,
\\[
p\left(ABC^f\mid A^C=1\right)=
\sum\_{BC^C\_V}p\left(ABC^f\mid A^C=1,BC^C\_V\right)p^\text{per}\left(BC^C\_V\right)
\\]

여기서도 \\(B\\) 또는 \\(C\\)로부터의 공통 입력이 \\(A^f\\), \\(B^f\\)와 \\(C^f\\) 상관을 발생시킬 수 있다.
이 상관관계를 요소 \\(A\\)의 효과로 계산하는 것을 방지하기 위해서 요소 \\(B\\), \\(C\\)를 모든 요소에 대해 독립적인 출력을 주는 가상 요소로 대체해야 한다.

고려하는 메커니즘은 모두 조건부 독립으로 가정하므로 결과분포의 실제 계산은 다음 공식을 이용할 수 있다.

\begin{equation}
p\left(ABC^f\mid A^C=1\right)=
p\left(A^f\mid A^C=1\right)\cdot p\left(B^f\mid A^C=1\right)\cdot p\left(C^f\mid A^C=1\right)
\label{eq:1}
\end{equation}

이 때, 단일 요소의 결과분포는 다음과 같이 얻는다.
요소 \\(A\\)의 경우,

$$
p\left(A^f\mid A^C=1\right)=
\sum\_{BC^C}p\left(A^f\mid A^C=1,BC^C\right)\cdot p^\text{per}\left(BC^C\mid A^C=1\right)
$$

이고, \\(A\\)는 \\(\mathrm{OR}\\)게이트이고 \\(BC^C\\)는 \\(\{00,10,01,11\}\\)의 값을 가질 수 있으므로 다음 표

\begin{equation}
\begin{array}{c|cccc|l}
BC^C\mid A^C=1&00&10&01&11&p^\text{per}\left(BC^C\mid A^C=1\right)=1/ 4\text{ each.}
\newline
\hline
A^f\mid A^C=1&0&1&1&1
\newline
\hline
p\left(A^f=0\mid A^C=1,BC^C\right)&1&0&0&0&p\left(A^f=0\mid A^C=1\right)=1/ 4
\newline
p\left(A^f=1\mid A^C=1,BC^C\right)&0&1&1&1&p\left(A^f=1\mid A^C=1\right)=3/ 4
\end{array}
\label{tab:1}
\end{equation}

를 얻는다. \\(\mathrm{AND}\\) 게이트 \\(B\\)에 대해서는,
$$
p\left(B^f\mid A^C=1\right)=
\sum_{CA^C}p\left(B^f\mid A^C=1,CA^C\right)\cdot p^\text{per}\left(CA^C\mid A^C=1\right)
$$
이고, \\(CA^C\\)는 \\(\{01,11\}\\)의 두 상태를 가질 수 있으므로 다음 표를 얻는다.


\begin{equation}
\begin{array}{c|cc|l}
CA^C\mid A^C=1&01&11&p^\text{per}\left(CA^C\mid A^C=1\right)=1/ 2\text{ each.}
\newline
\hline
B^f\mid A^C=1&0&1
\newline
\hline
p\left(B^f=0\mid A^C=1,CA^C\right)&1&0&p\left(B^f=0\mid A^C=1\right)=1/ 2
\newline
p\left(B^f=1\mid A^C=1,CA^C\right)&0&1&p\left(B^f=1\mid A^C=1\right)=1/ 2
\end{array}
\label{tab:2}
\end{equation}


또, \\(\mathrm{XOR}\\) 게이트 \\(C\\)에 대해서는
\\[
p\left(C^f\mid A^C=1\right)=
\sum_{AB^C}p\left(C^f\mid A^C=1,AB^C\right)\cdot p^\text{per}\left(AB^C\mid A^C=1\right)
\\]
로부터 다음 표를 얻는다.

\begin{equation}
\begin{array}{c|cc|l}
AB^C\mid A^C=1&10&11&p^\text{per}\left(AB^C\mid A^C=1\right)=1/ 2\text{ each.}
\newline
\hline
C^f\mid A^C=1&0&1
\newline
\hline
p\left(C^f=0\mid A^C=1,AB^C\right)&1&0&p\left(C^f=0\mid A^C=1\right)=1/ 2
\newline
p\left(C^f=1\mid A^C=1,AB^C\right)&0&1&p\left(C^f=1\mid A^C=1\right)=1/ 2
\end{array}
\label{tab:3}
\end{equation}

이 표 \eqref{tab:1}, \eqref{tab:2}, \eqref{tab:3}를 이용해서 결과분포 \eqref{eq:1}을 계산할 수 있다.

\begin{equation}
\begin{array}{c|cccccccc|c}
ABC^f&000&100&010&110&001&101&011&111&\text{total}
\newline
\hline
p\left(ABC^f\mid A^C=1\right)&\frac{1}{16}&\frac{3}{16}&\frac{1}{16}&\frac{3}{16}&\frac{1}{16}&\frac{3}{16}&\frac{1}{16}&\frac{3}{16}&1
\end{array}
\end{equation}


**참고**: 가상변수를 도입하지 않고 상관 효과를 그대로 둔 채 계산한 경우에는 다음과 같이 다른 결과를 얻는다.

\begin{equation}
\begin{array}{c|cccccccc|c}
ABC^C\mid A^C=1&&110&&111&&100&&101&
\newline
\hline
ABC^f\mid A^C=1&000&100&010&110&001&101&011&111&\text{total}
\newline
\hline
p\left(ABC^f\mid A^C=1\right)&0&\frac{1}{4}&0&\frac{1}{4}&0&\frac{1}{4}&0&\frac{1}{4}&1
\end{array}
\end{equation}

이와 같은 차이가 나타나는 이유는 뭘까?

### 자유결과분포 Unconstrained Effect Repertore

메카니즘에 의한 제약이 없는 자유결과분포 \\(p^\text{uc}\left(ABC^f\right)\\)는 다음과 같이 정의된다.
$$
p^\text{uc}\left(ABC^f\right)=
\sum\_{ABC^C\_V}p\left(ABC^f\mid ABC^C\_V\right)\cdot p^\text{per}\left(ABC^C\_V\right)
$$
이 경우에도 공통입력으로 인한 상관 효과를 제거하기 위해 가상요소를 이용한다.
메커니즘들이 조건부 독립인 경우, 자유결과분포는 다음 공식을 이용해서 구할 수 있다.

\begin{align\*}
p^\text{uc}\left(ABC^f\right)=
\sum\_{ABC^C}p\left(A^f\mid ABC^C\right)\cdot p^\text{per}\left(ABC^C\right)\\\\\
\times
\sum\_{ABC^C}p\left(B^f\mid ABC^C\right)\cdot p^\text{per}\left(ABC^C\right)\\\\\
\times
\sum\_{ABC^C}p\left(C^f\mid ABC^C\right)\cdot p^\text{per}\left(ABC^C\right)
\end{align\*}

즉,

\\[
p^\text{uc}\left(ABC^f\right)=
\prod\_{X\in\{A,B,C\}}\left[\sum\_{ABC^C}p\left(X^f\mid ABC^C\right)\cdot p^\text{per}\left(ABC^C\right)\right]
\\]

이제 각각의 요소에 대한 자유결과분포를 구해보자.
먼저 계의 \\(ABC^C\\)가능한 모든 상태 각각이 요소 \\(A\\), \\(B\\), \\(C\\) 각각에 주는 결과분포는 다음과 같이 얻어진다.


\begin{equation\*}
\small\begin{array}{c|cccccccc|l}
ABC^C&000&100&010&110&001&101&011&111&p^\text{per}\left(ABC^C\right)=1/ 8\text{ each.}
\newline
\hline
A^f  & 0 & 0 & 1 & 1 & 1 & 1 & 1 & 1&\sum_{ABC^C}p\left(A^f=0\mid ABC^C\right)\cdot p^\text{per}\left(ABC^C\right)=\frac{1}{4}
\newline
&&&&&&&&&\sum\_{ABC^C}p\left(A^f=1\mid ABC^C\right)\cdot p^\text{per}\left(ABC^C\right)=\frac{3}{4}
\newline
\hline
B^f  & 0 & 0 & 0 & 0 & 0 & 1 & 0 & 1&\sum\_{ABC^C}p\left(B^f=0\mid ABC^C\right)\cdot p^\text{per}\left(ABC^C\right)=\frac{3}{4}
\newline
&&&&&&&&&\sum\_{ABC^C}p\left(B^f=1\mid ABC^C\right)\cdot p^\text{per}\left(ABC^C\right)=\frac{1}{4}
\newline
\hline
C^f  & 0 & 1 & 1 & 0 & 0 & 1 & 1 & 0&\sum\_{ABC^C}p\left(C^f=0\mid ABC^C\right)\cdot p^\text{per}\left(ABC^C\right)=\frac{1}{2}
\newline
&&&&&&&&&\sum\_{ABC^C}p\left(C^f=1\mid ABC^C\right)\cdot p^\text{per}\left(ABC^C\right)=\frac{1}{2}
\newline
\hline
\end{array}
\normalsize
\end{equation\*}

이 개별 요소의 결과분포를 이용해서 계의 자유결과분포를 구하면 다음과 같다.

$$\begin{array}{c|cccccccc|c}
ABC^f&000&100&010&110&001&101&011&111&\text{total}
\newline
\hline
p\left(ABC^f\right)
&\frac{3}{32}&\frac{9}{32}&\frac{1}{32}&\frac{3}{32}&\frac{3}{32}&\frac{9}{32}&\frac{1}{32}&\frac{3}{32}&1
\newline
\end{array}$$

로부터

$$\begin{array}{c|cccccccc|c}
ABC^f&000&100&010&110&001&101&011&111&\text{total}
\newline
\hline
p\left(ABC^f\right)&\frac{1}{8}&\frac{2}{8}&0&\frac{1}{8}&\frac{1}{8}&\frac{2}{8}&0&\frac{1}{8}&1
\end{array}$$

**참고**: 이 경우에도, 상관효과를 제거하지 않은 결과는 다음과 같다:
\begin{array}{c|cccccccc|c}
ABC^C&000&100&010&110&001&101&011&111&p^\text{per}\left(ABC^c\right)=1/ 8\text{ each.}
\newline
\hline
ABC^f&000&001&101&100&100&111&101&110
\end{array}
