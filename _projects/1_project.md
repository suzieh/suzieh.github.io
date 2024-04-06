---
layout: page
title: Local Manifold Distance
description: (R) Removing the arch effect in dimensionality reduction.
img: assets/img/hoops_lmdist_2023.gif
importance: 1
category: Seen on GitHub
github: https://github.com/knights-lab/LMdist
---

This work has been published with *Bioinformatics*. Read the <a href="https://doi.org/10.1093/bioinformatics/btad727">full article here</a>.

___

## Local Manifold Distance (LMdist) removes the arch effect in dimensionality reduction

Here we give a brief introduction to LMdist, an algorithm for adjusting pairwise distances in dimensionality reduction in order to remove the "arch effect."

Let's start with the problem: **what is the arch/horseshoe effect?**

When conducting dimensionality reduction on big, multivariate datasets, it is common to see the data points form an arch-like formation. It was debated where this was coming from, but most researchers tended to ignore the effect as some "anomaly."

I found that the arch and horseshoe appear when a *gradient* of some sort is being sampled. So, if the data points are collected along some scale like temperature, age, pH, or even time. If the ends of the scale are very different from one another, then the arch would appear.

Consider for example this soil dataset, where each dot represents a soil sample taken at a different pH level. The arch is clearly evident, making samples at the ends of the pH gradient appear closer together in the plot, rather than a linear relationship we would expect!

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/hoops_lmdist_2023_before.png" title="Soil PCoA before correction" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    PCoA plot of Soil microbiome samples with varying pH levels. The closer sample points appear to one another, the more similar their microbiome content. The plot clearly demonstrates an arched shape, not quite the linear pH relationship we would expect.
</div>



citation: 
