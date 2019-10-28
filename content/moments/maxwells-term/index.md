---
title: "맥스웰의 추가항"
date: 2019-10-02T21:19:15+09:00
categories:
    - 표현
    - 방법
tags:
    - Maxwell
keywords:
inspired: "S. Hassani, Mathematical Methods for Students of physics and Related Fields, 2nd ed. Springer, 2009. pp. 416--"
motivation: '표현의 발견이 사실의 발견으로 이어지는 전형적인 사례. 그래서 이건 방법의 발견에 해당하는 이야기이기도 하다. 하사니가 정당히게 지적한 것처럼 코페르니쿠스 자신에게서 시작된 이런 패턴은 플랑크의 양자, 디랙의 마이너스 해, 찬드라세카르의 블랙홀 등등으로 이어지게 된다. 모두가 물리적으로 가능하지 않은 기상천외한 결과로 인식되는...
"Mathematics and the force of logic and human reasoning unravel one of the greatest secrets of Nature!" (S. Hassani)
'
draft: false
---

Maxwell's most important achievement was his extension and mathematical formulation of Michael Faraday's theories of electricity and magnetic lines of force. His paper On Faraday's lines of force was read to the Cambridge Philosophical Society in two parts, 1855 and 1856. Maxwell showed that a few relatively simple mathematical equations could express the behavior of electric and magnetic fields and their interrelation.

The four partial differential equations, now known as Maxwell's equations, first appeared in fully developed form in *Treatise on Electricity and Magnetism* (1873). They are one of the great achievements of nineteenth-century mathematical physics. Solving these equations Maxwell predicted the existence of electromagnetic waves and the fact that these waves propagate at the speed of light (1862). He proposed that the phenomenon of light is therefore an electromagnetic phenomenon.

The differential form of the equations is important because it places particular emphasis on the fields which are the primary objects. The differential form of the equations are:

\begin{align}
\begin{split}
\divergence{\vb E}&=\frac\rho{\epsilon\_0},\quad&\curl{\vb E}&=-\frac{\partial\vb B}{\partial t}
\newline
\divergence{\vb B}&=0,\quad&\curl{\vb B}&=\mu\_0\vb J\color{green}+\mu\_0\epsilon\_0\frac{\partial\vb E}{\partial t}.
\end{split}
\label{eq:15.28}
\end{align}

---

*Maxwell discovers the inconsistency of Equation \eqref{eq:15.28}---위의 방정식에서 초록색으로 표시된 부분을 제외한 것---with the conservation of electric charge, and modifies the last equation to resolve the inconsistency.*

Maxwell inherited the four equations in \eqref{eq:15.28}, and started pondering about them in the 1860s.
He noticed that while the second and third are consistent with other aspects of electromagnetism, the other two equations lead to a contradiction.
Let us retrace his argument. By Equation
\begin{equation}
\divergence{(\curl{\vb A})}  =0,
\label{eq:15.5}
\end{equation}
the divergence of the LHS of the last equation of \eqref{eq:15.28} vanishes.
Therefore, taking the divergence of both sides, we get \\(\divergence{\vb J}=0\\).
This contradicts the differential form of the continuity equation for charges which expresses the conservation of electric charge:
\begin{equation}
\frac{\partial\rho\_Q}{\partial t}+\divergence{\vb J}\_Q=0
\label{eq:13.22}
\end{equation}

Because of the firm establishment of the *charge conservation*, Maxwell decided to try altering the four equations to make them compatible with charge conservation. The clue is in the first equation of \eqref{eq:15.28}. If we differentiate that equation with respect to time, we obtain
\begin{align\*}
\frac\partial{\partial t}\divergence{\vb E}=\frac1{\epsilon\_0}\frac{\partial\rho}{\partial t}
&\implies\divergence{\left(\frac{\partial\rho}{\partial t}\right)}=\frac1{\epsilon\_0}\frac{\partial\rho}{\partial t}
\newline
&\implies\divergence{\left(\epsilon\_0\frac{\partial\vb E}{\partial t}\right)}=\frac{\partial\rho}{\partial t}
\end{align\*}
This suggested to Maxwell that, if the four equations are to be consistent with charge conservation, the fourth equation had to be modified to include \\(\epsilon\_0\left(\partial\vb E/\partial t\right)\\).
Hence the complete form of \eqref{eq:15.28}

It was a great moment in the history of physics and mathematics when Maxwell, prompted solely by the forces of logic and pure deduction, introduced the second term(빨강색으로 표시된 항) in the last equation. Such moments were rare prior to Maxwell, and with the exception of Copernicus's introduction of the heliocentric theory of the solar system and Descartes's introduction of analytic geometry, deductive reasoning was the exception rather than the rule. Theories and laws were empirical (or inductive); they were introduced to fit the data and summarize, more or less directly, the numerous observations made. Maxwell broke this tradition and set the stage for deductive reasoning which, after a great deal of struggle to abandon the inductive tradition, became the norm for modern physics.

Today, we aptly call all four equations in \eqref{eq:15.28} Maxwell's equations, although his contribution to those equations was a "mere'' introduction of the second term on the RHS of the last equation. However, no other "small'' contribution has ever affected humankind so enormously. This very "small'' contribution was responsible for Maxwell's prediction of the electromagnetic waves which were subsequently produced in the laboratory in 1887---only eight years after Maxwell's premature death---and put to technological use in 1901 in the form of the first radio. Today, Maxwell's equations are at the heart of every electronic device. Without them, our entire civilization, as we know it, would be nonexistent.