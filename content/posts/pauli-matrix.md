---
title: "Pauli Matrix (mathjax example)"
date: "2019-08-31T18:03:43+09:00"
categories:
    - 표현
tags:
    - 물리
    - qm
motivation:
draft: true
---

## 파울리 행렬

다음 행렬을 파울리 행렬이라고 한다.

\\[
\sigma_z=
    \begin{pmatrix}
        1&0\newline
        0&-1
    \end{pmatrix},\quad
\sigma_x=
    \begin{pmatrix}
        0&1\newline
        1&0
    \end{pmatrix},\quad
\sigma_y=
    \begin{pmatrix}
        0&-i\newline
        i&0
    \end{pmatrix}
\\]

\\(\ket u\\), \\(\ket d\\)를 표준기저로 하자.
\\[\begin{align}
\ket u=
    \begin{pmatrix}
        1\newline
        0
    \end{pmatrix},
\quad
\ket d=
    \begin{pmatrix}
        0\newline
        1
    \end{pmatrix}
\end{align}
\\]
파울리 행렬은 다음 관계를 준다.
\\[\begin{align}
\sigma_z\ket u&=\ket u,&\quad\sigma_z\ket d&=-\ket d,\newline
\sigma_x\ket u&=\ket d,&\quad\sigma_x\ket d&=\ket u,\newline
\sigma_y\ket u&=i\ket d,&\quad\sigma_y\ket d&=-i\ket u
\end{align}\\]
