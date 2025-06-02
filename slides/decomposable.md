---
layout: two-cols-header
---

# Decomposable structures [(Pearl, 1988)](https://doi.org/10.1016/C2009-0-27609-4)

::left::

<div class="h-full flex items-top justify-center">
<div class="grid grid-cols-1 grid-rows-2">

- Requires chordal structures
- Tree assembly
- Product of the distributions of the maximal cliques divided by their predecessor intersections
- Avoids direct partition function computation
- Retains resemblance with the dependency structure
- Exact inference
- Running intersection property

$$
\begin{equation*}
p(\mathbf{x} \mid \boldsymbol{\theta}) = \prod_{\mathcal{C} \in \mathscr{C}} \frac{p(\mathbf{x}_{\mathcal{C}} \mid \boldsymbol{\theta}_{\mathcal{C}})}{p(\mathbf{x}_{\mathcal{C} \cap \mathcal{P}_{\mathscr{T}}(\mathcal{C})} \mid \boldsymbol{\theta}_{\mathcal{C} \cap \mathcal{P}_{\mathscr{T}}(\mathcal{C})})}
\end{equation*}
$$

</div>
</div>

::right::

<v-switch>

<template #1>
<div class="h-full flex items-center justify-center">
<div class="grid grid-cols-1 grid-rows-2">
<div class="grid grid-cols-2 grid-rows-1">

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
p(\mathbf{X}) = \, & p(X_1, X_2, X_3) \, \times \\ & \frac{p(X_2, X_3, X_4)}{p(X_2, X_3)} \, \times \\ & \frac{p(X_3, X_5)}{p(X_3)}
\end{split}
\end{equation*}
$$

</div>

```mermaid
graph LR
%%{init: {'theme':'neutral'}}%%
  %%{init: {'theme':'neutral'}}%%
  C_1(("$$X_1, X_2, X_3$$")) --> C_2(("$$X_2, X_3, X_4$$"))
  C_2 --> C_3(("$$X_3, X_5$$"))
```
</div>
</div>
</template>


<template #2>
<div class="h-full flex items-center justify-center">
<div class="grid grid-cols-1 grid-rows-2">
<div class="grid grid-cols-2 grid-rows-1">

```mermaid
graph TD
%%{init: {'theme':'neutral'}}%%
  X_1(("$$X_1$$")) e1@--- X_2(("$$X_2$$"))
  X_3(("$$X_3$$")) e2@--- X_2
  X_1 e3@--- X_3
  X_4(("$$X_4$$")) --- X_3
  X_4 --- X_2
  X_5(("$$X_5$$")) --- X_3

e1@{ animate: true}
linkStyle 0 stroke:red
e2@{ animate: true}
linkStyle 1 stroke:red
e3@{ animate: true}
linkStyle 2 stroke:red
classDef highlight stroke:red,stroke-width:2px;
  class X_1 highlight;
  class X_2 highlight;
  class X_3 highlight;
```

$$
\begin{equation*}
\begin{split}
p(\mathbf{X}) = \, & \color{red}{p(X_1, X_2, X_3)} \, \color{gray}{\times} \\ & \frac{\color{gray}{p(X_2, X_3, X_4)}}{\color{gray}{p(X_2, X_3)}} \, \color{gray}{\times} \\ & \frac{\color{gray}{p(X_3, X_5)}}{\color{gray}{p(X_3)}}
\end{split}
\end{equation*}
$$

</div>

```mermaid
graph LR
%%{init: {'theme':'neutral'}}%%
  %%{init: {'theme':'neutral'}}%%
  C_1(("$$X_1, X_2, X_3$$")) --> C_2(("$$X_2, X_3, X_4$$"))
  C_2 --> C_3(("$$X_3, X_5$$"))

  classDef highlight stroke:red,stroke-width:2px;
    class C_1 highlight;
```
</div>
</div>
</template>


<template #3>
<div class="h-full flex items-center justify-center">
<div class="grid grid-cols-1 grid-rows-2">
<div class="grid grid-cols-2 grid-rows-1">

```mermaid
graph TD
%%{init: {'theme':'neutral'}}%%
  X_1(("$$X_1$$")) --- X_2(("$$X_2$$"))
  X_3(("$$X_3$$")) e1@--- X_2
  X_1 --- X_3
  X_4(("$$X_4$$")) e2@--- X_3
  X_4 e3@--- X_2
  X_5(("$$X_5$$")) --- X_3

e1@{ animate: true}
linkStyle 1 stroke:red
e2@{ animate: true}
linkStyle 3 stroke:red
e3@{ animate: true}
linkStyle 4 stroke:red
classDef highlight stroke:red,stroke-width:2px;
  class X_2 highlight;
  class X_3 highlight;
  class X_4 highlight;
```

$$
\begin{equation*}
\begin{split}
p(\mathbf{X}) = \, & \color{gray}{p(X_1, X_2, X_3)} \, \color{gray}{\times} \\ & \frac{\color{red}{p(X_2, X_3, X_4)}}{\color{gray}{p(X_2, X_3)}} \, \color{gray}{\times} \\ & \frac{\color{gray}{p(X_3, X_5)}}{\color{gray}{p(X_3)}}
\end{split}
\end{equation*}
$$

</div>

```mermaid
graph LR
%%{init: {'theme':'neutral'}}%%
  %%{init: {'theme':'neutral'}}%%
  C_1(("$$X_1, X_2, X_3$$")) --> C_2(("$$X_2, X_3, X_4$$"))
  C_2 --> C_3(("$$X_3, X_5$$"))

  classDef highlight stroke:red,stroke-width:2px;
    class C_2 highlight;
```
</div>
</div>
</template>

<template #4>
<div class="h-full flex items-center justify-center">
<div class="grid grid-cols-1 grid-rows-2">
<div class="grid grid-cols-2 grid-rows-1">

