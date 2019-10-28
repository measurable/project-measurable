---
title: "Mathjax 설정"
date: 2019-09-16T15:45:17+09:00
categories:
    - sitedoc
tags:
    - mathjax
keywords:
inspired: http://docs.mathjax.org/en/latest/options/input/tex.html
motivation:
draft: true
---


## 디폴트 설정

### The Configuration Block


```js
MathJax = {
  tex: {
    packages: ['base'],        // extensions to use
    inlineMath: [              // start/end delimiter pairs for in-line math
      ['\\(', '\\)']
    ],
    displayMath: [             // start/end delimiter pairs for display math
      ['$$', '$$'],
      ['\\[', '\\]']
    ],
    processEscapes: true,      // use \$ to produce a literal dollar sign
    processEnvironments: true, // process \begin{xxx}...\end{xxx} outside math mode
    processRefs: true,         // process \ref{...} outside of math mode
    digits: /^(?:[0-9]+(?:\{,\}[0-9]{3})*(?:\.[0-9]*)?|\.[0-9]+)/,
                               // pattern for recognizing numbers
    tags: 'none',              // or 'ams' or 'all'
    tagSide: 'right',          // side for \tag macros
    tagIndent: '0.8em',        // amount to indent tags
    useLabelIds: true,         // use label name rather than tag for ids
    multlineWidth: '85%',      // width of multline environment
    maxMacros: 1000,           // maximum number of macro substitutions per expression
    maxBuffer: 5 * 1024,       // maximum size for the internal TeX string (5K)
    baseURL:                   // URL for use with links to tags (when there is a <base> tag in effect)
       (document.getElementsByTagName('base').length === 0) ?
        '' : String(document.location).replace(/#.*$/, ''))
  }
};
```

### default autoload definitions:

```js
MathJax = {
  tex: {
    autoload: expandable({
      action: ['toggle', 'mathtip', 'texttip'],
      amsCd: [[], ['CD']],
      bbox: ['bbox'],
      boldsymbol: ['boldsymbol'],
      braket: ['bra', 'ket', 'braket', 'set', 'Bra', 'Ket', 'Braket', 'Set', 'ketbra', 'Ketbra'],
      cancel: ['cancel', 'bcancel', 'xcancel', 'cancelto'],
      color: ['color', 'definecolor', 'textcolor', 'colorbox', 'fcolorbox'],
      enclose: ['enclose'],
      extpfeil: ['xtwoheadrightarrow', 'xtwoheadleftarrow', 'xmapsto',
                 'xlongequal', 'xtofrom', 'Newextarrow'],
      html: ['href', 'class', 'style', 'cssId'],
      mhchem: ['ce', 'pu'],
      newcommand: ['newcommand', 'renewcommand', 'newenvironment', 'renewenvironment', 'def', 'let'],
      unicode: ['unicode'],
      verb: ['verb']
    }
  }
};
```













### Mathjax 설정

