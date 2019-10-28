---
title: "html <div>를 이용한 theorem 환경"
date: 2019-09-22T01:48:37+09:00
categories:
    - generic
tags:
    - mathjax
keywords:
inspired:
motivation:
draft: true
---

환경을 `<div>`로 묶으니까 번거로운 점이 나타나는데,
아래 "*convex*"에서 나타나듯이,

- 마크다운 태그가 안먹고,
- mathjax 수식을 이스케이프 시키지 않아야 한다.
    +  math delimiter는 `$` 와 `$$` 를 사용하고,
    +  `\_`와 `\*`는 이스케이프 시키지 않고 `_`, `*`처럼 네이키드로 써야.

test of *emph*'d *convex* ...

<div class="definition">
A set $C$ is *convex* if for all
$x,y \in C$ and for all
$\alpha \in [0,1]$ the point
$\alpha x + (1-\alpha) y \in C$.
</div>

<div class="definition">
임의의 \(x,y\in C\)와
임의의 \(\alpha\in[0,1]\)에 대하여
\(\alpha x+(1-\alpha)y\in C\)일 때,
\(C\)는 <em class="emkorean">볼록</em>(<em>convex</em>)
 집합이라고 한다.
</div>

<div class="definition">
임의의 $x,y\in C$와
임의의 $\alpha\in[0,1]$에 대하여
$\alpha x+(1-\alpha)y\in C$일 때,
$C$는 <em class="emkorean">볼록</em>(<em>convex</em>)
 집합이라고 한다.
</div>



