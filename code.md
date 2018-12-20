---
layout: home
title: Code
permalink: /code/
---

Grab the code below for Jekyll or any other CMS:



```{html}
<div id="visual"></div>

<script type="module">

  // NOTEBOOK CONFIGURATION
  import notebook from "https://api.observablehq.com/@fil/tissots-indicatrix.js";

  const target = document.querySelector("#visual");
  const renders = {
    "viewof p": "p",
    "display": "div.fullwidth",
  };


  // BOILERPLATE
  import {Inspector, Runtime} from "https://unpkg.com/@observablehq/notebook-runtime@1.2.0?module";
  for (let i in renders) {
    let s = renders[i], a = s.match(/^\w+/);
    if (a) {
      renders[i] = document.createElement(a[0]);
      target.appendChild(renders[i]);
      if (a = s.match(/\.(\w+)$/))
        renders[i].className = a[1]; 
    }
    else
      renders[i] = document.querySelector(renders[i]);
  }
  Runtime.load(notebook, (variable) => {
    if (renders[variable.name]) {
      return new Inspector(renders[variable.name]);
    } else {
      // return true; // uncomment to run hidden cells
    }
  });
</script>
```

Or see similar How-tos for :
- [react](https://beta.observablehq.com/@jashkenas/how-to-embed-a-notebook-in-a-react-app), by Jeremy Ashkenas;
- [ydill](https://mathisonian.github.io/observable-idyll/), by Matthew Conlen;
- [codepen](https://codepen.io/jashkenas/pen/gzZXPG), by J.A.

<style>
pre, code {
  font-size: 0.75rem;
  line-height: 0.95rem;
}
</style>