---
tags:
  - NonlinearSystems/Theorem
Note Author:
  - Trym A. Gabrielsen
Theory Author:
  - Hassan K. Kahlil
Reviewed By:
---
Consider: ![[Consider - NTV#^system]]
If:
- $f(t,x)$ is piecewise continuous in $t$
- $\forall~x,y\in\mathbb{R}^{n_x},t\in[t_\circ,t_1]$
	- $||f(t,x) - f(t,y)|| \leq L||x-y||$    *([[Lipschitz]])*
then:
- the state equation of $\Sigma_\circ$ has a unique solution $x^\circ(t)$ on $[t_\circ,t_1]$



**Note:** 
- if the system has a solution on $t\in[t_\circ,\infty\rangle$, the the system is [[Forward Completeness|forward complete]].
	This theorem, with $t_1\rightarrow \infty$, is therefore sufficient to show forward completeness.


