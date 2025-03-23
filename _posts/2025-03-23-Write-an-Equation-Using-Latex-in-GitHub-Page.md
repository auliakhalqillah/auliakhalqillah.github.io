---
tags: Programming
---
The GitHub page is simple blog created and hosted in a GitHub repository for free. May be some of you who want to share an information related to mathematical expression using LaTex, you may consider to adjust some configuration in the GitHub page. In this case, the GitHub page is created by using template from https://github.com/chadbaldwin/simple-blog-bootstrap.

## Setup _config.yml
We need to set a `markdown: kramdown` and the `math_engine: mathjax` also `mathjax: true`. These three important things to be considered. In general, the configuration will looks like as follow
```
markdown: kramdown
kramdown:
  math_engine: mathjax
  mathjax: true
  syntax_highlighter_opts:
    disable: true
```
## Setup the MathJax convertion
This set up is done in the `_includes/head.html`. Please add the following JavaScript code in the `_includes/head.html` before end of `</head>`.

```
<script type="text/javascript" async
    src="https://polyfill.io/v3/polyfill.min.js?features=es6">
  </script>
  <script type="text/javascript" async
    id="MathJax-script" src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js">
  </script>
  ```
  
  Once you have finished set up, please create an equation post. The equation can be written by using `$$ equation $$`, for example, the command of `$$ y = mx + c $$` will be rendered as $$ y = mx + c $$ 

