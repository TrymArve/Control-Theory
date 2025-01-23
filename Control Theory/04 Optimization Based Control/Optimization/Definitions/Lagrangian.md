---
tags: 
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
consider: ![[NLP formulation#^NLP]]
The Lagrangian is defined *(in this vault)* as:

$$\mathcal{L}(z,\lambda) \triangleq \phi(z) - \sum\limits_{i=1}^{n_{eq}}\bar{\lambda}_{i}g_i(z) - \sum\limits_{i=1}^{n_{in}}\hat{\lambda}_{i}h_i(z) $$ ^Lagrangian

where
- $\lambda^{\top} \triangleq [\bar{\lambda}^{\top}, \hat{\lambda}^{\top}]$
	- these are called the *"Lagrangian multipliers"*

**Remarks:**
- The signs of the constraints terms may vary depending on the particular book/paper, and on the formulation of the inequality constraints.
- The sign of the Lagrange multipliers ([[KKT Conditions (First-Order Necessary Conditions)|dual feasibility]]) will depend on the choice of Lagrangian and the formulation of the inequality constraints.