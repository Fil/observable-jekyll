---
layout: post
title:  "Vega Embed"
date:   2018-05-23 09:00:00 +0200
author: Dominik Moritz
categories: explore
---


<div id="visual"></div>

_Note: The last example doesn’t work, because the dataset is unreachable from this website._

<script type="module">

  // NOTEBOOK CONFIGURATION
  import notebook from "https://api.observablehq.com/d/8582ee54f32ffbbe.js";

  const target = document.querySelector("#visual");
  const renders = {
    "cars": "div",
    "lite": "div",
    "life": "div",
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


<style>
/* https://css-tricks.com/full-width-containers-limited-width-parents/ */
.fullwidth {
  width: 100vw;
  position: relative;
  left: 50%;
  right: 50%;
  margin-left: -50vw;
  margin-right: -50vw;
}
.observablehq--error { color: red }
#visual { min-height: 40vw }
</style>


[Source](https://beta.observablehq.com/@domoritz/hello-vega-embed)