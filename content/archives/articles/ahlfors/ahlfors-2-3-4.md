---
title: "Ahlfors 2 3 4"
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


# 2.3.4. 복소로그

...

마지막으로, 다음 방정식에서 얻어지는 inverse cosine을 다룬다.
\\[
w=\cos z=\frac{1}{2}\left(e^{iz}+e^{-iz}\right)
\\]
이것은 \\(e^{iz}\\)에 관한 이차방정식
\\[
\left(e^{iz}\right)^2-2w\left(e^{iz}\right)+1=0
\\]
이며, 근은 다음과 같다.
\\[
e^{iz}=w\pm\sqrt{w^2-1}
\\]
따라서,
\\[
z=\mathrm{arc}\cos w=-i\log\left(w\pm\sqrt{w^2-1}\right)
\\]
그런데 \\(w\pm\sqrt{w^2-1}\\)이 서로의 역수이므로 다음과 같이 쓸 수 있다.
\\[
\mathrm{arc}\cos w=\pm i\log\left(w+\sqrt{w^2-1}\right)
\\]
\\(\mathrm{arc}\cos w\\)의 값이 무수히 많은 것은 \\(\cos z\\)가  우함수이며 주기함수이기 때문이다.
inverse sine은 다음과 같이 정의하는 것이 가장 쉽다.
\\[
\mathrm{arc}\sin w=\frac{\pi}{2}-\mathrm{arc}\cos w
\\]

주목할 것은,
복소해석함수의 이론에서 모든 기본 초월함수는 \\(e^z\\)와 그 역함수인 \\(\log z\\)로 나타낼 수 있다는 점이다.
다시말해서, 본질적으로 오직 한개의 기본 초월함수만이 존재한다.
