---
layout: two-cols-header
---

# Graph theory

::left::

## Undirected graphs

<div class="h-full flex items-center justify-center">
<div class="grid grid-cols-1 grid-rows-2">

```mermaid
graph LR
%%{init: {'theme':'neutral'}}%%
  X_1(("$$X_1$$")) e1@--- X_2(("$$X_2$$"))
  X_3(("$$X_3$$")) --- X_2
  X_4(("$$X_4$$")) --- X_3
  X_4 --- X_2

  e1@{ animate: true}
  linkStyle 0 stroke:red
  classDef highlight stroke:blue,stroke-width:2px;
    class X_3 highlight;
    class X_2 highlight;
  classDef highlight_green stroke:green,stroke-width:2px;
    class X_4 highlight_green;
```

$$
\begin{align*}
G &= \{V, E\}\\
V &= \{X_1, X_2, X_3, X_4\}\\
E &= \left\{  \{X_1, X_2\}, \{X_2, X_3\}, \{X_3, X_4\}, \{X_2, X_4\} \right\}\\
\color{red}{X_1} & \, \color{red}{\sim_{G} X_2}\\
\mathcal{N}_{G}(\color{green}{X_4}\color{black}{)} &= \color{blue}{\{X_2, X_3\}}
\end{align*}
$$
</div>
</div>

::right::

## Directed graphs

<div class="h-full flex items-center justify-center">
<div class="grid grid-cols-1 grid-rows-2">

```mermaid
graph LR
%%{init: {'theme':'neutral'}}%%
  X_1(("$$X_1$$")) --> X_2(("$$X_2$$"))
  X_3(("$$X_3$$")) --> X_2
  X_4(("$$X_4$$")) --> X_3
  X_4 --> X_2

  classDef highlight stroke:blue,stroke-width:2px;
    class X_1 highlight;
    class X_3 highlight;
    class X_4 highlight;
  classDef highlight_green stroke:green,stroke-width:2px;
    class X_2 highlight_green;
```

$$
\begin{align*}
G &= \{V, E\}\\
V &= \{X_1, X_2, X_3, X_4\}\\
E &= \{(X_1, X_2), (X_3, X_2), (X_4, X_3), (X_4, X_2)\}\\
\mathcal{P}_{G}(\color{green}{X_2}\color{black}{)} &= \color{blue}{\{X_1, X_3, X_4\}}
\end{align*}
$$

</div>
</div>