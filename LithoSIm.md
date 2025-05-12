---
layout: default
title: "LithoSim: A Large, Holistic Lithography Simulation Benchmark for AI-Driven Semiconductor Manufacturing"
---
# Overview

<div>
	<img width="900" src="assets/img/teaser.png" class="center"> 
</div>>
<p>
<strong>Figure 1: PolyDiffuse for floorplan and HD map reconstruction:</strong> Starting from an initial proposal (e.g., from a human annotator or an existing method), the sensor-conditioned denoising process of our Guided Set Diffusion Model (GS-DM) generates shape reconstructions in a few sampling steps, initialized and directed by the guidance networks. The initial proposal above mimics simple human inputs that indicate rough locations and specify the number of vertices  for the polygonal shapes.
</p>

<div>
	<img width="900" src="assets/img/method_figure.png" class="center"> 
</div>>

<p style="text-align:center">
	<strong> Figure 2: </strong>Illustration of the forward and reverse processes of PolyDiffuse with floorplan data.
</p>

# Paper

<div>
	<a href=".">
	<img class="thumbnail" src="assets/img/thumbnail.png"> 
	</a>
</div>>

<div class="text-center">
	<a href="assets/paper.pdf"> Download PDF </a>     <a href="https://arxiv.org/abs/2306.01461"> Arxiv </a>     <a href="assets/supp.pdf"> Supplementary </a>     
	<!-- <a href="assets/poster.pdf"> Poster </a> -->
</div>

<br>
<div class="bibtex-box">
	<strong>@article{</strong>chen2023polydiffuse,
	<br>
	     title={PolyDiffuse: Polygonal Shape Reconstruction via Guided Set Diffusion Models}, 
	<br> 
	     author={Chen, Jiacheng and Deng, Ruizhi and Furukawa, Yasutaka},
	<br> 
	     journal={arXiv preprint arXiv:2306.01461},
	<br> 
	     year={2023}<br><strong>}</strong>
</div>

# Code / Pre-trained Models

Check out the code and pre-trained models in our [Github repo](https://github.com/woodfrog/poly-diffuse).

# Acknowledgement

This research is partially supported by NSERC Discovery Grants with Accelerator Supplements and DND/NSERC Discovery Grant Supplement, NSERC Alliance Grants, and John R. Evans Leaders Fund (JELF). We thank the Digital Research Alliance of Canada and BC DRI Group for providing computational resources.
