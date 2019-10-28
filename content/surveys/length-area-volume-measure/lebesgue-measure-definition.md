---
title: "Lebesgue Measure: 정의"
date: 2019-10-19T19:18:17+09:00
categories:
    - generic
tags:
    - generic
keywords:
inspired: https://ko.wikipedia.org/wiki/르베그_측도
motivation: ""
draft: true
---

The Lebesgue measure, named after French mathematician Henri Lebesgue, is the standard way of assigning a measure to subsets of \\(n\\)--dimensional Euclidean space. For \\(n = 1, 2,  3\\), it coincides with the standard measure of length, area, or volume.
Sets that can be assigned a Lebesgue measure are called Lebesgue--measurable; the measure of the Lebesgue--measurable set \\(A\\) is here denoted by \\(\lambda(A)\\).

Henri Lebesgue described this measure in the year 1901, followed the next year by his description of the Lebesgue integral. Both were published as part of his dissertation in 1902.

## 정의

실수의 구간 \\(I=(a,b)\\)(또는 \\(I=[a,b]\\))의 길이가 \\(l(I)=b-a\\)로 주어질 때, 집합 \\(E\subset\vb R\\)의 르베그 외측도 \\(\lambda^\ast(E)\\)를 다음과 같이 정의한다.

\\[
\lambda^\ast(E)=\inf\left\\{\sum\_{k=1}^\infty l(I\_k):E\subset \bigcup\_{k=1}^\infty I\_k\right\\}
\\]

르베그 측도는 르베그 [\\(\sigma\\)--대수](https://en.wikipedia.org/wiki/Sigma-algebra) 위에서 다음과 같이 정의된다.
\\[
\lambda(E)=\lambda^\ast(E)
\\]

르베그 [\\(\sigma\\)--대수](https://en.wikipedia.org/wiki/Sigma-algebra)는 [Carathéodory criterion](https://en.wikipedia.org/wiki/Carath%C3%A9odory%27s_criterion)이라 불리우는 다음 조건
\\[
\lambda^\ast(A)=\lambda^\ast(A\cap E)+\lambda^\ast(A\cap E^c),\ \forall A\subset\vb R
\\]
을 만족하며, \\(\mathcal P(\vb R)\\)의 진부분집합이다.
즉, 실수의 부분집합 중 르베그 [\\(\sigma\\)--대수](https://en.wikipedia.org/wiki/Sigma-algebra)에 속하지 않는 집합이 존재하며, 이 집합은 르베그 비가측이다.

이 부분을 좀 더 자세히 알아보자.
르베그 외측도의 기본적인 아이디어는 집합 \\(E\\)를 포함하는 구간열 길이의 infimum이다.

이 아이디어에 의하면 유리수 집합의 외측도가 0임을 보일 수 있다.(실은 실수의 모든 가산부분집합의 르베그 외측도는 0임?)
유리수 집합은 가산이므로, 유리수를 \\(q\_i\\), \\(i\in\vb N\\)으로 나타내고, 각각의 유리수 \\(q\_i\\)를 구간 \\([q\_i-2^{-i}\epsilon,q\_i+2^{-i}\epsilon]\\)으로 덮자.
이 덮개들 길이의 합은 \\(2\epsilon\sum\_{i=1}^\infty2^{-i}=4\epsilon\\)이므로, infimum은 0이다.

그러나 이 외측도를 항상 르베그 측도로 정의할 수 있는 것은 아니다.
그 가능성은 [Carathéodory criterion](https://en.wikipedia.org/wiki/Carath%C3%A9odory%27s_criterion)에 의해 결정된다.[^lbg1]

[^lbg1]: The Carathéodory criterion is of considerable importance because, in contrast to Lebesgue's original formulation of measurability, which relies on certain topological properties of \\(\vb R\\), this criterion readily generalizes to a characterization of measurability in abstract spaces. Indeed, in the generalization to abstract measures, this theorem is sometimes extended to a definition of measurability. Thus, we have the following definition: Let \\(\mu^\ast\\) be an outer measure on a set \\(X\\). Then \\(E\subset X\\) is called \\(\mu^\ast\\)--measurable if for every \\(A\subset X\\), the equality \\(\mu^\ast(A)=\mu^\ast(A\cap E)+\mu^\ast(A\cap E^c)\\) holds.







[Carathéodory criterion](https://en.wikipedia.org/wiki/Carath%C3%A9odory%27s_criterion)은 \\(E\\)가 다른 집합의 측도에 대해 어떤
임의의 집합 \\(A\\)에 대하여 \\(E\\)를 그 집합을 둘로 분할하는 기준으로 사용하는 거다.



That characterizes the Lebesgue outer measure. Whether this outer measure translates to the Lebesgue measure proper depends on an additional condition. This condition is tested by taking subsets {\displaystyle A}A of the real numbers using {\displaystyle E}E as an instrument to split {\displaystyle A}A into two partitions: the part of {\displaystyle A}A which intersects with {\displaystyle E}E and the remaining part of {\displaystyle A}A which is not in {\displaystyle E}E: the set difference of {\displaystyle A}A and {\displaystyle E}E. These partitions of {\displaystyle A}A are subject to the outer measure. If for all possible such subsets {\displaystyle A}A of the real numbers, the partitions of {\displaystyle A}A cut apart by {\displaystyle E}E have outer measures whose sum is the outer measure of {\displaystyle A}A, then the outer Lebesgue measure of {\displaystyle E}E gives its Lebesgue measure. Intuitively, this condition means that the set {\displaystyle E}E must not have some curious properties which causes a discrepancy in the measure of another set when {\displaystyle E}E is used as a "mask" to "clip" that set, hinting at the existence of sets for which the Lebesgue outer measure does not give the Lebesgue measure. (Such sets are, in fact, not Lebesgue-measurable.)