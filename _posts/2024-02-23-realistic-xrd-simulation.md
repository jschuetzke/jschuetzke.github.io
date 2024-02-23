---
layout: post
title: Simulation of realistic powder X-ray diffraction patterns
date: 2024-02-23 10:05:00+0100
description: A quick guide to explain the python-powder-diffraction package
tags: python xrd simulation
categories: guides
giscus_comments: False
related_posts: false
toc:
  sidebar: left
---

This post shows how to utilize the python-powder-diffraction package to simulate realistic powder XRD patterns.

## Powder XRD patterns

X-ray diffraction (XRD) is a popular method to analyze crystalline sampes. In practice, the sample is often ground into a fine powder to analyze the sample from all directions simultaneously without the need to rotate the sample. Thus, the data is recorded as pairs of angles (typically $$ 2θ $$) and corresponding intensities. These diffraction patterns provide valuable information about the crystal structure, including lattice spacing and symmetry. Furthermore, the pattern contains information regarding the specimen, such as the size of grains in the powder.

Depending on the chemical composition and arrangement within the resulting crystal structure, each material exhibits a unique diffraction pattern characterized by specific peak intensities and positions. As a result, the diffraction pattern serves as a distinctive fingerprint that can be used to identify materials present in the recorded data. By comparing experimental diffraction patterns with known reference patterns stored in databases, scientists can accurately determine the composition and structure of the crystalline sample under investigation. Therefore, XRD is widely employed in various domains to rapidly identify known materials and ensure quality control, while also playing a crucial role in research to determine the properties of novel materials.

### Appearance

The following figure shows an exemplary XRD pattern that has been acquired from the [RRUFF database](https://rruff.info/). In particular, entry R050031 has been selected, which corresponds to the mineral rutile. This substance with chemical composition TiO<sub>2</sub> and a tetragonal crystal structure has been analyzed using a XRD instrument with a copper anode (wavelength 1.540562 nm), resulting in the following pattern:

<div class="l-page">
  <iframe src="{{ '/assets/plotly/rutile_R050031.html' | relative_url }}" frameborder='0' scrolling='no' height="500px" width="100%" style="border: 1px dashed grey;"></iframe>
</div>

Analysis of the acquired pattern allowed for determining the lattice parameters, which has been reported as $$ a = b = 4.5945; c = 2.9594 $$.

### Reported Information

While the RRUFF database provides measured XRD patterns for some minerals, the information derived from the diffraction data is typically stored in reduced form. Databases such as the [COD](https://www.crystallography.net/cod/) or the [ICSD](https://icsd.fiz-karlsruhe.de/) have thousands of entries and store various information including the chemical composition and arrangement within the crystal structure.
