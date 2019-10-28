---
title: "1.1.3. Justification of Complex Number"
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

# Justification of \\(\mathbb C\\) as a Number System (Ahlfors 1.3 )

사칙연산에 관한 실수의 모든 법칙을 보존하면서 \\(x^2+1=0\\)의 근을 가지는 수체계가 존재하는가의 문제이다.

 먼저 실수의 성질을 정리하자
 실수는 체의 일종이다. 사칙연산을 자유롭게 할 수 있으며 정역(integral domain)인 집합을 체라고 한다. 그러므로 실수를 정의한다는 것은 체의 조건을 만족한다는 존제 하에 실수의 성질 중에서 실수를 유일하게 특정할 수 있는 속성들만을 골라내면 된다.

### 실수는 완비순서체이다

체 \\(\mathbb R\\)에 순서를 준다. \\(\mathbb R\\)의 부분집합으로 양수의 집합 \\(\mathbb R^+\\)를 정의하면,  이 \\(\mathbb R^+\\)를 이용해서 순서를 정의할 수 있다.

양수의 집합 \\(\mathbb R^+\\)를 정의하기 위해서는 양수의 집합이 가져야 할 성질을 구성하면 된다. \\(\mathbb R^+\\)는 다음과 같은 성질을 갖는다:

\begin{equation}
0\not\in\mathbb R^+
\label{eq:rplus1}
\end{equation}
\begin{equation}
\alpha\ne0\implies\alpha\in\mathbb R^+\text{ or }-\alpha\in\mathbb R^+
\label{eq:rplus2}
\end{equation}
\begin{equation}
\alpha,\beta\in\mathbb R^+\implies\alpha+\beta,\alpha\beta\in\mathbb R^+
\label{eq:rplus3}
\end{equation}

위의 조건들을 이용해서 \\(\alpha\\)와 \\(-\alpha\\)가 동시에 \\(\mathbb R^+\\)에 속할 수 없다는 것을 보일 수 있다.
또, 두 음수의 합이 음수이고 곱은 양수라든가 음수와 양수의 곱이 음수라는 사실 등도 보일 수 있다.

이제 양수를 이용해서 순서를 정의할 수 있다.
\\[
\alpha<\beta\iff(\beta-\alpha)\in\mathbb R^+
\\]

순서와 \\(\mathbb R^+\\)의 성질을 이용해서 부등식을 다루기 위한 모든 법칙들을 유도할 수 있으며, 모든 \\(\alpha\in\mathbb R\\)에 대하여 \\(\alpha^2=0\\) 또는 \\(\alpha^2\in\mathbb R^+\\) 임을 보일 수 있다. \\(1^2=1\\)은 그래서 양수이다.

순서관계 때문에 \\(\mathbb R\\)은 자연수를 포함하며, 체이므로 모든 유리수로 이루어진 부분체를 갖는다.

마지막으로 \\(\mathbb R\\)에 완비 조건을 준다.
순서관계를 이용해서 유계인 단조증가열을 정의할 수 있고, 여기에 최소상계공리를 주면 된다.

이와 같은 조건을 만족하는 체 \\(\mathbb R^+\\)가 존재하며 유일하다는 것(up to isomorphism)을 보일 수 있다.
이 \\(\mathbb R\\)을 실수라고 한다.

임의의 실수 \\(\alpha\\)에 대하여 \\(\alpha^2+1>0\\)
이므로 방정식 \\(x^2+1=0\\)은 실근을 갖지 않는다.
\\(\mathbb R\\)를 부분체로 포함하며 방정식 \\(x^2+1=0\\)의 해를 갖는 체 \\(\mathbb F\\)가 존재한다고 가정하자.
이 해를 \\(i\in\mathbb F\\)라고 하면 \\(x^2+1=(x+i)(x-i)\\)이므로 \\(\mathbb F\\)에서 이 방정식은 두개의 근 \\(i,-i\\)를 갖는다.
이제 \\(\mathbb F\\)의 부분집합 \\(\mathbb C\\)가 \\(\alpha+i\beta,\ \forall\alpha,\beta\in\mathbb R\\)의 꼴로 나타낼 수 있는 \\(\mathbb F\\)의 원소 전체의 집합이라고 하자.
이 표현이 유일하다는 것은 다음과 같이 보일 수 있다:

\\(\alpha+i\beta=\alpha'+i\beta'\\)이면 \\(\alpha-\alpha'=-i(\beta-\beta')\\)이므로
\\((\alpha-\alpha')^2=-(\beta-\beta')^2\\)이다.
그래서 \\(\alpha=\alpha'\\)이고 \\(\beta=\beta'\\)이다.(증명끝)

\\(\mathbb C\\)가 \\(\mathbb F\\)의 부분체임을 보이는 것은 어렵지 않다.
또, \\(\mathbb C\\)의 대수적 구조가 \\(\mathbb F\\)에 의존하지 않음은 다음과 같이 보일 수 있다:

