---
layout: default
title: "LithoSim: A Large, Holistic Lithography Simulation Benchmark for AI-Driven Semiconductor Manufacturing"
---
| Update Status                                                                                    | Contributors                                                                                                                                                             | Deployment Status                                                                                                                                                                                                                          |
| ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ![GitHub last commit](https://img.shields.io/github/last-commit/dw-hongquan/dw-hongquan.github.io) | [![contributors](https://img.shields.io/github/contributors/dw-hongquan/dw-hongquan.github.io.svg)](https://github.com/dw-hongquan/dw-hongquan.github.io/graphs/contributors) | [![pages-build-deployment](https://github.com/dw-hongquan/dw-hongquan.github.io/actions/workflows/pages/pages-build-deployment/badge.svg)](https://github.com/dw-hongquan/dw-hongquan.github.io/actions/workflows/pages/pages-build-deployment) |

# Overview

<div>
	<img width="900" src="../assets/img/lithosim/overview.png" class="center"> 
</div>>
<p>
<strong>Figure 1: (a). Lithography simulation tools by combining source and defocus on a fixed projector to create an optical model (a.k.a TCC), then using mask and dose inputs to generate resist. (b). Physical process for advanced optical lithography, resist imaging performance depends on source and mask quality, as well as dose and defocus fluctuations. (c). Previous benchmark (LithoBench, NIPS'23) at 45nm node ignored source, dose, and defocus effects, using DNNs for mask-to-resist generation. (d). Our benchmark at sub-28nm node considers simulation across wider mask ranges with source and process variations, using data-driven or physics-informed generative models for complete simulation.
</p>

<div>
	<img width="900" src="../assets/img/lithosim/data.png" class="center"> 
</div>
<p style="text-align:center">
	<strong> Figure 2: </strong>LithoSim Benchmark Overview.
</p>

# Getting Started



# Models and Evaluation

## Baseline Models

## Evaluation Metrics

Check out the code and pre-trained models in our [Github repo](https://github.com/woodfrog/poly-diffuse).

# Project Structure

# Legal

LithoSim uses the Apache 2.0 license for code found on the associated GitHub repo and the CC BY-NC 4.0 license for data hosted on HuggingFace.  The LICENSE file for the repo can be found in the top-level directory.
