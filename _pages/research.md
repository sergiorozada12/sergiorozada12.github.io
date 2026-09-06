---
layout: single
title: "Research"
permalink: /research/
---

My research sits at the interplay between data, models, and optimization, with the goal of understanding and controlling dynamical systems. Three threads run through it: exploiting parsimonious low-rank structure to make sequential decision making tractable, reading dynamic programming through the lens of signal processing, and building generative models that respect the irregular domains where data lives.

## Low-rank methods in dynamical systems

Value functions and policies are the central objects of reinforcement learning, and in large state-action spaces they can neither be stored nor estimated entry by entry. Rather than turning to generic neural parametrizations, I model them as low-rank matrices and tensors: values and policy parameters are collected across states, actions, and time into multi-dimensional arrays, and factorized using PARAFAC decompositions. The resulting estimators are online and model-free, with a number of parameters that grows additively rather than multiplicatively in the dimensions of the problem. This parsimony buys interpretability and sample efficiency, and it keeps the analysis tractable: we can characterize the convergence of the resulting stochastic algorithms and quantify the error introduced by the low-rank assumption. The same idea extends beyond value functions to policy parametrizations, to finite-horizon problems where time is simply another tensor mode, to multi-task settings where the task indexes a mode, and to the transition kernels of multi-dimensional Markov models.

**Selected publications**

- **Rozada S.**, Paternain S., and Marques A. G., *Tensor and Matrix Low-Rank Value-Function Approximation in Reinforcement Learning,* IEEE Transactions on Signal Processing, 2024.  
- **Rozada S.**, Wai H. T., and Marques A. G., *Multilinear Tensor Low-Rank Approximation for Policy-Gradient Methods in Reinforcement Learning,* IEEE Transactions on Signal Processing, 2025.  
- **Rozada S.**, Orejuela J. L., and Marques A. G., *Addressing Finite-Horizon MDPs via Low-Rank Tensor Value Approximation,* IEEE Transactions on Signal Processing (under review), 2026.  
- Navarro M., **Rozada S.**, Marques A. G., and Segarra S., *Low-Rank Tensors for Multi-Dimensional Markov Models,* ICASSP, 2025.  

## A signal processing perspective on dynamical systems

Bellman's equations are fixed-point equations, and value and policy iteration are the algorithms that solve them by repeated application of an operator. Reading the transition kernel of a Markov decision process as the adjacency matrix of a weighted directed graph turns that operator into a graph shift, and dynamic programming into the repeated filtering of a signal supported on states and actions. This dictionary lets me import tools from graph signal processing and algorithm unrolling into sequential decision making: truncating and parametrizing policy iteration yields BellNet, a cascade of nonlinear graph filters trained to minimize the Bellman error, which approximates optimal policies in far fewer iterations than the classical recursion and generalizes, without retraining, to related unseen tasks. The same perspective is fruitful on the optimization side, where I study primal-dual methods for constrained decision problems in continuous spaces, and representations of policies that can be steered at test time to satisfy requirements never seen during training.

**Selected publications**

- **Rozada S.**, Rey S., Mateos G., and Marques A. G., *Unrolling Dynamic Programming via Graph Filters,* CAMSAP, 2025.  
- **Rozada S.**, Ding D., Marques A. G., and Ribeiro A., *Deterministic Policy Gradient Primal-Dual Methods for Continuous-Space Constrained MDPs,* AAAI Conference on Artificial Intelligence, 2025.  
- Li B., **Rozada S.**, and Ribeiro A., *Learning Policy Representations for Steerable Behavior Synthesis,* 2026.  

## Graph and graph signal generative modeling

Diffusion models are the state of the art for generating images and text, but their forward processes know nothing about the irregular domains where much of the interesting data lives: sensor and traffic networks, recommender systems, molecules. I study how to build the domain into the generative process itself, rather than bolting it on through the architecture. For signals on a fixed graph, replacing isotropic noising by the graph heat equation drives the forward process to a Gaussian Markov random field whose covariance is parametrized by the graph Laplacian, and turns every backward step into a graph-signal denoising problem. For generating the graphs themselves, formulating diffusion on graphons as a Jacobi stochastic differential equation yields a model that inherits the size-agnostic statistics of the continuous process, so it can be trained on small graphs and sample progressively larger ones at inference without retraining. A related line asks what attention should look like under a denoising objective, showing that linear attention can only learn an average spectral filter and motivating graph-filtered queries and keys.

**Selected publications**

- **Rozada S.**, Vimal K. B., Cavallo A., Marques A. G., Jamali-Rad H., and Isufi E., *Graph-Aware Diffusion for Signal Generation,* ICASSP, 2026.  
- Uslu Y. B., Hadou S., **Rozada S.**, Saeedi Bidokhti S., and Ribeiro A., *Graph Signal Generative Diffusion Models,* ICASSP, 2026.  
- **Rozada S.**, Qin Y., Madeira M., Frossard P., and Ribeiro A., *DiPhon: Diffusion on Graphons for Scalable Graph Generation,* 2026.  
- Khalafi S., Krawczuk I., **Rozada S.**, Kanatsoulis C., Marques A. G., and Ribeiro A., *Graph Convolutional Attention: A Spectral Perspective on Graph Denoising and Diffusion,* 2026.  

A full list is available in [Publications]({{ site.baseurl }}/publications/).
