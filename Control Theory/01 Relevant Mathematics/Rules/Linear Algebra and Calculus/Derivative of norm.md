---
tags:
  - NonlinearSystems/Rule
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
Consider: $x \in \mathbb{R}^{n_x}$
**Rule:**
$$\frac{\partial ||x||_2}{\partial x} = \frac{x^\top}{||x||_2}$$

**Intuition:**
![[Derivative of norm.pdf]]
- The change $dx$ to vector $x$ can be decomposed into a parallel part and an orthogonal part
- Only the parallel part is going to contribute to changing the length of the vector
- The vector $\frac{x^{\top}}{||x||}$ is the unit vector in the parallel direction.