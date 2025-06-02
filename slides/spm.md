---
layout: two-cols-header
---

# Structured probabilistic models

- Multivariate systems
- Joint probability distribution representation
- Conditional (in)dependence assumptions encoded by the structure
- Factorization

::left::

## Markov random fields (MRFs)

<div class="h-full flex items-center justify-center">
<div class="grid grid-cols-2">

```mermaid
---
title: 2-clique
---
graph LR
%%{init: {'theme':'neutral'}}%%
  X(("$$X$$")) --- Y(("$$Y$$"))
```

```mermaid
---
title: 3-clique
---
graph LR
%%{init: {'theme':'neutral'}}%%
  Z(("$$Z$$")) --- X(("$$X$$"))
  Z --- Y(("$$Y$$"))
  X --- Y
```
</div>
</div>

::right::

## Bayesian networks (BNs)

<div class="h-full flex items-center justify-center">
<div class="grid grid-cols-3">
```mermaid
---
title: Pipe
---
graph TD
%%{init: {'theme':'neutral'}}%%
  X(("$$X$$")) --> Z(("$$Z$$"))
  Z --> Y(("$$Y$$"))
```

```mermaid
---
title: Fork
---
graph TD
%%{init: {'theme':'neutral'}}%%
   Z(("$$Z$$")) --> X(("$$X$$"))
  Z --> Y(("$$Y$$"))
```

```mermaid
---
title: Collider
---
graph TD
%%{init: {'theme':'neutral'}}%%
  X(("$$X$$")) --> Z(("$$Z$$"))
  Y(("$$Y$$")) --> Z
```
</div>
</div>