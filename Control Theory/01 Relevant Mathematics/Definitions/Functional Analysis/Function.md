---
tags: []
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
A *function* is a mathematical object that assign exactly one element of an output [[Set|set]] $\mathbb{Y}$, to each element of an input  [[Set|set]] $\mathbb{X}$.


**Definition:**
A *function* with domain $\mathbb{X}$ and codomain $\mathbb{Y}$; $$f:\mathbb{X}\mapsto \mathbb{Y}$$is a [[Binary Relation]] over $\mathbb{X}$ and $\mathbb{Y}$, that satisfies:
- $\exists y\in \mathbb{Y}: (x,y) \in f, \quad \forall x\in \mathbb{X}\quad$ *("total" condition)* 
- $(x,y)\in f \wedge (x,z)\in f \implies y=z\quad$ 


---

### Terminology
**Domain:** The set $\mathbb{X}$, for which all elements are assigned some value in $\mathbb{Y}$.

**Image:**
- **... of an element in the domain; $x\in \mathbb{X}$,** is the element $f(x)$
- **... of a subset of the domain; $\mathbb{\tilde{X}}\subset \mathbb{X}$,** is the set of elements $$\mathbb{\tilde{M}} = \{ ~ f(x) ~|~ x\in \mathbb{\tilde{X}} ~\}$$- **... of a function $f$,** is the set of all elements that are mapped to by the function; $$\mathbb{M} = \{~f(x) ~|~ x\in \mathbb{X}~\}$$

**Codomain:** A set $\mathbb{Y}$, whose elements *may* be assigned to elements of $\mathbb{X}$.
- Note that the set $\mathbb{Y}$ is usually simply defined, but any set $\mathbb{Y}$ such that the image is a subset; $$\mathbb{M} \subseteq \mathbb{Y} $$ is a codomain.

**Preimage:** The subset of the domain; $\mathbb{\tilde{X}}\subseteq \mathbb{X}$, such that all $$\mathbb{\tilde{X}} = \{x\in \mathbb{X} ~|~ f(x) \in \mathbb{\tilde{M}}\}$$
- The preimage is defined similarly to the image; ... of an element, ... of a subset, ... of the image.

**Range:** is ambiguously used to refer to either the codomain or the image of a function



**Remarks:**
- It is common to denote a function by a symbol, often $f$.
- The assigned value from the output set $\mathbb{Y}$ to a given element of the input set; $x\in \mathbb{X}$, is often denoted $f(x)$. (such that  $f(x) \in \mathbb{Y}$)
- The notation $$x\mapsto f(x)$$ is used to mean "$x$ maps to $f(x)$"
- One may use this notation, to avoid naming the function; $x\mapsto x^{2}\sin(x)$
- A function is also referred to as a "total function", to distinguish it from a [[Partial Functions|partial function]]

