# Basic Optimization Notation
- $\phi(\cdot)$ - objective/cost function
	- not $f$, to distinguish from dynamic constraints
- $z$ - decision/optimization variable
	- not $x$, to distinguish from state variables in dynamic opt.problems
	- $z^*$  -  used to denote a [[Solution]]
	- $z^{**}$  - used to specify a [[Solution#Global Solution|global solution]]
	- $z^{***}$ - used to specify a [[Solution#Unique Solution|unique solution]]
- $\mathcal{L}$ - [[Lagrangian]]
- $\lambda$ - Lagrangian multipliers for equality constraints
	- $\bar{\lambda}$ - to specify equality constraints
	- $\hat{\lambda}$ - to specify inequality constraints
	- Unless otherwise specified, we use $\lambda^{\top} \triangleq [\bar{\lambda}^{\top}, \hat{\lambda}^{\top}]$
- $g(\cdot)$ - equality constraints
- $h(\cdot)$ - inequality constraints ($h(\cdot) \geq 0$)

## LP/QP Specific
- 