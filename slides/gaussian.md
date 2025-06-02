---
layout: two-cols-header
---

# Gaussian Markov random fields [(Rue, 2005)](https://doi.org/10.1201/9780203492024)

::left::

<div class="h-full flex items-top justify-center">
<div class="grid grid-cols-1 grid-rows-2">

- Avoids direct partition function computation (normalized by definition)
- Exploits the sparsity of the precision matrix
- Pairwise Markov property (precision operator)
- Closed under marginalization and conditioning
- Implicit none tail dependence
- Gaussian marginals

$$
\begin{align*}
\mathbf{X} &\sim \textsf{multivariate normal}(\boldsymbol{\mu}, \boldsymbol{\Sigma})\\
\mathbf{\Sigma}_{ij}^{-1} & \neq 0 \iff X_i \sim_{\mathscr{G}} X_j \colon \forall i, j \in \mathscr{V}\\
X_i &\!\perp\!\!\!\perp X_j \mid \mathbf{X}_{-ij} \iff \mathbf{\Sigma}_{ij}^{-1} = 0
\end{align*}
$$

</div>
</div>

::right::

<v-switch>
<template #1>
<div class="h-full flex items-center justify-center">
<div class="grid grid-cols-1 grid-rows-2">

```mermaid
graph TD
%%{init: {'theme':'neutral'}}%%
  X_1(("$$X_1$$")) --- X_2(("$$X_2$$"))
  X_3(("$$X_3$$")) --- X_2
  X_1 --- X_3
  X_4(("$$X_4$$")) --- X_3
  X_4 --- X_2
  X_5(("$$X_5$$")) --- X_3
```

$$
\begin{equation*}
\mathbf{\Sigma}^{-1}=\begin{bmatrix}\ast & \ast & \ast & 0 & 0 \\ \ast & \ast & \ast & \ast & 0 \\ \ast & \ast & \ast & \ast & \ast \\ 0 & \ast & \ast & \ast & 0 \\ 0 & 0 & \ast & 0 & \ast\end{bmatrix}
\end{equation*}
$$

</div>
</div>
</template>


<template #2>
<div class="h-full flex items-center justify-center">
<div class="grid grid-cols-1 grid-rows-2">

```mermaid
graph TD
%%{init: {'theme':'neutral'}}%%
  X_1(("$$X_1$$")) e1@--- X_2(("$$X_2$$"))
  X_3(("$$X_3$$")) --- X_2
  X_1 --- X_3
  X_4(("$$X_4$$")) --- X_3
  X_4 --- X_2
  X_5(("$$X_5$$")) --- X_3

  e1@{ animate: true}
  linkStyle 0 stroke:red
  classDef highlight stroke:red,stroke-width:2px;
    class X_1 highlight;
    class X_2 highlight;
  classDef highlight_blue stroke:blue,stroke-width:2px;
    class X_3 highlight_blue;
    class X_4 highlight_blue;
    class X_5 highlight_blue;
```

$$
\begin{align*}
\mathbf{\Sigma}^{-1}&=\begin{bmatrix}\color{gray}{\ast} & \color{red}{\ast} & \color{gray}{\ast} & \color{gray}{0} & \color{gray}{0} \\ \color{red}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{0} \\ \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} \\ \color{gray}{0} & \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{0} \\ \color{gray}{0} & \color{gray}{0} & \color{gray}{\ast} & \color{gray}{0} & \color{gray}{\ast}\end{bmatrix}\\
&\color{red}{X_1} \, \color{black}{\not\!\perp\!\!\!\perp} \, \color{red}{X_2} \, \color{black}{\mid} \,\color{blue}{X_3, X_4, X_5}
\end{align*}
$$

</div>
</div>
</template>


<template #3>
<div class="h-full flex items-center justify-center">
<div class="grid grid-cols-1 grid-rows-2">

```mermaid
graph TD
%%{init: {'theme':'neutral'}}%%
  X_1(("$$X_1$$")) --- X_2(("$$X_2$$"))
  X_3(("$$X_3$$")) e1@--- X_2
  X_1 --- X_3
  X_4(("$$X_4$$")) --- X_3
  X_4 --- X_2
  X_5(("$$X_5$$")) --- X_3

  e1@{ animate: true}
  linkStyle 1 stroke:red
  classDef highlight stroke:red,stroke-width:2px;
    class X_2 highlight;
    class X_3 highlight;
  classDef highlight_blue stroke:blue,stroke-width:2px;
    class X_1 highlight_blue;
    class X_4 highlight_blue;
    class X_5 highlight_blue;
```

