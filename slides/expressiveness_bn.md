---
layout: two-cols-header
---

# How expressive are Bayesian networks?

::left::

## Bayesian networks

<div class="h-full flex items-center justify-center">
<div class="grid grid-cols-1 grid-rows-2">
```mermaid
---
title: Coins and Bell
---
graph TD
%%{init: {'theme':'neutral'}}%%
  C_1(("$$C_1$$")) --> B(("$$B$$"))
  C_2(("$$C_2$$")) --> B
```

$$
\begin{align*}
C_1 & \!\perp\!\!\!\perp C_2 \\
C_1 & \not\!\perp\!\!\!\perp C_2 \mid B\\
\end{align*}
$$
</div>
</div>

::right::

## Markov random fields

<div class="h-full flex items-center justify-center">
<div class="grid grid-cols-2 grid-rows-2">
```mermaid
---
title: Naive
---
graph TD
%%{init: {'theme':'neutral'}}%%
  C_1(("$$C_1$$")) --- B(("$$B$$"))
  C_2(("$$C_2$$")) --- B
```

```mermaid
---
title: Trivial
---
graph LR
%%{init: {'theme':'neutral'}}%%
  C_1(("$$C_1$$")) --- B(("$$B$$"))
  C_2(("$$C_2$$")) --- B
  C_1 --- C_2
```

$$
\begin{align*}
C_1 & \!\perp\!\!\!\perp C_2 \mid B\\
\end{align*}
$$

$$
\begin{align*}
C_1 & \not\!\perp\!\!\!\perp C_2\\
\end{align*}
$$
</div>
</div>