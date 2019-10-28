---
title: "mathematical structure란?"
date: 2019-10-04T20:14:44+09:00
categories:
    - 방법
tags:
    - structure
keywords:
inspired: https://arxiv.org/abs/0704.0646
motivation: "Tegmark의 수학적 우주론으로 들어가는 입구에서...: finite structue의 정의와 부호화에 관한 예시적 설명.
유한 구조의 경우는 유한 길이의 정수열로 encoding된다. 무한 구조의 경우에는 알고리즘을 포함해야 한다. 여기서 알고리즘 대신 재귀원리(또는 무한공리)로 해도 될 듯."
draft: true
---

A discussion of mathematical structures at a more technical level.
The mathematics described here falls within the subject known as model theory.
For an introductory textbook on the subject that is reasonably accessible to physicists, see: Hodges W, *A Shorter Model Theory*, 1997 Cambridge Univ. Press, Cambridge.

There are two common ways of introducing mathematical structures:

1. as relations between abstract entities (as in \Sec{HypothesisSec})
2. or via formal systems (as in, \eg, \cite{toe}).

The two are intimately linked: in model theory terminology, 1. is said to be a model of 2.
I have centered the discussion in this paper around 1., both
for pedagogical reasons
and because it is more closely linked to our discussion of issues such as symmetry and computability.

This Appendix is organized as follows:

1. definition of the concept of a mathematical structure,
2. the definition is illustrated with examples of a few simple finite ones.
3. We then give examples of infinite ones, and discuss various subtleties related to units, observability, Gödel--incompleteness and Church--Turing incomputability.

## mathematical structures

We define a  mathematical structure as *a set $S$ of abstract entities and relations $R\_1$, $R\_2$, ... between them*[^f19].
Specifically, let us define the *entities* and *relations* of a mathematical structure as follows:

[^f19]: The mathematical structure definition given here differs from the common one of Hodge's in two ways: (1) It allows multiple types (corresponding to the different sets $S\_i$), much like different data types (Boolean, integer, real, etc.) in a programming language, because this greatly simplifies the definition of more complex structures cropping up in physics. (2) It defines a mathematical structure by *all* its relations. This means that one only needs to specify generators, a finite set of relations that generate all others.

Given a finite number of sets $S\_1$, $S\_2$, ..., $S\_n$,

- the *set of entities* is the union $S=S\_1\cup S\_2\cup\cdots\cup S\_n$,
- the relations are functions on these sets, specifically mappings from some number of sets to a set:
$S\_{i\_1}\times S\_{i\_2}\times \cdots\times  S\_{i\_k}\mapsto S\_j$.

For a Boolean--valued function $R$, (a function whose range $S\_j=\\{0,1\\}$)
we say that "the relation $R$ holds'' for those variables where $R=1$.
Functions that are not Boolean--valued can readily be interpreted as relations as well---for instance,
we say that the relation $R(a,b)=c$ holds if the function $R$ maps $(a,b)$ to $c$.[^20]
A mathematical structure typically has a countably infinite number of relations.
It is defined by

