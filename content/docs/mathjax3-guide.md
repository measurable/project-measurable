---
title: "Mathjax3 가이드"
date: 2019-09-12T05:28:57+09:00
categories:
    - sitedoc
tags:
    - mathjax
keywords:
inspired: https://docs.mathjax.org/en/latest/index.html
motivation:
draft: true
---

## hugo 마크다운 프로세서를 사용할 때의 고려사항

## TeX and LaTeX Support

The support for TeX and LaTeX in MathJax involves two functions:

1. Looks for mathematics within your web page (indicated by math delimiters like `$$`...`$$`) and marks the mathematics for later processing by MathJax, and
2. Converts the TeX notation into MathJax’s internal format, where one of MathJax’s output processors then displays it in the web page.

A component, the **TeX input jax** provide both functions.

The TeX input jax can be configured to look for whatever markers you want to use for your math delimiters. See the [TeX configuration options](https://docs.mathjax.org/en/latest/options/input/tex.html#tex-options) section for details on how to customize the delimiters, and other options for TeX input.

The TeX input processor handles conversion of your mathematical notation into MathJax’s internal format (which is essentially MathML), and so acts as a TeX to MathML converter. The TeX input processor has can also be customized through the use of extensions that define additional functionality (see the [TeX and LaTeX extensions](https://docs.mathjax.org/en/latest/input/tex/extensions.html#tex-extensions) section).

### Differences from Actual TeX

**First** and foremost, the TeX input processor implements **only the math-mode macros** of TeX and LaTeX, not the text-mode macros.
For example, MathJax does not implement `\emph` or `\begin{enumerate}`...`\end{enumerate}` or other text-mode macros or environments.

There are **two exception** to this rule. First,

1. MathJax supports the `\ref` macro outside of math-mode.
2. MathJax supports some macros that add text within math-mode (such as `\text{}`) as well as $...$ and \(...\) within such macros (to switch back into math-mode) and `\$` to escape.

**Second**, some features in MathJax might be necessarily limited. For example, MathJax only implements a limited subset of the `array` environment’s preamble; i.e., only the `l`, `r`, `c`, and `|` characters alongside `:` for dashed lines---everything else is ignored.

### Automatic Equation Numbering

The TeX input processing in MathJax can be configured to add equation numbers to displayed equations automatically. This functionality is turned off by default, but it is easy to configure MathJax to produce automatic equation numbers by adding:

```js
window.MathJax = {
  tex: {
    tags: 'ams'
  }
};
```

to tell the TeX input processor to use the AMS numbering rules (where only certain environments produce numbered equations, as they would be in LaTeX). It is also possible to set the tagging to `all`, so that every displayed equation will get a number, regardless of the environment used.

