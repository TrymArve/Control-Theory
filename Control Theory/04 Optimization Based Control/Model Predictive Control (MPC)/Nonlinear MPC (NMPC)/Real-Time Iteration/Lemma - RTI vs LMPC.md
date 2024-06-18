---
tags:
  - Optimization/NMPC/RTI
  - Optimization/LMPC
Note Author:
  - Trym A. Gabrielsen
Theory Author:
  - Sébastien Gros
Reviewed By:
---
If:
- in an [[Gros ~ RTI|RTI]] scheme
	- [[Gauss-Newton Hessian Approximation]] is used
		- $H_{j}^{i} = W^{i}_{j}$
	- the initial guess *(/previous solution)* is the reference
		- $(x^{i-1*},u^{i-1*})=(x^{ref,i},u^{ref,i})$

Then:
- the RTI scheme delivers the same solution as an [[Gros ~ LMPC|LMPC]] scheme

