---
layout: post
title: Training a neural network for classification of TiO2 XRD patterns
date: 2024-02-26 11:55:00+0100
description: A guide to instruct and demonstrate how neural networks can be employed for automatic phase identification in powder XRD patterns.
tags: python xrd classification
categories: guides
thumbnail: 
giscus_comments: False
related_posts: false
toc:
  sidebar: left
---

This post demonstrates the usage of neural networks for automatic analysis of powder XRD data. In this application, the objective is to identify various TiO<sub>2</sub> structures based on their characteristic pattern.

## Titanium Oxides

Titanium oxide TiO<sub>2</sub> can crystallize in various arrangements, depending on diverse influences. According to crystalline databases, such as the [COD](https://www.crystallography.net/cod/) or the [ICSD](https://icsd.fiz-karlsruhe.de/), there are 5 major phases to consider at ambient conditions:

* Anatase, e.g., COD 9009086
* Rutile, e.g., COD 9015662
* Brookite, e.g., COD 8104269
* β-TiO<sub>2</sub>, e.g., COD 1528778
* TiO<sub>2</sub>-II, e.g., COD 1530026

While the chemical composition for all of these phases is identical, their crystalline structures differ. Therefore, the XRD technique is a useful method to determine the exact phase for titanium oxide samples.

{% include figure.html path="assets/img/xrd-class-patterns.png" class="img-fluid rounded z-depth-1" zoomable=true %} 

The above figure shows the simulated, ideal diffraction patterns for the different structures. While the highest peak lies in the range between 25 and 30 degrees $$ 2θ $$ for 4 of the 5 structures (TiO<sub>2</sub>-II being the exception), the structures are distinguishable based on the presence and positions of additional diffraction peaks. Therefore, it can be expected that an automated classification algorithm is able to classify the structures accordingly.

## Network Training

The use of neural networks for analysis of powder XRD patterns has been demonstrated in various publications.[^1]<sup>,</sup>[^2]

## References
[^1]: Wang, H., et al. "Rapid identification of X-ray diffraction patterns based on very limited data by interpretable convolutional neural networks." Journal of chemical information and modeling 60.4 (2020): 2004-2011.
[^2]: Schuetzke, J., et al. "Enhancing deep-learning training for phase identification in powder X-ray diffractograms." IUCrJ 8.3 (2021): 408-420.