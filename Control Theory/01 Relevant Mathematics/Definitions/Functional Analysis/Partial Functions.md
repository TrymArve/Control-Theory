---
tags: []
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
A *partial function* is a [[Function]], except that it doe's not necessarily have to define an image for every element of it's domain.

**Definition:**
A *partial function* with domain $\mathbb{X}$ and codomain $\mathbb{Y}$; $$f:\mathbb{X}\mapsto \mathbb{Y}$$is a [[Binary Relation]] over $\mathbb{X}$ and $\mathbb{Y}$, that satisfies:
- $(x,y)\in f \wedge (x,z)\in f \implies y=z$


---
**Natural Domain / Domain of Definition**
The set $\mathbb{\tilde{X}} \subset \mathbb{X}$ such that $$\mathbb{\tilde{X}} = \{x\in \mathbb{X} ~|~ f(x) \in \mathbb{Y}\}$$ is called the "natural domain" or the "domain of definition".
