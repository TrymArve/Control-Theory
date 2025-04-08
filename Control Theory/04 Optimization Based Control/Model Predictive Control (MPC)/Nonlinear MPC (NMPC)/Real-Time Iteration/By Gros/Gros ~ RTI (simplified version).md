---
tags:
  - Optimization/NMPC/RTI
Note Author:
  - Trym A. Gabrielsen
Theory Author:
  - Sébastien Gros
Reviewed By:
---
This is only a simplified version of the [[Gros ~ RTI|RTI]] algorithm by Gros (originally by [[Real Time Iterations (RTI)|Diehl]]), with the purpose of explaining the concept before the full RTI algorithm is explained.

This algorithm is an adjustment of [[Gros ~~ SQP-NMPC Algorithm]].

---
# $\text{RTI}^{i}_{\text{simple}}(\hat{x}_{i},\tilde{x}^{i-1*},\tilde{u}^{i-1*},x^{ref,i},u^{ref,i}) \triangleq$

1) $\text{Shift Previous Solution:}$  *(see [[Shifting Procedure]])* 
	- $\tilde{x}^{i,g_{0}} = \{\tilde{x}^{i-1*}_{1,\dots,H_{i}}~,~~\tilde{x}^{i}_{>H_{i-1}}\}$
	- $\tilde{u}^{i,g_{0}} = \{\tilde{u}^{i-1*}_{1,\dots,H_{i}-1}~,~~\tilde{u}^{i}_{>H_{i-1}-1}\}$
1) $\text{Do Once:}$ 
	1) $\text{Evaluate at}~(x^{i,g_{0}},u^{i,g_{0}}):$ *([[Gros ~~ QP-NMPC Linearizations|linearize]], [[Gros ~~ QP-NMPC Correction Terms|correction]])*
		- $r^{i}_{j},\quad h^{i}_{j}$
		- $A^{i}_{j},\quad B^{i}_{j}$
		- $C^{i}_{j},\quad D^{i}_{j}$
		- $J^{i}_{j}, \quad H^{i}_{j}$
	1) $\text{Construct and Solve:}$
		- $(\Delta x^{i}, \Delta u^{i})_{0} = \text{QP}^{i}_{\text{NMPC}}(\hat{x}_{i},\tilde{x}^{i,g_{0}},\tilde{u}^{i,g_{0}},x^{ref,i},u^{ref,i})$
	2) $\text{Use Full Steps:}$
		- $\alpha=1$
	3) $\text{Update Guess:}$
		- $(\tilde{x}^{i,g_{1}},\tilde{u}^{i,g_{1}}) = (\tilde{x}^{i,g_{0}},\tilde{u}^{i,g_{0}}) + \alpha(\Delta x^{i}, \Delta u^{i})$
2) $\text{Return:} ~~ (\tilde{x}^{i,g_{1}},\tilde{u}^{i,g_{1}})$

---
**Inputs:**
- $\hat{x}_{i}$ - estimate of current system state
- $(\tilde{x}^{i-1*},\tilde{u}^{i-1*})$ - the previous NMPC-NLP solution (or estimate thereof)
- $(x^{ref,i},u^{ref,i})$ - reference trajectory on current horizon

**Remarks:**
- There are three main differences from the [[Gros ~~ SQP-NMPC Algorithm|SQP-NMPC Algorithm]];
	- The initial guess is assumed to be the previous solution, thus there is a shifting procedure, to adjust the guess at the start of the algorithm.
	- Only one iteration is performed, equivalent to the [[Gros ~~ SQP-NMPC Algorithm|SQP-NMPC Algorithm]] being called with $k_{max}=1$.
	- There is no line search, and the full Newton step is always used.
- The linearized system dynamics and constraints are evaluated at the shifted initial guess, rather that at the new state estimate; that is
	- at: $x^{i-1*}_{1}$
		- which is derived from the previous state estimate; $\hat{x}_{i-1}$, and the previous linearization of the system.
	- rather that at: $\hat{x}_{i}$
		- which is the newest state estimate
	this is called [[Initial Value Embedding]]