$$
\begin{align*}
\mathbf{\Sigma}^{-1}&=\begin{bmatrix}\color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{0} & \color{gray}{0} \\ \color{gray}{\ast} & \color{gray}{\ast} & \color{red}{\ast} & \color{gray}{\ast} & \color{gray}{0} \\ \color{gray}{\ast} & \color{red}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} \\ \color{gray}{0} & \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{0} \\ \color{gray}{0} & \color{gray}{0} & \color{gray}{\ast} & \color{gray}{0} & \color{gray}{\ast}\end{bmatrix}\\
&\color{red}{X_2} \, \color{black}{\not\!\perp\!\!\!\perp} \, \color{red}{X_3} \, \color{black}{\mid} \,\color{blue}{X_1, X_4, X_5}
\end{align*}
$$

</div>
</div>
</template>


<template #4>
<div class="h-full flex items-center justify-center">
<div class="grid grid-cols-1 grid-rows-2">

```mermaid
graph TD
%%{init: {'theme':'neutral'}}%%
  X_1(("$$X_1$$")) --- X_2(("$$X_2$$"))
  X_3(("$$X_3$$")) --- X_2
  X_1 e1@--- X_3
  X_4(("$$X_4$$")) --- X_3
  X_4 --- X_2
  X_5(("$$X_5$$")) --- X_3

  e1@{ animate: true}
  linkStyle 2 stroke:red
  classDef highlight stroke:red,stroke-width:2px;
    class X_1 highlight;
    class X_3 highlight;
  classDef highlight_blue stroke:blue,stroke-width:2px;
    class X_2 highlight_blue;
    class X_4 highlight_blue;
    class X_5 highlight_blue;
```

$$
\begin{align*}
\mathbf{\Sigma}^{-1}&=\begin{bmatrix}\color{gray}{\ast} & \color{gray}{\ast} & \color{red}{\ast} & \color{gray}{0} & \color{gray}{0} \\ \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{0} \\ \color{red}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} \\ \color{gray}{0} & \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{0} \\ \color{gray}{0} & \color{gray}{0} & \color{gray}{\ast} & \color{gray}{0} & \color{gray}{\ast}\end{bmatrix}\\
&\color{red}{X_1} \, \color{black}{\not\!\perp\!\!\!\perp} \, \color{red}{X_3} \, \color{black}{\mid} \,\color{blue}{X_2, X_4, X_5}
\end{align*}
$$

</div>
</div>
</template>

<template #5>
<div class="h-full flex items-center justify-center">
<div class="grid grid-cols-1 grid-rows-2">

```mermaid
graph TD
%%{init: {'theme':'neutral'}}%%
  X_1(("$$X_1$$")) --- X_2(("$$X_2$$"))
  X_3(("$$X_3$$")) --- X_2
  X_1 --- X_3
  X_4(("$$X_4$$")) e1@--- X_3
  X_4 --- X_2
  X_5(("$$X_5$$")) --- X_3

  e1@{ animate: true}
  linkStyle 3 stroke:red
  classDef highlight stroke:red,stroke-width:2px;
    class X_3 highlight;
    class X_4 highlight;
  classDef highlight_blue stroke:blue,stroke-width:2px;
    class X_1 highlight_blue;
    class X_2 highlight_blue;
    class X_5 highlight_blue;
```

$$
\begin{align*}
\mathbf{\Sigma}^{-1}&=\begin{bmatrix}\color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{0} & \color{gray}{0} \\ \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{0} \\ \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} & \color{red}{\ast} & \color{gray}{\ast} \\ \color{gray}{0} & \color{gray}{\ast} & \color{red}{\ast} & \color{gray}{\ast} & \color{gray}{0} \\ \color{gray}{0} & \color{gray}{0} & \color{gray}{\ast} & \color{gray}{0} & \color{gray}{\ast}\end{bmatrix}\\
&\color{red}{X_3} \, \color{black}{\not\!\perp\!\!\!\perp} \, \color{red}{X_4} \, \color{black}{\mid} \,\color{blue}{X_1, X_2, X_5}
\end{align*}
$$