- specifying the entities,
- specifying a finite set of relations ("generating relations''), and
- the rule that composition of any two relations generates a new relation.

This means that there are typically infinitely many equivalent ways of defining a given mathematical structure, the most convenient one often being the shortest.
We say that one mathematical structure definition generates another if its generating relations generate all generating relations of the other, so two structure definitions are equivalent if they generate each other.
There is a simple halting algorithm for determining whether any two finite mathematical structure definitions are equivalent.

[^20]: The reader preferring to start without assuming the definition of a function can begin with Zermelo-Fraenkel set theory alone and define relations as subsets of product sets of the type $S\_{i\_1}\times S\_{i\_2}\times \cdots\times  S\_{i\_k}$. Subsets are equivalent to Boolean functions: one says that the relation $R(a\_1,a\_2,\cdots,a\_n)$ holds (and that the Boolean function $R(a\_1,a\_2,\cdots,a\_n)$ is true) if $(a\_1,a\_2,\cdots,a\_n)\in R$, false otherwise. Non-Boolean functions are definable by interpreting a relation $R$ as an $S\_{i\_k}$-valued function and writing $R(a\_1,a\_2,\cdots,a\_{n-1})=a\_n$ if for any values of the first $n-1$ variables, there is one and only one value $a\_n$ of the last variable such that the relation $R(a\_1,a\_2,\cdots,a\_n)$ is true.

## mathematical structures examples

Let us clarify all of this with a few examples, starting with *finite* mathematical structures (ones where there are only
a finite number of sets $S\_i$ with a finite number of elements).

### example: boolean algebra

This example corresponds to the case of a single set with only two elements, with the generating relations indicated by the following tableaus:

\begin{align}
  \begin{split}
S=\begin{bmatrix}
0
\newline
1
\end{bmatrix},\qquad
&R\_1=&\,\begin{bmatrix}
0
\end{bmatrix},
&R\_2=&\,\begin{bmatrix}
1
\end{bmatrix},
&R\_3=&\,\begin{bmatrix}
1
\newline
0
\end{bmatrix},
&R\_4=&\,\begin{bmatrix}
0&0
\newline
0&1
\end{bmatrix},
\newline
&R\_5=&\,\begin{bmatrix}
0&1
\newline
1&1
\end{bmatrix},\;\;
&R\_6=&\,\begin{bmatrix}
1&1
\newline
0&1
\end{bmatrix},\;\;
&R\_7=&\,\begin{bmatrix}
1&0
\newline
0&1
\end{bmatrix},\;\;
&R\_8=&\,\begin{bmatrix}
1&1
\newline
1&0
\end{bmatrix}.
  \end{split}
\label{eq:boolstr}
\end{align}

The $2\times 2$ boxes specify the values of functions with two arguments analogously to the multiplication
table, and the smaller boxes analogously define functions taking zero or one arguments.
These eight relations are normally denoted by the symbols
$F$, $T$, $\sim$, $\\&$, $\vee$, $\Rightarrow$, $\Leftrightarrow$ and $|$, respectively, and referred to as `false`, `true`, `not`, `and`, `or`, `implies`, `is equivalent to (xor)` and `nand`.

As an illustration of the idea of equivalent definitions, note that
\begin{equation}
S=\begin{bmatrix}
0
\newline
1
\end{bmatrix},\qquad
R=\begin{bmatrix}
1&1
\newline
1&0
\end{bmatrix}.
\label{eq:boolstr2}
\end{equation}
defines the *same* mathematical structure as \eqref{eq:boolstr}. This is because the single relation $R$ ("nand'', also known as Sheffer symbol $|$) generates all the relations of \eqref{eq:boolstr}:
\begin{align\*}
R\_1&=R(R(X,R(X,X)),R(X,R(X,X))),
\newline
R\_2&=R(X,R(X,X)),
\newline
R\_3(X)&=\nonumber R(X,X),
\newline
R\_4(X,Y)&=R(R(X,Y),R(X,Y)),
\newline
R\_5(X,Y)&=R(R(X,X),R(Y,Y)),
\newline
R\_6(X,Y)&=R(X,R(Y,Y)),
\newline
R\_7(X,Y)&=R(R(X,Y),R(R(X,X),R(Y,Y))),
\newline
R\_8(X,Y)&=R(X,Y)
\end{align\*}
or, in more familiar notation,
\begin{align\*}
F&=(X|(X|X))|(X|(X|X)),
\newline
T&=X|(X|X),
\newline
\sim X&= X|X,
\newline
X\\&Y&=(X|Y)|(X|Y),
\newline
X\vee Y&=(X|X)|(Y|Y),
\newline
X\Rightarrow Y&=X|(Y|Y),
\newline
X\Leftrightarrow Y&=(X|Y)|((X|X)|(Y|Y)),
\newline
X|Y&=X|Y.
\end{align\*}
(Note that the parentheses are needed since, whereas $\\&$, $\vee$ and $\Leftrightarrow$
are associative, $|$ is not.)
*Not or* ("nor'') generates the same mathematical structure as "nand''.
Another popular choice of generators for Boolean algebra, employed by Gödel, is using only
$R\_3$ and $R\_5$ ($\sim$ and $\vee$) from \eqref{eq:boolstr}.

Not only the relations of \eqref{eq:boolstr}, but *all* possible Boolean functions of arbitrarily many (not just zero, one or two) variables can be expressed in terms of the Sheffer relation $|$ alone.
This means that the mathematical structure of Boolean algebra is simply all Boolean functions.

This simple example also illustrates why we humans create "baggage'', symbols and words with implied meaning, like `or`.
Of all of the infinitely many equivalent definitions of Boolean algebra,
\eqref{eq:boolstr2} is clearly the most economical, with only a single generating relation.
Why then is it so common to define symbols and names for more? Because this provides convenient
shorthand and intuition when working with Boolean algebra in practice.
Note that we humans have come up with familiar names
for *all* nonary, unary and binary relations:
There are $2^{2^0}=2$ nonary ones ($F$ and $T$),
$2^{2^1}=4$ unary ones
($F$, $T$, the identity relation and $\sim$, the last one being the only one deserving a new symbol)
and $2^{2^2}=16$ binary ones:
\begin{align\*}
F,\;\;&T,
\newline
X,\;\;\sim X,\;\;&Y,\;\;\sim Y,
\newline
X\\&Y,\;\;\sim(X\\&Y),\;\;&X\vee Y,\;\;\sim(X\vee Y),
\newline
X\Leftrightarrow Y,\;\;\sim(X\Leftrightarrow Y),\;\;
X\Rightarrow Y,\;\;&\sim(X\Rightarrow Y),\;\;
Y\Rightarrow X,\;\;\sim(Y\Rightarrow X).
\end{align\*}

### example: the group $c\_3$

As another very simple example of a finite mathematical structure, consider the 3--element group defined by
\begin{equation}
S=\begin{bmatrix}
0
\newline
1
\newline
2
\end{bmatrix},\;\;
R\_1=\begin{bmatrix}
0
\end{bmatrix},\;\;
R\_2=\begin{bmatrix}
0
\newline
2
\newline
1
\end{bmatrix},\;\;
R\_3=\begin{bmatrix}
0&1&2
\newline
1&2&0
\newline
2&0&1
\end{bmatrix},\;\;
\label{eq:z3str}
\end{equation}

The usual notation for these relations is $R\_1=e$, $R\_2(g)=g^{-1}$, $R\_3(g\_1,g\_2)=g\_1g\_2$.
In the above-mentioned Boolean algebra example, there were many equivalent choices of generators.
The situation is similar for groups, which can be defined with a single generating relation
$R(a,b)=ab^{-1}$, in terms of which the three relations above can all be reexpressed:
\begin{align}
  \begin{split}
R\_1&=&R(a,a)=e,
\newline
R\_2(a)&=&R(R(a,a),a)=a^{-1},
\newline
R\_3(a,b)&=&R(a,R(R(b,b),b))=ab.
  \end{split}
\label{eq:z3str2}
\end{align}
The specific example of \eqref{eq:z3str} thus has the following simpler equivalent definition:
\begin{align}
  \begin{split}
S=\begin{bmatrix}
0
\newline
1
\newline
2
\end{bmatrix},\;\;
R=\begin{bmatrix}
0&2&1
\newline
1&0&2
\newline
2&1&0
\end{bmatrix}
  \end{split}
\label{eq:z3str3}
\end{align}

Note that the identity element can be read off as the diagonal element(s) of this "division table''
and that the inverses can be read off from the first row.

### encoding finite mathematical structures

Since the generating relations of a finite mathematical structure can be specified by simply tabulating
all their values as in equations\eqref{eq:boolstr} and\eqref{eq:boolstr2}, it is straightforward to encode
the structure definition as a finite string of integers. Here is a simple example of such an encoding scheme:

```
<# of sets><# of relations><set def.1>...<rel.def.1>...
```

Here each set definition is simply an integer giving the number of elements in
the set.
Each relation (function) definition has the following structure:

```
<# of args><arg type 1>...<output type><value array>
```

For each of the arguments as well as for the output returned by the relation,
the type is simply one of the previously defined sets, numbered 0, 1, 2, ...
The value tensor simply lists all the values as an array (0--dimensional, 1--dimensional, 2--dimensional, etc. depending on the number of arguments, looping over earlier arguments first in the same way that computer languages such as Fortran store arrays. Elements of the output set are numbered 0, 1, ...

Following table illustrates how this works for a number of simple examples:
\\[
\begin{array}{ll}
\text{구조} & \text{부호화}
\newline
\hline
\text{공집합}       & 100
\newline
\text{5원소 집합}    & 105
\newline
\text{군 } C\_1    & 11120000
\newline
\text{다각형 } P\_3 & 113100120
\newline
\text{군 } C\_2    & 11220000110
\newline
\text{불대수}       & 11220001110
\newline
\text{군 } C\_3    & 1132000012120201
\end{array}
\\]


The two equivalent definitions of Boolean algebra corresponding to \eqref{eq:boolstr} and\eqref{eq:boolstr2} correspond to the strings
\begin{align}
  \begin{split}
s\_1&=&\,\\{ 1 8 2
0 0 0
0 0 1
1 0 0 0 1
2 0 0 0 0 0 0 1
2 0 0 0 0 1 1 1
\newline
&&\quad2 0 0 0 1 0 1 1
2 0 0 0 1 0 0 1
2 0 0 0 1 1 1 0
\\},
\newline
s\_2&=&\,\\{ 1 1 2 2 0 0 0 1 1 1 0 \\}
\newline
  \end{split}
\label{eq:boolstrings}
\end{align}
respectively; the latter is clearly more economical.

Such an explicit encoding scheme allows mathematical structures to be defined in a way more amenable to computers.
We say that an encoding $s\_1$ *generates* an encoding $s\_2$ if
$s\_1$ contains all the sets of $s\_2$ and all relations in $s\_2$ are generated by relations in $s\_1$.
We say that two encodings $s\_1$ and $s\_2$ are *equivalent*
if $s\_1$ generates $s\_2$ and $s\_2$ generates $s\_1$. In our example above, $s\_1$ and $s\_2$ are equivalent, since they generate each other.

If one wishes to catalog and enumerate all finite mathematical structures, it is convenient to order
them by some measure of their complexity. There are many ways of doing this.
For example, one could define
the complexity $H(s)$ (measured in bits) of an encoding
$s=\\{k\_1,k\_2, ...,k\_n\\}$
of a mathematical structure as
\begin{equation}
H(s)=\sum\_{i=1}^n\log\_2(2+k\_i).
\label{eq:complexity}
\end{equation}

Then the integers 0, 1 and 2 add complexities of 1 bit, $\log\_2(3)\approx 1.6$ bits and 2 bits, respectively,
and the two above encodings of Boolean algebra have complexities of $H(s\_1)=72$ bits and $H(s\_2) = 16$ bits, respectively,
whereas the empty set in Table~{\StructureTable} has 3.6 bits.

This allows us to explicitly define a finite mathematical structure as an equivalence class of encodings.
We label it by the encoding that has the lowest complexity, using lexicographical ordering to break any ties,
and we define the complexity of the mathematical structure as the complexity of this simplest encoding.
In other words, this provides an explicit scheme for enumerating all finite mathematical structures.


### infinite mathematical structures

The more general case of infinite mathematical structures is discussed at length in \Sec{GoedelSec}.
The key point is that there are only countably many computable ones (which include all the countably many finite structures),
and that to enumerate them all, the encoding scheme
above must be replaced by one that defines the relations not by explicit tabulation, but by providing an algorithm or computer
program that implements them.