\\(\mathbb R\\)을 포함하고 방정식 \\(x^2+1=0\\)의 해 \\(i'\\)을 갖는 체 \\(\mathbb F'\\)가 존재한다고 가정하고, \\(\mathbb C'\\)가 \\(\alpha+i'\beta,\ \forall\alpha,\beta\in\mathbb R\\)인 모든 원소를 포함하는 \\(\mathbb F'\\)의 부분체라고 하자.
\\(\mathbb C\\)와 \\(\mathbb C'\\) 사이에는 \\(\alpha+i\beta\\)와 \\(\alpha+i'\beta\\)를 대응시키는 일대일 대응이 존재하고 이것은 분명히 체동형사상(field isomorphism)이다.\\(\Box\\)

\\(\mathbb C\\)가 \\(\mathbb F\\)의 구조에 무관하므로 이제 위와 같은 조건을 만족하는 체 \\(\mathbb F\\)가 존재함을 보이면 복소수체 \\(\mathbb C\\)를 정의할 수 있다.

체 \\(\mathbb F\\)를 구성하는 방법은 많다.
다음 방법이 가장 간단하다.

모든 실수 \\(\alpha,\beta\\)에 대한 표현 \\(\alpha\oplus\mathbf i\beta\\)의 집합을 만들고, 그 원소들 사이의 두 연산을 다음과 같이 정의한다.

\begin{align\*}
&(\alpha\oplus\mathbf i\beta)+(\alpha'\oplus\mathbf i\beta')
=(\alpha+\alpha')\oplus\mathbf i(\beta+\beta'),\newline
&(\alpha\oplus\mathbf i\beta)(\alpha'\oplus\mathbf i\beta')
=(\alpha\alpha'-\beta\beta')\oplus\mathbf i(\alpha\beta'+\beta\alpha')
\end{align\*}

이 집합을 \\(\mathbb F\\)라 하면 이 연산에 대하여 \\(\mathbb F\\)는 체이고,
표현 \\(\alpha\oplus\mathbf i0\\)전체로 이루어진 집합은 \\(\mathbb R\\)과 동형인 부분체이다.
그래서 \\(\alpha\oplus\mathbf i0\\)는 \\(\alpha\\)로 나타낼 수 있고, \\(\mathbb F\\)의 원소 \\(0+\mathbf i1\\)은 방정식 \\(x^2+1=0\\)을 만족한다.
이제 체 \\(\mathbb F\\)는 필요한 조건을 모두 만족한다.
\\(0+\mathbf i1\\)을 \\(i\\)로 나타내면
\\[
\alpha+i\beta
=(\alpha\oplus\mathbf i0)+(0\oplus\mathbf i1)(\beta\oplus\mathbf i0)
\\]
라고 쓸 수 있으므로 \\(\mathbb C\\)는 \\(\mathbb F\\)의 부분체이다.

사실, \\(\mathbb F\\)는 \\(\mathbb C\\)와 같다.

---

또는, 표현을 \\((\alpha,\beta)\\)로 써서 해도 된다.
실수의 순서쌍 \\((\alpha,\beta)\\) 전체의 집합에 대하여, 원소들 사이의 연산을 다음과 같이 정의한다.

\begin{align\*}
&(\alpha,\beta)+(\alpha',\beta')
=(\alpha+\alpha',\beta+\beta'),\newline
&(\alpha,\beta)(\alpha',\beta')
=(\alpha\alpha'-\beta\beta',\alpha\beta'+\beta\alpha')
\end{align\*}

이 집합을 \\(\mathbb F\\)라 하면 이 연산에 대하여 \\(\mathbb F\\)는 체이고,
표현 \\((\alpha,0)\\)전체로 이루어진 집합은 \\(\mathbb R\\)과 동형인 부분체이다.
그래서 \\((\alpha,0)\\)는 \\(\alpha\\)로 나타낼 수 있고, \\(\mathbb F\\)의 원소 \\((0,1)\\)은 방정식 \\(x^2+1=0\\)을 만족한다.
이제 체 \\(\mathbb F\\)는 필요한 조건을 모두 만족한다.
\\((0,1)\\)을 \\(i\\)로 나타내면
\\[
\alpha+i\beta
=(\alpha,0)+(0,1)(\beta,0)
\\]
라고 쓸 수 있으므로 \\(\mathbb C\\)는 \\(\mathbb F\\)의 부분체이다.

---


>연습

1. \\(\begin{pmatrix}
\ \ \alpha&\beta\newline
-\beta&\alpha
\end{pmatrix}\\)
(단, \\(\alpha,\beta\\)는 실수)
의 꼴인 모든 행렬의 집합이 행렬 덧셈과 곱셈에 대하여 복소수체 \\(\mathbb C\\)와 동형임을 보여라.

2. 다항식 \\(x^2+1\\)을 법으로 하는 모든 실계수 다항식의 체가 \\(\mathbb C\\)와 동형임을 보여라.
