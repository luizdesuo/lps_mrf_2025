---
layout: two-cols-header
---

# How expressive are Markov random fields?

::left::

## Markov random fields

<div class="h-full flex items-center justify-center">
<div class="grid grid-rows-2">

```mermaid
---
title: Diamond-shaped
---
graph LR
%%{init: {'theme':'neutral'}}%%
  X(("$$X$$")) --- Y(("$$Y$$"))
  X --- Z(("$$Z$$"))
  Z --- W(("$$W$$"))
  Y --- W
```

$$
\begin{align*}
X & \!\perp\!\!\!\perp W \mid Y, Z\\
Y & \!\perp\!\!\!\perp Z \mid X, W\\
\end{align*}
$$
</div>
</div>

::right::

## Bayesian networks

<div class="h-full flex items-center justify-center">
<div class="grid grid-cols-2 grid-rows-2">
```mermaid
---
title: From X to W
---
graph LR
%%{init: {'theme':'neutral'}}%%
  X(("$$X$$")) --> Y(("$$Y$$"))
  X --> Z(("$$Z$$"))
  Z --> W(("$$W$$"))
  Y --> W
```

```mermaid
---
title: From Y to Z
---
graph LR
%%{init: {'theme':'neutral'}}%%
  Y(("$$Y$$")) --> X(("$$X$$"))
  X --> Z(("$$Z$$"))
  W(("$$W$$")) --> Z
  Y --> W
```

$$
\begin{align*}
X & \!\perp\!\!\!\perp W \mid Y, Z\\
Y & \not\!\perp\!\!\!\perp Z \mid X, W\\
\end{align*}
$$

$$
\begin{align*}
X & \not\!\perp\!\!\!\perp W \mid Y, Z\\
Y & \!\perp\!\!\!\perp Z \mid X, W\\
\end{align*}
$$
</div>
</div>