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
- $x = 0$ is an equilibrium of $\Sigma_\circ$
-  on a domain $\mathbb{B}_{<r} = \{x\in\mathbb{R}^{n_x}\big|~ ||x||_2 < r\}$
	- $f:[0,\infty\rangle\times\mathbb{B}_{<r}\mapsto\mathbb{R}^{n_x}$ is 
		- continuously differentiable
	- $\frac{\partial f}{\partial x}$ is
		- [[Boundedness|bounded]] [[Uniform Boundedness|uniformly]] in $t$
- $\exists~(\beta\in\mathcal{KL} ,\quad r_0>0 ):$
	- $\beta(r_0,0) <r$
	- $||x^\circ|| \leq \beta(||x_\circ||,t-t_\circ) \quad \forall~(x_\circ \in \mathbb{B}_{<r_0},~t\geq t_\circ >0)$    *([[Lyapunov Stability#Asymptotic Stability (AS)|asymptotically stable]])*
then:
- $\exists~V:\mathbb{R}_+\times\mathbb{B}_{<r_0}\mapsto\mathbb{R}$ 
- $\exists~\alpha_{1,2,3,4}\in \mathcal{K}$ defined on $[0,r]$
such that
$$
\begin{gather}
\alpha_1(||x||) \leq V(t,x) \leq \alpha_2(||x||) \\[0.3cm]
\frac{\partial V}{\partial t} + \frac{\partial V}{\partial x}f(t,x) \leq -\alpha_3(||x||)\\[0.3cm]
\Bigg|\Bigg|\frac{\partial V}{\partial x}\Bigg|\Bigg|\leq \alpha_4(||x||)
\end{gather}
$$
Moreover, if the system is autonomous/time-invariant, then $V$ can be chosen to be independent of $t$.