**ref**: 'Ch. 7 Configuring and Loading MathJax', [_MathJax Documentation, Release 3.0_](https://buildmedia.readthedocs.org/media/pdf/mathjax/latest/mathjax.pdf), Sep 10. 2019. pp. 25-

Mathjax는 다양한 컴퍼넌트들을 가지며, 이들 컴퍼넌트의 설정은 `Mathjax`라는 이름의 js global objet를 통해 이루어진다.
`Mathjax` 컴퍼넌트는 각각의 Mathjax 컴퍼넌트를 설정하는 sub-object 블럭들로 이루어진다.

>html 페이지 소스에서 설정을 담은 Mathjax object는 Mathjax 자체를 로드하는 스크립트 앞에 위치해야 한다.

다음은 inline-math delimiter를 설정하는 TeX input 컴퍼넌트와 출력의 작동 방식설정하는 SVG 컴퍼넌트


```html
<!--- config mathjax --->
<script> MathJax = {
  tex: {
    inlineMath: [['$', '$'], ['\\(', '\\)']],
    autoload: expandable({
      braket: []
    }
  },
  svg: {
    fontCache: 'global'
  }
};
</script>

<!--- load mathjax --->
<script type="text/javascript" id="MathJax-script" async
src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js"> </script>
```

또는, 다음과 같이 설정 스크립트를 별도의 js 파일로 만들 수도 있다.

`mathjax-config.js`

```js
window.MathJax = {
  tex: {
    inlineMath: [['$', '$'], ['\\(', '\\)']]
  },
  svg: {
    fontCache: 'global'
} };
```

and then

```html
<script src="mathjax-config.js" defer></script>
<script type="text/javascript" id="MathJax-script" defer
src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js"> </script>
```

OR 하나의 스크립트에서 설정과 로딩을 모드 처리할 수도 있다.


`load-mathjax.js`

```js
window.MathJax = {
  tex: {
    inlineMath: [['$', '$'], ['\\(', '\\)']]
  },
  svg: {
    fontCache: 'global'
} };
(function () {
var script = document.createElement('script');
script.src = 'https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js'; script.async = true;
document.head.appendChild(script);
})();
```

and then simply,

```html
<script src="load-mathjax.js" async></script>
```




The various components of MathJax, including

- its input and output processors,
- its extensions, and
- the MathJax core,

all can be configured though a `MathJax` global object that specifies the configuration you want to use.
The `MathJax` object consists of sub-objects that configure the individual components of MathJax. For example,

- the [input/tex](https://docs.mathjax.org/en/latest/basic/mathematics.html#tex-input) component is configured through a `tex` block within the `MathJax` object, while the [startup](https://docs.mathjax.org/en/latest/web/components/misc.html#startup-component) component is configured through the `startup` block.

These blocks are javascript objects that includes `name: value` pairs giving the names of parameters and their values, with pairs separated by commas.

>Be careful not to include a comma after the last value, however, as some browsers will fail to process the configuration if you do.

Some blocks may contain further sub-blocks. For example,

- the `tex` block can have a `macros` sub-block that pre-defines macros, and
- a tagFormat block (when the [tagFormat](https://docs.mathjax.org/en/latest/input/tex/extensions/tagFormat.html#tex-tagformat) component is used) to define how equation tags are displayed and handled.

### TeX Input Processor Options

The options below control the operation of the TeX input processor that is run when you include 'input/tex', 'input/tex-full', or 'input/tex-base' in the load array of the loader block of your MathJax configuration, or if you load a combined component that includes the TeX input jax. They are listed with their default values. To set any of these options, include a tex section in your MathJax global object.

```js
MathJax = {
  tex: {
    packages: ['base'],        // extensions to use
    inlineMath: [              // start/end delimiter pairs for in-line math
      ['\\(', '\\)']
    ],
    displayMath: [             // start/end delimiter pairs for display math
      ['$$', '$$'],
      ['\\[', '\\]']
    ],
    processEscapes: true,      // use \$ to produce a literal dollar sign
    processEnvironments: true, // process \begin{xxx}...\end{xxx} outside math mode
    processRefs: true,         // process \ref{...} outside of math mode
    skipHtmlTags: [            //  HTML tags that won't be searched for math
        'script', 'noscript', 'style', 'textarea', 'pre',
        'code', 'annotation', 'annotation-xml'
    ],
    includeHtmlTags: {         //  HTML tags that can appear within math
        br: '\n', wbr: '', '#comment': ''
    },
    ignoreHtmlClass: 'tex2jax_ignore',    //  class that marks tags not to search
    processHtmlClass: 'tex2jax_process',  //  class that marks tags that should be searched
    digits: /^(?:[0-9]+(?:\{,\}[0-9]{3})*(?:\.[0-9]*)?|\.[0-9]+)/,
                               // pattern for recognizing numbers
    tags: 'none',              // or 'ams' or 'all'
    tagSide: 'right',          // side for \tag macros
    tagIndent: '0.8em',        // amount to indent tags
    useLabelIds: true,         // use label name rather than tag for ids
    multlineWidth: '85%',      // width of multline environment
    maxMacros: 1000,           // maximum number of macro substitutions per expression
    maxBuffer: 5 * 1024,       // maximum size for the internal TeX string (5K)
    baseURL:                   // URL for use with links to tags (when there is a <base> tag in effect)
       (document.getElementsByTagName('base').length === 0) ?
        '' : String(document.location).replace(/#.*$/, ''))
  }
};
```

Note that some extensions make additional options available. See the [TeX Extension Options](https://docs.mathjax.org/en/latest/options/input/tex.html#tex-extension-options) section  for details.
