---
layout: two-cols-header
---

# Besag's approximation [(Besag, 1974)](https://doi.org/10.1111/j.2517-6161.1974.tb00999.x)

::left::

<div class="h-full flex items-top justify-center">
<div class="grid grid-cols-1 grid-rows-2">

- Relaxes fundamental probability axioms
- Product of local conditional probability distributions
- Avoids direct partition function computation
- Retains resemblance with the dependency structure
- Approximation (pseudolikelihood)

$$
\begin{equation*}
p(\mathbf{X} \mid \boldsymbol{\theta}) \approx \prod_{V \in \mathscr{V}} p(x_V \mid \mathcal{N}_{\mathscr{G}}(V); \boldsymbol{\theta}_{X_V \mid \mathcal{N}_{\mathscr{G}}(V)})
\end{equation*}
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
\begin{split}
p(\mathbf{X}) \approx \, & p(X_1 \mid X_2, X_3) p(X_2 \mid X_1, X_3, X_4) \, \times \\ & p(X_3 \mid X_1, X_2, X_4, X_5) \, \times \\ & p(X_4 \mid X_2, X_3) p(X_5 \mid X_3)
\end{split}
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
  X_1 e2@--- X_3
  X_4(("$$X_4$$")) --- X_3
  X_4 --- X_2
  X_5(("$$X_5$$")) --- X_3

e1@{ animate: true}
linkStyle 0 stroke:red
e2@{ animate: true}
linkStyle 2 stroke:red
classDef highlight stroke:red,stroke-width:2px;
  class X_1 highlight;
```

$$
\begin{equation*}
\begin{split}
p(\mathbf{X}) \approx \, & \color{red}{p(X_1 \mid X_2, X_3)} \color{gray}{p(X_2 \mid X_1, X_3, X_4)} \, \color{gray}{\times} \\ & \color{gray}{p(X_3 \mid X_1, X_2, X_4, X_5)} \, \color{gray}{\times} \\ & \color{gray}{p(X_4 \mid X_2, X_3)} \color{gray}{p(X_5 \mid X_3)}
\end{split}
\end{equation*}
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
  X_1(("$$X_1$$")) e1@--- X_2(("$$X_2$$"))
  X_3(("$$X_3$$")) e2@--- X_2
  X_1 --- X_3
  X_4(("$$X_4$$")) --- X_3
  X_4 e3@--- X_2
  X_5(("$$X_5$$")) --- X_3

e1@{ animate: true}
linkStyle 0 stroke:red
e2@{ animate: true}
linkStyle 1 stroke:red
e3@{ animate: true}
linkStyle 4 stroke:red
classDef highlight stroke:red,stroke-width:2px;
  class X_2 highlight;
```

$$
\begin{equation*}
\begin{split}
p(\mathbf{X}) \approx \, & \color{gray}{p(X_1 \mid X_2, X_3)} \color{red}{p(X_2 \mid X_1, X_3, X_4)} \, \color{gray}{\times} \\ & \color{gray}{p(X_3 \mid X_1, X_2, X_4, X_5)} \, \color{gray}{\times} \\ & \color{gray}{p(X_4 \mid X_2, X_3)} \color{gray}{p(X_5 \mid X_3)}
\end{split}
\end{equation*}
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
  X_3(("$$X_3$$")) e1@--- X_2
  X_1 e2@--- X_3
  X_4(("$$X_4$$")) e3@--- X_3
  X_4 --- X_2
  X_5(("$$X_5$$")) e4@--- X_3

e1@{ animate: true}
linkStyle 1 stroke:red
e2@{ animate: true}
linkStyle 2 stroke:red
e3@{ animate: true}
linkStyle 3 stroke:red
e4@{ animate: true}
linkStyle 5 stroke:red
classDef highlight stroke:red,stroke-width:2px;
  class X_3 highlight;
```

$$
\begin{equation*}
\begin{split}
p(\mathbf{X}) \approx \, & \color{gray}{p(X_1 \mid X_2, X_3)} \color{gray}{p(X_2 \mid X_1, X_3, X_4)} \, \color{gray}{\times} \\ & \color{red}{p(X_3 \mid X_1, X_2, X_4, X_5)} \, \color{gray}{\times} \\ & \color{gray}{p(X_4 \mid X_2, X_3)} \color{gray}{p(X_5 \mid X_3)}
\end{split}
\end{equation*}
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
  X_4 e2@--- X_2
  X_5(("$$X_5$$")) --- X_3

e1@{ animate: true}
linkStyle 3 stroke:red
e2@{ animate: true}
linkStyle 4 stroke:red
classDef highlight stroke:red,stroke-width:2px;
  class X_4 highlight;
```

$$
\begin{equation*}
\begin{split}
p(\mathbf{X}) \approx \, & \color{gray}{p(X_1 \mid X_2, X_3)} \color{gray}{p(X_2 \mid X_1, X_3, X_4)} \, \color{gray}{\times} \\ & \color{gray}{p(X_3 \mid X_1, X_2, X_4, X_5)} \, \color{gray}{\times} \\ & \color{red}{p(X_4 \mid X_2, X_3)} \color{gray}{p(X_5 \mid X_3)}
\end{split}
\end{equation*}
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
  X_4 --- X_2
  X_5(("$$X_5$$")) e1@--- X_3

e1@{ animate: true}
linkStyle 5 stroke:red
classDef highlight stroke:red,stroke-width:2px;
  class X_5 highlight;
```

$$
\begin{equation*}
\begin{split}
p(\mathbf{X}) \approx \, & \color{gray}{p(X_1 \mid X_2, X_3)} \color{gray}{p(X_2 \mid X_1, X_3, X_4)} \, \color{gray}{\times} \\ & \color{gray}{p(X_3 \mid X_1, X_2, X_4, X_5)} \, \color{gray}{\times} \\ & \color{gray}{p(X_4 \mid X_2, X_3)} \color{red}{p(X_5 \mid X_3)}
\end{split}
\end{equation*}
$$

</div>
</div>
</template>

</v-switch>