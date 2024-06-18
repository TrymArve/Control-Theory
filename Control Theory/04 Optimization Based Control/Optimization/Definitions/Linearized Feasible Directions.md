---
tags: 
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
The set of Linearized Feasible Directions; $\vec{\mathbb{F}}$, is a set of vectors defined w.r.t. a feasible set $\mathbb{F}$, and is defined at a feasible point $z'\in \mathbb{F}$.

$$\vec{\mathbb{F}}(z') \triangleq \left\{d\in \mathbb{R}^{n_{z}} ~\bigg| \quad\begin{aligned} d^{\top}\nabla g_{i}(z')=0, & \quad \forall i \in \mathbb{A}_{eq} \\ d^{\top}\nabla h_{i}(z')\geq0, & \quad\forall i \in \mathbb{A}_{in} \end{aligned} \right\}$$

**Remarks:**
- The Linearized Feasible Directions are defined in terms of the algebraic specification of the [[Feasible Set]], and not by the geometry, as is the case for the [[Tangent Cone]].