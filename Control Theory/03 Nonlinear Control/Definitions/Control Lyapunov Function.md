#NonlinearSystems/Definition 
Consider: ![[Consider - Control Affine System#^system]]
Iff a function $(t,x,u)\mapsto V(t,x,u)$
- is positive definite in $x$
	- uniformly in $(t,u)$
- is such that$$\inf_{u\in U}[L_fV(t,x,u) + L_GV(t,x,u)u] \leq -\gamma(V(t,x,u)) \quad \forall~(x,t)\in\mathbb{R}^{n_x}\times\mathbb{R}$$
	- where
		- $\gamma\in\mathcal{K}_\infty$  *([[Class K function]])*
		- $U$ is the set of permissible inputs $u$
Then
-  $V$ is a Control Lyapunov Function (CLF)

