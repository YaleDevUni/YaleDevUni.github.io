---
title:  "Github pages with mathjax and jekyll"
categories: 
  - Jekyll
tag:
  - jekyll
  - mathjax
toc: true
toc_sticky: true
use_math: true
---

Currently, github pages does not support ***LaTex*** syntax with pure jekyll engine. We want to intergrate mathmatical symbols to markdown file instead inserting images. I tried some methods to generate math symbols in markdown, and found a way that works on me.<br />
Here is what I found: 
(solution from [Here](http://haixing-hu.github.io/programming/2013/09/20/how-to-use-mathjax-in-jekyll-generated-github-pages/))
## Step 1
Make sure your markdown engine is **kramdown** in **root_directory_of_project/_config.yml** file
```
markdown: kramdown
```
## Step 2
In  **_include** folder, create new file named **_mathjax_support.html**
``` html
<script type="text/x-mathjax-config">
MathJax.Hub.Config({
    TeX: {
      equationNumbers: {
        autoNumber: "AMS"
      }
    },
    tex2jax: {
    inlineMath: [ ['$', '$'] ], //you can modifiy here
    displayMath: [ ['$$', '$$'] ], //you can modify here
    processEscapes: true,
  }
});
</script>
<script type="text/javascript" async
  src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_CHTML">
</script>
```

## Step 3
In the **_layouts/default.html**, append below code in the **<head>**
``` 
{% raw %}
{% if page.use_math %}
{% include _mathjax_support.html %}
{% endif %}
{% endraw %}
```
## Step 4
In the YAML front-matter, you just need to add below
``` yaml
use_math: true
```
## Outputs
Now you can just write LaTex syntax on markdown. Here are some examples
### Inline equation
``` latex
Hello! this is example inline equation $m \le \frac {n(n-1)} {2}$
``` 
output:<br />
Hello! this is example inline equation $m \le \frac {n(n-1)} {2}$

### math block
``` latex
Hello! this is example math block $$m \le \frac {n(n-1)} {2}$$
```
outputs:<br />
Hello! this is example math block $$m \le \frac {n(n-1)} {2}$$

For more about mathjax, surf [here](http://docs.mathjax.org/en/latest/)
## Some References:
- http://haixing-hu.github.io/programming/2013/09/20/how-to-use-mathjax-in-jekyll-generated-github-pages/
- http://docs.mathjax.org/en/latest/