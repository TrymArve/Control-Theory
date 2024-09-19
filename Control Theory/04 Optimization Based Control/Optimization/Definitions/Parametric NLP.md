---
tags:
  - Optimization/NLP
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
$$\text{(PNLP):} \qquad  \min_{z\in\mathbb{R}^{n_z}} ~\phi(z,p)\quad s.t. \quad g(z,p) = 0\, , \quad h(z,p) \geq 0$$ ^PNLP


where
- $z\in \mathbb{R}^{n_z}$ is the decision vector
- $p\in \mathbb{R}^{n_p}$ is the decision vector
- $\phi:\mathbb{R}^{n_z}\mapsto\mathbb{R}$ is the cost/objective function
- $g:\mathbb{R}^{n_{z}}\mapsto\mathbb{R}^{n_{eq}}$ is the equality constraint function
- $h:\mathbb{R}^{n_{z}}\mapsto\mathbb{R}^{n_{in}}$ is the inequality constraint function

**Remarks:**
- This is in principle just an [[NLP formulation|NLP]], but when a set of parameters are of particular interest, such as how the solution changes when the parameters change, we tend to but some emphasis on the parameters, resulting in a parametric NLP (PNLP).
