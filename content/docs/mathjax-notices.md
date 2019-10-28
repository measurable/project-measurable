---
title: "Mathjax Notices"
date: 2019-09-13T19:27:40+09:00
categories:
    - sitedoc
tags:
    - mathjax
keywords:
inspired: http://docs.mathjax.org/en/latest/
motivation:
draft: true
---


- `tex-chtml`로 출력을 common html로 설정하면 `\underbrace`가 깨져나온다. `tex-svg`로 아웃풋을 `svg`로 설정하면 이 문제가 안생긴다.
## TeX and LaTeX extensions

While MathJax includes nearly all of the Plain TeX math macros, and many of the LaTeX macros and environments, not everything is implemented in the core TeX input processor. Some less-used commands are defined in extensions to the TeX processor. MathJax will load some extensions automatically when you first use the commands they implement (for example, the \color macro is implemented in the color extension, but MathJax loads this extension itself when you use that macro). While most extensions are set up to load automatically, there are a few that you would need to load explicitly yourself. See the autoload extension below for how to configure which extensions to autoload.


Loading TeX Extensions
To enable one of the TeX extensions you need to do two things: load the extension, and configure TeX to include it in its package setup. For the first, to load an extension as a component, add its name to the load array in the loader block of your MathJax configuration. For example, to load the color extension, add '[tex]/color' to the load array, as in the example below. To do the second, add the extension name to packages array in the tex block of your configuration. You can use the special '[+]' notation to append it to the default packages (so you don’t need to know what they are). For example:

window.MathJax = {
  loader: {load: ['[tex]/color']},
  tex: {packages: {'[+]': ['color']}}
};
will load the color extension and configure the TeX input jax to enable it.

A number of extensions are already loaded and configured in the components that contain the TeX extension. The input/tex, and the combined components containing tex and not ending in -full include the ams, newcommand, noUndefined, require, autoload, and configMacros extensions, with the other extensions being autoloaded as needed. The input/tex-base component has no extensions loaded, while the input/tex-full and the combined extensions ending in -full load all the extensions.

If you load a component that has an extension you don’t want to use, you can disable it by removing it from the package array in the tex block of your MathJax configuration. For example, to disable \require and autoloading of extensions, use

window.MathJax = {
  tex: {packages: {'[-]': ['require', 'autoload']}}
};
if you are using, for example, the tex-chtml.js combined component file.

Loading Extensions at Run Time
You can also load these extensions from within a math expression using the non-standard \require{extension} macro. For example

\(\require{color}\)
would load the color extension into the page. This way you you can load extensions into pages that didn’t load them in their configurations (and prevents you from having to load all the extensions into all pages even if they aren’t used).

Configuring TeX Extensions
Some extensions have options that control their behavior. For example, the color extension allows you to set the padding and border-width used for the \colorbox and \fcolorbox macros. Such extensions are configured using a block within the tex configuration of your MathJax configuration object. The block has the same name as the extension, and contains the options you want to set for that extension. For example,

window.MathJax = {
  loader: {load: ['[tex]/color']},
  tex: {
    packages: {'[+]': ['color']},
    color: {
      padding: '5px'
    }
  }
};
would set the padding for \colorbox to be 5 pixels.

See the Configuring MathJax section for details about the options for each of the extensions below.

For extensions that are not loaded explicitly but may be loaded via the autoload package or the \require macro, you can’t include the configuration within the tex block, because MathJax will not know the options that are available (since the extension hasn’t been loaded yet). In that case, move the configuration block to the top level of the MathJax configuration object and prefix it with [tex]/, as in:

window.MathJax = {
  '[tex]/color': {
    padding: '5px'
  }
};

## 브라우저 호환성

The CommonHTML and SVG output supports all modern browsers (Chrome, Safari, Firefox, Edge), and most mobile browsers. Include the polyfill library in order to support earlier browser versions (see their browser support page for details). In particular, to allow MathJax version 3 to work with IE11, include the line

```html
<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
```

**before** the script that loads MathJax.

### Viewport meta tag

The `viewport` meta tag provides the browser with instructions regarding viewports and zooming. This way, web developers can control how a webpage is displayed on a mobile device.

Incorrect or missing viewport information can confuse MathJax’s layout process, leading to very small font sizes. We recommend that you use standard values such as the following:

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

### Internet Explorer Emulation modes

Internet Explorer provides so-called emulation modes for backward compatibility to its legacy versions. These emulation modes have been deprecated since Internet Explorer 11, cf. Microsoft documentation.

MathJax is fastest when in the standards mode of each IE version, so it is best to force the highest mode possible. That can be accomplished by adding

```html
<meta http-equiv="X-UA-Compatible" content="IE=edge">
```

at the top of the `<head>` section of your HTML documents.

>Note: This line must come at the beginning of the `<head>`, before any stylesheets, scripts, or other content are loaded.

Note that versions of IE prior to 11 are no longer supported in MathJax version 3.
