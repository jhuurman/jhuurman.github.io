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

Consider an arbitrary number (not too large, but not too small) of polyelectrolytes (polymers with $$\pm$$ charge on the monomer units) with $$N$$ monomers and lattice spacing $a$ in bad solvent. Polymers in bad solvent will tend to form clumps (this is called many things depending on the flavor of polymer one studies, but here I will refer to it as aggregation). Because the polyelectrolytes are strictly positively charged, they induce counter-ions (negatively charged particles) in the solvent. It is natural then to define the scalar fields $$\phi(\mathbf{r})$$ and $$n(\mathbf{r})$$ which denote the polyelectrolyte density and counter-ion density, respectively. We can define now the charge density also as a scalar field:
  
  $$
    \rho(\mathbf{r}) = (f\phi(\mathbf{r}) - n(\mathbf{r})),
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

  where $$\mathcal{F}_\mathrm{vol} = \int_{\mathbb{R}^3} d^3 \left(\mathbf{r} \frac{\phi(\mathbf{r})}{N}\mathrm{ln}(\phi(\mathbf{r})) + (1-\phi(\mathbf{r})\mathrm{ln}(1-\phi(\mathbf{r})) + \chi \phi(\mathbf{r})^2\right)$$.

This theme supports rendering beautiful math in inline and display modes using [MathJax 3](https://www.mathjax.org/) engine. You just need to surround your math expression with `$$`, like `$$ E = mc^2 $$`. If you leave it inside a paragraph, it will produce an inline expression, just like $$ E = mc^2 $$.

To use display mode, again surround your expression with `$$` and place it as a separate paragraph. Here is an example:

$$
\sum_{k=1}^\infty |\langle x, e_k \rangle|^2 \leq \|x\|^2
$$

You can also use `\begin{equation}...\end{equation}` instead of `$$` for display mode math.
MathJax will automatically number equations:

\begin{equation}
\label{eq:cauchy-schwarz}
\left( \sum_{k=1}^n a_k b_k \right)^2 \leq \left( \sum_{k=1}^n a_k^2 \right) \left( \sum_{k=1}^n b_k^2 \right)
\end{equation}

and by adding `\label{...}` inside the equation environment, we can now refer to the equation using `\eqref`.

Note that MathJax 3 is [a major re-write of MathJax](https://docs.mathjax.org/en/latest/upgrading/whats-new-3.0.html) that brought a significant improvement to the loading and rendering speed, which is now [on par with KaTeX](http://www.intmath.com/cg5/katex-mathjax-comparison.php).
