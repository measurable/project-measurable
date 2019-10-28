---
title: "Ahlfors 2 3 1"
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


# 2.3. 지수함수와 삼각함수

실수 위에서 지수함수와 삼각함수 사이의 관계를 포착하기는 어렵지만, 테일러 전개의 유사성에 주목해서 허수 \\(i\\)를 적절히 활용하면 오일러 공식 \\(e^{ix}=\cos x+i\sin x\\)을 formal identity로 유도할 수는 있다.
그것이 가지는 의미를 완전하게 분석한 것은 가우스였다.

\\(e^z\\), \\(\cos z\\) 및 \\(\sin z\\)를 정의하고 이들 사이의 관계를 도출한다.
또, 로그함수를 지수함수의 역함수로 정의하고, 로그를 이용해서 복소수의 편각을 정의한다. 그렇게 해서 각의 비기하적인 정의가 만들어진다.

## 2.3.1. 지수 The Exponential

지수함수를 다음 미분방정식의 해로 정의한다.
\\[
f'(z)=f(z),\ \ f(0)=1
\\]
멱급수 표현
\\[\begin{align}
f(z)&=a_0+a_1z+a_2z^2+\cdots+a_nz^n+\cdots\newline
f'(z)&=a_1+2a_2z+3a_3z^2\cdots+na_nz^{n-1}+\cdots\newline
\cdots
\end{align}\\]
에서 계수 사이의 관계 \\(a_{n-1}=na_n\\)를, 그리고 초기조건에서 \\(a_0=1\\)를 얻는다.
여기에 귀납법을 적용하면 \\(a_n=1/n!\\)이다.

이 해를 \\(e^z\\)로 나타내면,
\\[
e^z=1+\frac{z}{1!}+\frac{z^2}{2!}+\cdots+\frac{z^n}{n!}+\cdots
\tag{21}\\]
이다. 이 급수가 수렴함을 보여야 한다. \\((n!)^{1/n}\to\infty\\)를 이용한다.

정의에 사용된 미분방정식의 결과로 다음 합의 정리를 얻는다.
\\[
e^{a+b}=e^ae^b
\\]

이 정리에 의해 \\(e^ze^{-z}=1\\)이고, 이 결과는 임의의 \\(z\\)에 대해 \\(e^z\\)가 \\(0\\)이 아니라는 사실을 의미한다.
전개식 \\((21)\\)은 양의 실수 \\(x\\)에 대해 \\(e^x>1\\)임을 보여준다.
\\(e^x\\)와 \\(e^{-x}\\)는 서로의 역수이므로 \\(x<0\\)일 때는 \\(0<e^x<1\\)이다.
급수가 실계수만을 가지므로 \\(\exp \bar z\\)는 \\(\exp z\\)의 켤레복소수다. 그래서
\\[
\left|e^{iy}\right|^2=e^{iy}e^{-iy}=1,\quad\left|e^{x+iy}\right|=e^x
\\]
이다.
따라서, \\(\left|e^z\right|=1\\)이면 \\(x=0\\)이고 \\(z=iy\\)이다.

## 2.3.2 삼각함수

삼각함수는 다음과 같이 정의한다.
\\[
\cos z=\frac{e^{iz}+e^{-iz}}{2},\quad\sin z=\frac{e^{iz}-e^{-iz}}{2i}
\tag{23}\\]
\\((21)\\)에 대입해서 다음 급수 전개를 얻는다.
\\[\begin{align}
\cos z=1-\frac{z^2}{2!}+\frac{z^4}{4!}-\cdots\newline
\sin z=z-\frac{z^3}{3!}+\frac{z^5}{5!}-\cdots
\end{align}\\]
\\((23)\\)으로부터 다음 관계들을 얻는다.
\\[
e^{iz}=\cos z+i\sin z
\\]
\\[
\cos^2z+\sin^2z=1
\\]
\\[
D\cos z=-\sin z,\quad D\sin z=\cos z
\\]
합의 공식
\\[\begin{align}
\cos(a+b)&=\cos a\cos b-\sin a\sin b\newline
\sin(a+b)&=\cos a\sin b+\sin a\cos b\newline
\end{align}\\]
는 \\((23)\\)과 지수함수의 합의 정리로부터 얻는다.
\\(\tan z,\cot z,\sec z,\csc z\\) 등의 다른 삼각함수들은 \\(\sin z\\)와 \\(\cos z\\)를 이용해서 통상적인 방법으로 정의도니다. 결국 모든 삼각함수는 \\(e^{iz}\\)의 분수함수이다.
