---
layout: post
title: Basics of Random Phase Approximation
date: 2025-11-4 11:12:00-0400
description: Basics of Random Phase Approximation
tags: physics math
categories: sample-posts
related_posts: false
---

I have recently been learning about Random Phase Approximation (RPA), which is a technique used to calculate fluctuations of the free energy in the so-called weak-segregation regime (of polymers). My aim with this blog post is to introduce RPA by way of simple (but nontrivial) example. 

Let us begin by defining terminology. The fluctuation of an observable $$\mathcal{A}$$ is defined as $$\delta\mathcal{A} = \mathcal{A} - \langle \mathcal{A} \rangle$$, where $$\langle \cdot \rangle$$ denotes the _mean-field value_, or _expectation value_, depending on the context.

Consider an arbitrary number (not too large, but not too small) of polyelectrolytes (polymers with $$\pm$$ charge on the monomer units) with $$N$$ monomers and lattice spacing $a$ in bad solvent. Polymers in bad solvent will tend to form clumps (this is called many things depending on the flavor of polymer one studies, but here I will refer to it as aggregation). Because the polyelectrolytes are strictly positively charged, they induce counter-ions (negatively charged particles) in the solvent. It is natural then to define the scalar fields $$\phi(\mathbf{r})$$ and $$n(\mathbf{r})$$ which denote the polyelectrolyte density and counter-ion density, respectively. We can define now the charge density also as a scalar field:
  
  $$
    \rho(\mathbf{r}) = \left(\frac{f}{a^3} \phi(\mathbf{r}) - n(\mathbf{r})\right),
  $$
  
where $$f$$ denotes the fraction of charged monomers in the polyelectrolyte. We assume for this problem that $$fN \gg 1$$, i.e., that a sufficient number of monomers carry charge. To make our calculations simple in the end,
we also assume the system is net neutral so that $$\frac{f}{a^3} \langle \phi \rangle = \langle n \rangle$$ (here, $$\langle \cdot \rangle $$ denotes the _expectation value_, or _mean field value_). The fluctuations in density
of both the polyelectrolytes and counter-ions are defined as

  $$
    \delta \phi(\mathbf{r}) = \phi(\mathbf{r}) - \langle \phi(\mathbf{r}) \rangle, \quad \delta n(\mathbf{r}) = n(\mathbf{r}) - \langle n(\mathbf{r}) \rangle.
  $$

We aim now to write down the second-order fluctuations 

  $$
    \delta^{(2)} \mathcal{F} = \delta^{(2)} \mathcal{F}_\mathrm{vol} + \delta^{(2)} \mathcal{F}_\mathrm{grad} + \delta^{(2)} \mathcal{F}_\mathrm{coul},
  $$

  where 
  
  $$
    \mathcal{F}_\mathrm{vol} = \int_{\mathbb{R}^3} d^3 \mathbf{r} \left[\frac{1}{a^3}\left( \frac{\phi(\mathbf{r})}{N}\mathrm{ln}(\phi(\mathbf{r})) + (1-\phi(\mathbf{r})\mathrm{ln}(1-\phi(\mathbf{r})) + \chi \phi(\mathbf{r})^2\right) + \left(n(\mathbf{r}) \ln(n(\mathbf{r})a^3) - n(\mathbf{r}) \right)\right],
  $$
  
  and
  
  $$
    \mathcal{F}_\mathrm{grad} = \int_{\mathbb{R}^3} d^3 \mathbf{r} \left(\frac{K}{2}(\nabla \phi(\mathbf{r}))^2\right),
  $$   
  
  and 
  
  $$
    \mathcal{F}_\mathrm{coul} = \frac{1}{2\varepsilon} \int_{\mathbb{R}^3} d^3 \mathbf{r} d^3 \mathbf{r}^\prime \left(\frac{\rho(\mathbf{r})\rho(\mathbf{r}^\prime)}{\lvert \mathbf{r} - \mathbf{r}^\prime \rvert}\right),
  $$

where $$d^3\mathbf{r} = dxdydz$$. The integrand of each of the free energies above is called the free energy _density_, and is denoted by $$f$$. Note that the free energies in the above are not functions in the usual sense, but functions _of_ functions, called _functionals_. A (real-valued) function $$f(x)$$ has argument $$x \in \mathbb{R}$$, whereas a functional $$f(g(x))$$ has argument $$g(x) \in X$$, where $$X(\mathbb{R})$$ denotes the space of functions valued over $$\mathbb{R}$$. Calculating the fluctuations of functionals requires additional machinery since defining differentiation of a functional is not obvious upon first glance. Suppose we are given a functional $$\mathcal{F}(\phi) = \int d^3 \mathbf{r}  f(\phi(\mathbf{r}), \nabla \phi(\mathbf{r}))$$ that is sufficiently nice (continuous, differentiable, etc.). The _functional derivative_ of $$\mathcal{F}(\phi)$$ with respect to $$\phi(\mathbf{r})$$ is given by
  
  $$
    \frac{\delta \mathcal{F}(\phi)}{\delta \phi} = \frac{\partial f(\phi, \nabla \phi)}{\partial \phi} - \nabla \cdot \frac{\partial f(\phi, \nabla \phi)}{\partial (\nabla \phi)}.
  $$

The functional derivative is only half of the story, though. To calculate the fluctuations $$\delta \mathcal{F}$$ we must first make some observations. Namely, the fluctuations of the free energy $$\delta \mathcal{F}$$ is a function of the fluctuations of the argument of $$\mathcal{F}$$. If $$\mathcal{F} = \mathcal{F}(\phi)$$, then $$\delta \mathcal{F} = \delta \mathcal{F}(\delta \phi)$$. Since $$\delta \phi = \phi - \langle \phi \rangle$$, we can make the observation that the fluctuation of the free energy can be written as a _functional taylor expansion_ about $$\langle \phi \rangle$$:
  
  $$
    \delta \mathcal{F}(\phi) = \underbrace{\mathcal{F}(\langle \phi \rangle)}_{\delta^{(0)}\mathcal{F}(\phi)} + \underbrace{\int d\mathbf{r} \frac{\delta f(\phi, \nabla \phi)}{\delta \phi} \delta \phi}_{\delta^{(1)} \mathcal{F}(\phi) } + \underbrace{\frac{1}{2}\iint d\mathbf{r} d\mathbf{r}^\prime \frac{\delta^2f(\phi, \nabla \phi)}{\delta \phi(\mathbf{r})\delta\phi(\mathbf{r}^\prime)}\delta \phi(\mathbf{r}) \delta \phi(\mathbf{r}^\prime)}_{\delta^{(2)} \mathcal{F}(\phi)} + \dots
  $$


