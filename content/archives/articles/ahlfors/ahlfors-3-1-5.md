---
title: "Ahlfors 3 1 5"
date: 2019-10-25T09:08:33+09:00
categories:
    - 방법
tags:
    - Ahlfors
keywords:
inspired:
motivation: ""
draft: true
---


# 3.1.5 연속함수

사상 \\(f:S\to S'\\)이 있을 때,
\\(X\subset S\\)에 대하여 \\(f(X)\\)를 \\(f\\)에 의한 \\(X\\)의 상image이라고 하고,
\\(X'\subset S'\\)에 대하여 \\(f^{-1}(X')\\)을 \\(X'\\)의 역상inverse image이라고 한다.
\\(f\left(f^{-1}\left(X'\right)\right)\subset X'\\)이고 \\(f^{-1}\left(f(X)\right)\supset X\\)이다.

다음 characterization은 연속함수의 정의로부터 바로 나오는 결과다.

- 모든 열린집합의 역상이 열린집합인 것은 함수가 연속이기 위한 필요충분조건이다.

- 모든 닫힌집합의 역상이 닫힌집합인 것은 함수가 연속이기 위한 필요충분조건이다.

함수가 \\(S\\) 전체에서 정의되지 않은 경우,
역상이 열려있다는 것과 닫혀있다는 것은 정의역 위에서의 상대적인 의미로 해석되어야 한다.

\\(\mathbb R\\)에서 \\(\mathbb R\\)로 가는 사상 \\(\displaystyle f(x)=\frac{x^2}{1+x^2}\\)의 경우,
상 \\(f(\mathbb R)=\{y\mid0\le y<1\}\\)은 open도 closed도 아니다. 닫힌 상이 아닌 이유는 \\(\mathbb R\\)가 컴팩트하지 않기 때문이다.

(정리 8).
컴팩트한 집합의 연속사상에 의한 상은 컴팩트하고, 그래서 닫혀있다.

(따름정리).
컴팩트한 집합 위의 연속인 실가함수는 최대값과 최소값을 가진다.

(정리 9).
연결집합의 연속사상에 의한 상은 연결집합이다.

사상 \\(f:S\to S'\\)이 전단사이고 \\(f\\)와 \\(f^{-1}\\)이 모두 연속이면 \\(f\\)를 위상사상topological mapping 또는 위상동형사상homeomorphism\\({}\\)이라고 한다.
집합의 어떤 성질이 위상동형사상에 의해 보존되는 경우, 이 성질을 위상적 성질topological property\\({}\\)이라고 한다.
정리 8.과 정리 9.는 컴팩트성과 연결이 위상적 성질임을 보여준다.
열린 부분집합이기 위한 설질은 위상적 성질이 아니다.
\\(X\subset S\\), \\(Y\subset S'\\)이고 \\(X\\)가 \\(Y\\)와 위상동형일 경우에도 \\(X\\)와 \\(Y\\)가 동시에 열린집합이어야 할 이유는 없다.
만일 \\(S=S'=\mathbb R^n\\)(영역불변invariance of the region)이면 둘 다 열린집합이긴 하지만 이와 관련된 정리는 여기서는 필요 없다.

균등연속uniform continuity 개념은 계속 사용된다.
일반적으로, 어떤 조건이 어떤 매개변수에 관해 균등하게 성립한다는 말은 조건을 그 매개변수에 의존하지 않는 부등식으로 나타낼 수 있다는 의미다.
그래서, 임의의 \\(\epsilon>0\\)에 대하여 \\(\delta>0\\)이 존재해서 다음 조건
\\[
d(x_1,x_2)<\delta\implies d'\left(f(x_1),f(x_2)\right)<\epsilon
\\]
이 성립하면 \\(f\\)는 균등연속이다.
\\(\delta\\)가 \\(x_1\\)에 의존하지 않는다는 사실이 핵심이다.

(정리 10).
컴팩트한 집합 위의 연속함수는 균등연속이다.

컴팩트하지 않은 집합 위의 연속함수는 균등연속인 것도 있고 아닌 것도 있다.
함수 \\(z\\)는 복소평면 전체에서 균등연속이지만 \\(z^2\\)은 그렇지 않다.
