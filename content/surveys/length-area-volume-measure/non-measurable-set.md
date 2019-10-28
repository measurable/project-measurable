---
title: "비가측집합 (Non Measurable Set)"
date: 2019-10-18T22:46:10+09:00
categories:
    - generic
tags:
    - generic
keywords:
inspired: https://www.encyclopediaofmath.org/index.php/Non-measurable_set
motivation: ""
draft: true
---

\\(H(S)\\)를 hereditary \\(\sigma\\)--ring이라 하자.
\\(\sigma\\)--ring \\(S\\)는 measure \\(\mu\\)가 정의되어 있고,
\\(\mu^\ast\\), \\(\mu\_\ast\\)를 각각 \\(S\\)의 exterior measure, interior measure라고 하자.
\\(H(S)\\)에 속한 집합 \\(X\\)에 대하여,
\\[
\mu^\ast(X)>\mu\_\ast(X)
\\]
일 때, 집합 \\(X\\)는 non-measurable set이다.[^nm1]

[^nm1]: 측도에 관해서는 [measure](https://www.encyclopediaofmath.org/index.php/Measure)를 참조. 비가측집합과 바나흐 타르스키 역설과 관련해서는 위키 항목 [non-measurable set](https://en.wikipedia.org/wiki/Non-measurable_set)에 좋은 설명이 있다.

**예**: 단위 사각형 \\(K=\\{(x,y):0\le x\le1,0\le y\le1\\}\\)을 생각하자.
르베그 가측집합 \\(E\\)의 측도를 \\(m(E)\\)라 하고, 집합
\\[
\hat E=\left\\{(x,y):x\in E,0\le y\le1\\right\\}
\\]
의 측도 \\(\mu\\)를 \\(\mu(\hat E)=m(E)\\)로 정의한다.
이 때, 다음 집합 \\(X\\)는 비가측이다.
\\[
X=\left\\{(x,y):0\le x\le1,y=\frac12\right\\}
\\]
\\(X\\)의 외측도와 내측도가 각각
\\[
\mu^\ast(X)=1.\quad\mu\_\ast(X)=0
\\]
이다.


