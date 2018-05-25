---
layout: post
title:  "Vega Embed"
date:   2018-05-23 09:00:00 +0200
categories: explore
---

(This example doesn’t work because the datasets are unreachable from this website.)

<div id="cars"></div>
<div id="lite"></div>
<div class="fullwidth">
  <div id="life"></div>
</div>

<script type="module">
  import notebook from "https://api.observablehq.com/d/8582ee54f32ffbbe.js?key=5a56073debd3654b";
  import {Inspector, Runtime} from "https://unpkg.com/@observablehq/notebook-runtime@1.0.1?module";
  const renders = {
    "cars": "#cars",
    "lite": "#lite",
    "life": "#life",
  };
  Runtime.load(notebook, (variable) => {
    const selector = renders[variable.name];
    if (selector) {
      return new Inspector(document.querySelector(selector));
    } else {
      // return true; // useful only for the rare notebooks that uses side effects
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
#display { min-height: 40vw }
</style>

[Source](https://beta.observablehq.com/@domoritz/hello-vega-embed)