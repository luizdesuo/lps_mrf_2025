# Markov properties

<v-switch>

<template #1>
<div class="h-full flex items-center justify-center">
<div class="grid grid-cols-1 grid-rows-2">

## Pairwise Markov property

$$
\begin{equation*}
\text{Any} \, X_i \not\sim_{\mathscr{G}} X_j \colon X_i \!\perp\!\!\!\perp X_j \mid \mathbf{X}_{-ij}
\end{equation*}
$$


```mermaid
graph LR
%%{init: {'theme':'neutral'}}%%
  X_1(("$$X_1$$")) --- X_2(("$$X_2$$"))
  X_3(("$$X_3$$")) --- X_2
  X_1 --- X_3
  X_4(("$$X_4$$")) --- X_3
  X_5(("$$X_5$$")) --- X_3
  X_6(("$$X_6$$")) --- X_4
  X_7(("$$X_7$$")) --- X_2

  classDef highlight stroke:red,stroke-width:2px;
    class X_1 highlight;
  classDef highlight_green stroke:green,stroke-width:2px;
    class X_6 highlight_green;
  classDef highlight_blue stroke:blue,stroke-width:2px;
    class X_2 highlight_blue;
    class X_3 highlight_blue;
    class X_4 highlight_blue;
    class X_5 highlight_blue;
    class X_7 highlight_blue;
```

$$
\begin{equation*}
\color{red}{X_1} \, \color{black}{\!\perp\!\!\!\perp} \, \color{green}{X_6} \, \color{black}{\mid} \, \color{blue}{\{X_2, X_3, X_4, X_5, X_7\}}
\end{equation*}
$$

</div>
</div>
</template>

<template #2>
<div class="h-full flex items-center justify-center">
<div class="grid grid-cols-1 grid-rows-2">

## Local Markov property

$$
\begin{equation*}
X \!\perp\!\!\!\perp \mathscr{V} \setminus \mathcal{N}_{\mathscr{G}}[X] \mid \mathcal{N}_{\mathscr{G}}(X)
\end{equation*}
$$


```mermaid
graph LR
%%{init: {'theme':'neutral'}}%%
  X_1(("$$X_1$$")) --- X_2(("$$X_2$$"))
  X_3(("$$X_3$$")) --- X_2
  X_1 --- X_3
  X_4(("$$X_4$$")) --- X_3
  X_5(("$$X_5$$")) --- X_3
  X_6(("$$X_6$$")) --- X_4
  X_7(("$$X_7$$")) --- X_2

  classDef highlight stroke:red,stroke-width:2px;
    class X_2 highlight;
  classDef highlight_green stroke:green,stroke-width:2px;
    class X_6 highlight_green;
    class X_4 highlight_green;
    class X_5 highlight_green;
  classDef highlight_blue stroke:blue,stroke-width:2px;
    class X_1 highlight_blue;
    class X_3 highlight_blue;
    class X_7 highlight_blue;
```

$$
\begin{equation*}
\color{red}{X_2} \, \color{black}{\!\perp\!\!\!\perp} \, \color{green}{\{X_4, X_5, X_6\}} \, \color{black}{\mid} \, \color{blue}{\{X_1, X_3, X_7\}}
\end{equation*}
$$

</div>
</div>

</template>

<template #3>
<div class="h-full flex items-center justify-center">
<div class="grid grid-cols-1 grid-rows-2">

## Global Markov property

$$
\begin{equation*}
\mathbf{X}_A \!\perp\!\!\!\perp \mathbf{X}_B \mid \mathbf{X}_S
\end{equation*}
$$


```mermaid
graph LR
%%{init: {'theme':'neutral'}}%%
  X_1(("$$X_1$$")) --- X_2(("$$X_2$$"))
  X_3(("$$X_3$$")) --- X_2
  X_1 --- X_3
  X_4(("$$X_4$$")) --- X_3
  X_5(("$$X_5$$")) --- X_3
  X_6(("$$X_6$$")) --- X_4
  X_7(("$$X_7$$")) --- X_2

  classDef highlight stroke:red,stroke-width:2px;
    class X_2 highlight;
    class X_7 highlight;
  classDef highlight_green stroke:green,stroke-width:2px;
    class X_6 highlight_green;
    class X_4 highlight_green;
  classDef highlight_blue stroke:blue,stroke-width:2px;
    class X_1 highlight_blue;
    class X_3 highlight_blue;
```

$$
\begin{equation*}
\color{red}{\{X_2, X_7\}} \, \color{black}{\!\perp\!\!\!\perp} \, \color{green}{\{X_4, X_6\}} \, \color{black}{\mid} \, \color{blue}{\{X_1, X_3\}}
\end{equation*}
$$

</div>
</div>

</template>

</v-switch>