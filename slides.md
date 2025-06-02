---
theme: apple-basic
layout: intro
title: Markov Random Fields
---

# Markov Random Fields

Signal Processing Laboratory (University of São Paulo)

<div class="absolute bottom-10">
  <div class="font-700">
    Luiz Desuó Neto<br>
    Prof. Carlos Dias Maciel<br>
    <span class="text-sm mt-2 block">2025</span>
  </div>
</div>

---
layout: default
---

# Content

- Introduction
- Graph theory basics
- Gibbs distribution
- Markov properties
- Structured probabilistic models
- Brief comparison with Bayesian networks
- Joint probability distribution factorization and computational intractability
- Besag's approximation
- Decomposable structures
- Gaussian Markov random fields
- Directions

---
src: ./slides/intro.md
---

---
src: ./slides/graph_theory.md
---

---

# Boltzmann-Gibbs distribution

$$
\begin{equation*}
p(x) = \frac{1}{Z_T} \exp\left(- \frac{1}{T} U(x)\right)
\end{equation*}
$$

- $Z_T$: partition function
- $T$: temperature
- $U(x)$: energy

The energy function $U$ is said to derive from the potential $\{V_{\mathcal{C}}(x)\}_{\mathcal{C} \subset \mathscr{V}}$ if

$$
\begin{equation*}
U(x) = \sum_{\mathcal{C}} V_{\mathcal{C}}(x)
\end{equation*}
$$

**Example:** $\mathbf{X} \sim \textsf{multivariate normal}(\boldsymbol{\boldsymbol{\Sigma}\Gamma}, \boldsymbol{\Sigma})$

$$
\begin{equation*}
U(\mathcal{C} \mid \bm{\theta}_\mathcal{C}) = \frac{1}{2}\left[\sum_{X_i \in \mathcal{C}} \frac{|\mathcal{C}|}{|\mathcal{N}_{\mathscr{G}}(X)|}\mathbf{\Sigma}_{ii}^{-1}x_i^2 - \gamma_i x_i\right] + \left[\sum_{X_i, X_j \in \mathcal{C} \colon i \neq j} x_i \mathbf{\Sigma}_{ij}^{-1} x_j\right]
\end{equation*}
$$

---
src: ./slides/markov_properties.md
---

---
layout: center
---

# Hammersley–Clifford theorem

## Every Gibbs system is Markovian.

---
src: ./slides/spm.md
---

---
layout: center
---

# Can Bayesian networks and Markov random fields represent the same dependency structures?

Clearly no! [(Pearl, 1988)](https://doi.org/10.1016/C2009-0-27609-4)

---
src: ./slides/expressiveness_mrf.md
---

---
src: ./slides/expressiveness_bn.md
---

---
src: ./slides/factorization_mrf_bn.md
---

---
src: ./slides/besag.md
---

---
src: ./slides/decomposable.md
---

---
src: ./slides/gaussian.md
---

---

# Directions

- GMRFs based on SPDEs [(Lindgren, 2011)](https://doi.org/10.1111/j.1467-9868.2011.00777.x)  
$\tau \, (\kappa^2 - \Delta_{\mathbf{s}})^{\alpha/2} \mathbf{X}(\mathbf{s}) = \mathbf{W}(\mathbf{s}) , \quad \mathbf{s} \in \Omega$
- Gaussian anamorphosis  
$\Phi^{-1} \circ F_i (\cdot)$
- Nonparanormal networks (semiparametric marginal models) [(Liu, 2009)](https://www.jmlr.org/papers/v10/liu09a.html)  
Transelliptical family: $\mathbf{X} \stackrel{d}{=} \bm{\mu} + \xi \mathbf{L}_{\mathbf{\Sigma}} \mathbf{U}$ [(Liu, 2012)](https://proceedings.neurips.cc/paper/2012/hash/af8d1eb220186400c494db7091e402b0-Abstract.html)
- Copula theory  
$p(\mathbf{x}) = c(F(x_1), \ldots, F(x_d)) \prod_{i=1}^d p(x_i)$
- Bayesian hierarchical models [(Desuó, 2025)](https://doi.org/10.1016/j.eswa.2025.127137)
- Special samplers [(Stoehr, 2017)](https://doi.org/10.1080/10618600.2018.1506346)

---
layout: center
---

# Questions?