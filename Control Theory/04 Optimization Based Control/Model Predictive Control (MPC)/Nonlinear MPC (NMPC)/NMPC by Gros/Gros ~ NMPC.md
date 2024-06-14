---
tags:
  - Optimization/NMPC
Note Author:
  - Trym A. Gabrielsen
Theory Author:
  - Sébastien Gros
Reviewed By:
---
Notation: [[Optimization#Dynamic Optimization / MPC|here]]
Consider OCP: ![[Optimal Control Problem#^OCP]]

**NMPC Controller**
$$u^{\text{NMPC}}_{i} \triangleq \tilde{u}^{i}_{0} \leftarrow \text{NLP}_{\text{NMPC}}^{i}(\hat{x}_{i},x^{ref,i},u^{ref,i})$$![[Gros ~~ NMPC Formulation#^NLP]]


**Remarks:**
- Note that there are no terminal costs/constraints, but should be present in an implementation
- Note that the cost/objective function may be nonlinear (non-quadratic)
	- this is sometimes preferred
- A neat algorithm for solving the NMPC-NLP problem is described in [[Gros ~ SQP for NMPC]]