</div>
</div>
</template>


<template #6>
<div class="h-full flex items-center justify-center">
<div class="grid grid-cols-1 grid-rows-2">

```mermaid
graph TD
%%{init: {'theme':'neutral'}}%%
  X_1(("$$X_1$$")) --- X_2(("$$X_2$$"))
  X_3(("$$X_3$$")) --- X_2
  X_1 --- X_3
  X_4(("$$X_4$$")) --- X_3
  X_4 e1@--- X_2
  X_5(("$$X_5$$")) --- X_3

  e1@{ animate: true}
  linkStyle 4 stroke:red
  classDef highlight stroke:red,stroke-width:2px;
    class X_2 highlight;
    class X_4 highlight;
  classDef highlight_blue stroke:blue,stroke-width:2px;
    class X_1 highlight_blue;
    class X_3 highlight_blue;
    class X_5 highlight_blue;
```

$$
\begin{align*}
\mathbf{\Sigma}^{-1}&=\begin{bmatrix}\color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{0} & \color{gray}{0} \\ \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} & \color{red}{\ast} & \color{gray}{0} \\ \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} \\ \color{gray}{0} & \color{red}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{0} \\ \color{gray}{0} & \color{gray}{0} & \color{gray}{\ast} & \color{gray}{0} & \color{gray}{\ast}\end{bmatrix}\\
&\color{red}{X_2} \, \color{black}{\not\!\perp\!\!\!\perp} \, \color{red}{X_4} \, \color{black}{\mid} \,\color{blue}{X_1, X_3, X_5}
\end{align*}
$$

</div>
</div>
</template>


<template #7>
<div class="h-full flex items-center justify-center">
<div class="grid grid-cols-1 grid-rows-2">

```mermaid
graph TD
%%{init: {'theme':'neutral'}}%%
  X_1(("$$X_1$$")) --- X_2(("$$X_2$$"))
  X_3(("$$X_3$$")) --- X_2
  X_1 --- X_3
  X_4(("$$X_4$$")) --- X_3
  X_4 --- X_2
  X_5(("$$X_5$$")) e1@--- X_3

  e1@{ animate: true}
  linkStyle 5 stroke:red
  classDef highlight stroke:red,stroke-width:2px;
    class X_3 highlight;
    class X_5 highlight;
  classDef highlight_blue stroke:blue,stroke-width:2px;
    class X_1 highlight_blue;
    class X_2 highlight_blue;
    class X_4 highlight_blue;
```

$$
\begin{align*}
\mathbf{\Sigma}^{-1}&=\begin{bmatrix}\color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{0} & \color{gray}{0} \\ \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{0} \\ \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} & \color{red}{\ast} \\ \color{gray}{0} & \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{\ast} & \color{gray}{0} \\ \color{gray}{0} & \color{gray}{0} & \color{red}{\ast} & \color{gray}{0} & \color{gray}{\ast}\end{bmatrix}\\
&\color{red}{X_3} \, \color{black}{\not\!\perp\!\!\!\perp} \, \color{red}{X_5} \, \color{black}{\mid} \,\color{blue}{X_1, X_2, X_4}
\end{align*}
$$

</div>
</div>
</template>

</v-switch>

---

# Gaussian Markov random fields [(Rue, 2005)](https://doi.org/10.1201/9780203492024)

$$
\begin{equation*}
\ell(\boldsymbol{\theta}) -\frac{d}{2} \log(2\pi) - \frac{1}{2} \log\left(|\mathbf{\Sigma}(\boldsymbol{\theta})|\right) -\frac{1}{2} (\mathbf{x} - \boldsymbol{\mu})^\mathrm{T} \, \mathbf{\Sigma}(\boldsymbol{\theta})^{-1} \, (\mathbf{x} - \boldsymbol{\mu})
\end{equation*}
$$

- $\mathbf{\Sigma}(\boldsymbol{\theta})^{-1}$ is SPD
- Sparse matrices
- Cholesky decomposition $\mathbf{\Sigma} = \mathbf{L}_{\mathbf{\Sigma}} \mathbf{L}_{\mathbf{\Sigma}}^{\mathrm{T}}$
- Split into autoregressive processes