```mermaid
graph TD
%%{init: {'theme':'neutral'}}%%
  X_1(("$$X_1$$")) --- X_2(("$$X_2$$"))
  X_3(("$$X_3$$")) --- X_2
  X_1 --- X_3
  X_4(("$$X_4$$")) --- X_3
  X_4 --- X_2
  X_5(("$$X_5$$")) --- X_3

classDef highlight stroke:blue,stroke-width:2px;
  class X_2 highlight;
  class X_3 highlight;
```

$$
\begin{equation*}
\begin{split}
p(\mathbf{X}) = \, & \color{gray}{p(X_1, X_2, X_3)} \, \color{gray}{\times} \\ & \frac{\color{red}{p(X_2, X_3, X_4)}}{\color{blue}{p(X_2, X_3)}} \, \color{gray}{\times} \\ & \frac{\color{gray}{p(X_3, X_5)}}{\color{gray}{p(X_3)}}
\end{split}
\end{equation*}
$$

</div>

```mermaid
graph LR
%%{init: {'theme':'neutral'}}%%
  %%{init: {'theme':'neutral'}}%%
  C_1(("$$X_1, X_2, X_3$$")) e1@--> C_2(("$$X_2, X_3, X_4$$"))
  C_2 --> C_3(("$$X_3, X_5$$"))

  e1@{ animate: true}
  linkStyle 0 stroke:blue
  classDef highlight_blue stroke:blue,stroke-width:2px;
    class C_1 highlight_blue;
  classDef highlight stroke:red,stroke-width:2px;
    class C_2 highlight;
```
</div>
</div>
</template>


<template #5>
<div class="h-full flex items-center justify-center">
<div class="grid grid-cols-1 grid-rows-2">
<div class="grid grid-cols-2 grid-rows-1">

```mermaid
graph TD
%%{init: {'theme':'neutral'}}%%
  X_1(("$$X_1$$")) --- X_2(("$$X_2$$"))
  X_3(("$$X_3$$")) --- X_2
  X_1 --- X_3
  X_4(("$$X_4$$")) --- X_3
  X_4 e3@--- X_2
  X_5(("$$X_5$$")) e1@--- X_3

e1@{ animate: true}
linkStyle 5 stroke:red
classDef highlight stroke:red,stroke-width:2px;
  class X_3 highlight;
  class X_5 highlight;
```

$$
\begin{equation*}
\begin{split}
p(\mathbf{X}) = \, & \color{gray}{p(X_1, X_2, X_3)} \, \color{gray}{\times} \\ & \frac{\color{gray}{p(X_2, X_3, X_4)}}{\color{gray}{p(X_2, X_3)}} \, \color{gray}{\times} \\ & \frac{\color{red}{p(X_3, X_5)}}{\color{gray}{p(X_3)}}
\end{split}
\end{equation*}
$$

</div>

```mermaid
graph LR
%%{init: {'theme':'neutral'}}%%
  %%{init: {'theme':'neutral'}}%%
  C_1(("$$X_1, X_2, X_3$$")) --> C_2(("$$X_2, X_3, X_4$$"))
  C_2 --> C_3(("$$X_3, X_5$$"))

  classDef highlight stroke:red,stroke-width:2px;
    class C_3 highlight;
```
</div>
</div>
</template>


<template #6>
<div class="h-full flex items-center justify-center">
<div class="grid grid-cols-1 grid-rows-2">
<div class="grid grid-cols-2 grid-rows-1">

```mermaid
graph TD
%%{init: {'theme':'neutral'}}%%
  X_1(("$$X_1$$")) --- X_2(("$$X_2$$"))
  X_3(("$$X_3$$")) --- X_2
  X_1 --- X_3
  X_4(("$$X_4$$")) --- X_3
  X_4 e3@--- X_2
  X_5(("$$X_5$$")) --- X_3

classDef highlight stroke:blue,stroke-width:2px;
  class X_3 highlight;
```

$$
\begin{equation*}
\begin{split}
p(\mathbf{X}) = \, & \color{gray}{p(X_1, X_2, X_3)} \, \color{gray}{\times} \\ & \frac{\color{gray}{p(X_2, X_3, X_4)}}{\color{gray}{p(X_2, X_3)}} \, \color{gray}{\times} \\ & \frac{\color{red}{p(X_3, X_5)}}{\color{blue}{p(X_3)}}
\end{split}
\end{equation*}
$$

</div>

```mermaid
graph LR
%%{init: {'theme':'neutral'}}%%
  %%{init: {'theme':'neutral'}}%%
  C_1(("$$X_1, X_2, X_3$$")) --> C_2(("$$X_2, X_3, X_4$$"))
  C_2 e1@--> C_3(("$$X_3, X_5$$"))

  e1@{ animate: true}
  linkStyle 1 stroke:blue
  classDef highlight_blue stroke:blue,stroke-width:2px;
    class C_2 highlight_blue;
  classDef highlight stroke:red,stroke-width:2px;
    class C_3 highlight;
```
</div>
</div>
</template>

</v-switch>

---

# Decomposable structures [(Pearl, 1988)](https://doi.org/10.1016/C2009-0-27609-4)

1. **Triangulation:** convert $\mathscr{G}$ into a chordal graph by adding edges to eliminate chordless cycles.
2. **Cliques identification:** extract all maximal cliques from the chordal graph.
3. **Cliques ordering:** assign an ordering to the cliques (e.g., by the highest-indexed node within each clique).
4. **Tree assembly:** connect each clique to a predecessor clique in the ordering that shares the maximal number of nodes.


A **chordal graph** is one in which all cycles of four or more vertices have a chord, which is an edge that is not part of the cycle but connects two vertices of the cycle.