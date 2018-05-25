---
layout: post
title:  "Histograms"
date:   2018-05-25 09:00:00 +0200
categories: explore
---

<div class="fullwidth">
  <p id="viewof-threshold"></p>
  <div id="chart"></div>
</div>

<script type="module">
  import {Inspector, Runtime} from "https://unpkg.com/@observablehq/notebook-runtime@1.0.1?module";
  import notebook from "https://api.observablehq.com/d/6e56831344136167.js?key=cdc0537b1eb54812";
  const renders = {
    "viewof threshold": "#viewof-threshold",
    "chart": "#chart",
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

[Source](https://beta.observablehq.com/@johnburnmurdoch/histograms)