---
layout: page
title: LMdist
description: (R) Removing the arch effect in dimensionality reduction.
img: assets/img/hoops_lmdist_2023.gif
importance: 1
category: Seen on GitHub
---

This work has been published with *Bioinformatics*, read the <a href="https://doi.org/10.1093/bioinformatics/btad727">full article here</a>.

___

## Local Manifold Distance (LMdist) removes the arch effect in dimensionality reduction

Here we give a brief introduction to LMdist, an algorithm for adjusting pairwise distances in dimensionality reduction in order to remove the "arch effect."

Let's start with the problem: **what is the arch/horseshoe effect?**

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/publication_preview/hoops_lmdist_2023_after.png" title="Soil PCoA before correction" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    On the left, we visualize the relationship between soil microbiome samples with varying pH levels. The plot clearly demonstrates an arched shape, not quite the linear pH relationship we would expect. Middle, the pairwise distances are adjusted to better reflect the gradient, since low pH and high pH samples have very few microbes in common. The arch is no longer present, and other sources of variation are now visible in the 2nd dimension (y-axis).
</div>


citation: 
