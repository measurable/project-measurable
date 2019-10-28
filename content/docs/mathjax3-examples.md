---
title: "Mathjax3 예제"
date: 2019-09-11T17:19:10+09:00
categories:
    - sitedoc
tags:
    - mathjax
keywords:
inspired: http://docs.mathjax.org/en/latest/index.html
motivation:
draft: true
---

## 주의할 점:

Hugo의 마크다운 프로세서를 사용할 경우,

- escape: `\*` and `\_`. ex. `\sum\_1^\infty` , `\begin{align\*}`

- `\\` 대신 `\newline` 또는 `\\\\`을 사용한다.
- 인라인 분수 `1/2`, `1/4`, `3/4`:
    - 1/2, \\(1/2\\), 1/4, \\(1/4\\), 3/4, \\(3/4\\)
    - 2/5, \\(2/5\\)
- 수식에서 `<`는 html 엘리먼트 선언으로 해석될 수 있다. 부등호 뒤로 한 칸을 띄우면 된다. 또는, `&lt;`를 써도 mathjax가 인식한다.
- $\LaTeX$ 환경 `\begin{...}` ... `\end{...}`은 math 모드 안팎에서 모두 작동한다. `align*` 환경에 하나의 넘버 태그를 줄 때 유용하다.


\begin{align}
\partial\_\mu F^{\mu\nu}&=\beta J^\nu,
\label{eq:96}
\newline
\partial\_\mu^\ast F^{\mu\nu}&=0.
\label{eq:97}
\end{align}

윗 식 \eqref{eq:96}과 \eqref{eq:97}은 옵션 `tags: 'ams'`에 의해 `align` 환경에서 자동 넘버링된 것.
위 \eqref{eq:96}, \eqref{eq:97}의 환경을 `align\*`으로 바꾸어 `\\[ ..\\]` 안에 넣을 수 있다.
이를 이용하면, 아래 \eqref{eq:99}와 같이 `\tag`와 `\label`을 `align\*`환경 밖에 주어 `\split`를 사용하지 않고 환경 전체에 번호를 할당할 수 있다.

\\[
\begin{align\*}
\partial\_\mu F^{\mu\nu}&=\beta J^\nu,
\newline
\partial\_\mu^\ast F^{\mu\nu}&=0.
\end{align\*}
\tag{99}\label{eq:99}
\\]

단, 자동 넘버링하려면 아래 식 \eqref{eq:split}과 같이 `\split`을 사용해야 한다.


\begin{align}
\begin{split}
\partial\_\mu F^{\mu\nu}&=\beta J^\nu,
\newline
\partial\_\mu^\ast F^{\mu\nu}&=0.
\end{split}
\label{eq:split}
\end{align}



심지어는, `equation` 환경을 math mode에 넣어도 된다.

\\[
\begin{equation}
e^{i\theta}=\cos\theta+i\sin\theta
\end{equation}
\\]

- `\Ket`: 이 매크로는 실행되지 않아야 한다.(`braket` 패키지 `autoload` 차단하고 사용자 매크로 `\ket`로 대체.)

\begin{equation}
\Ket\Psi
\quad\text{vs.}\quad
\ket\Psi
\label{eq:ket}
\end{equation}

$\LaTeX$ 의 경우, 해당 패키지가 로드되지 않으면 윗 식 \eqref{eq:ket}는 컴파일되지 않는다.

### 사용자 매크로


- \\(\psi,\Psi\\) with `\vb`, `\vi`, `\boldsymbol` (i.e. `\bf`, `\boldsymbol`, `\boldsymbol`.)
  + `\vb`: \\(\vb\psi\\), \\(\vb a\\), same as `\bf`: \\(\bf\psi\\), \\(\bf a\\)
  + `\vb`: \\(\vb\Psi\\), \\(\vb A\\), same as `\bf`: \\(\bf\Psi\\), \\(\bf A\\)
  + `\vi`: \\(\vi\psi\\), \\(\vi a\\)
  + `\vi`: \\(\vi\Psi\\), \\(\vi A\\)
  + `\boldsymbol`: \\(\boldsymbol\psi\\), \\(\boldsymbol a\\)
  + `\boldsymbol`: \\(\boldsymbol\Psi\\), \\(\boldsymbol A\\)
\bs
- unit vectors
  + `\uv`: \\(\uv\psi\\), \\(\uv a\\)
  + `\uv`: \\(\uv\Psi\\), \\(\uv A\\)
  + `\ui`: \\(\ui\psi\\), \\(\ui a\\)
  + `\ui`: \\(\ui\Psi\\), \\(\ui A\\)

- `\abs{}`:
\\[
\abs{\sum\_{k=1}^nz\_k}\le\sum\_{k=1}^n\abs{z\_k},
\quad
\abs{\int\_Ef}\le\int\_E\abs f
\tag{삼각부등식}\label{eq:trin}
\\]
- `\norm`:
\begin{align\*}
{\norm x}\_p&=\left(\sum\_{i\in N}\abs{x\_i}^p\right)^{\frac1p}
\tag{$\mathcal l^p$}
\newline
{\norm{f}}\_{p,X}&=\left(\int\_X\abs{f(x)}^pdx\right)^{\frac1p}
\tag{$L^p$}
\end{align\*}
\\[
\norm{\vi L-\sum\_{k=0}^\infty\vi x_k}=0
\tag{completeness}
\\]

- `\bra`, `\ket`:
\\[
\ket{\uparrow\_x}\bra{\downarrow\_y},\quad
\ket{\big\uparrow}\bra{\big\downarrow},\quad
\ket{\Big\uparrow}\bra{\Big\downarrow}.\quad
\ket{\Bigg\uparrow}\bra{\Bigg\downarrow}.
\\]

- `\braket`, `\matrel`, `\expect`:
\\[\Psi(x)=\braket x\Psi
\tag{\braket{}{}}
\\]
\\[
\matrel v{\sum\_{i\in N}\ket{e_i}\bra{e_i}}w
\tag{\matrel{}{}{}}
\\]
\\[
\expect P=\matrel{\psi_1}P{\psi_1}
\tag{\expect{}}\\]

- `\grad`, `\divergence{}`, and `\curl`:
\\[
\grad f=\frac{\partial f}{\partial x\_i}g^{ij}\vb e_j
\\]
