---
tags: 
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By: 
Relevant Papers: '"The advanced-step NMPC controller: Optimality, stability and robustness"'
---
**Terminal Cost:**
- $T(\cdot)$ satisfies $T(x) > 0 \quad \forall x\in \mathbb{X}_{T}\setminus \{0\}$

**Local Control Law:**
- $\exists h:\mathbb{X}_{T}\mapsto \mathbb{R}^{n_{u}}:$
	- $\forall x_{k}\in \mathbb{X}_{T}$
		- $f_{d}(x_{k},h(x_{k})) \in \mathbb{X}_{T}$
			- *(invariant terminal set)*
		- $T(f_{d}(x_{k},h(x_{k}))) - T(x_{k}) \leq -L(x_{k},h(x_{k}))$
			- *(using the local control law at the end of the predicted horizon always decreases the cost of the next prediction)*

**Stage Cost:**
- $\exists \alpha_{1,2}\in \mathcal{K}:$
	- $\alpha_{1}(||x||) \leq L(x,u) \leq \alpha_{2}(||x||)$

