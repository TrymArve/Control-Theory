#Theory/Lemma 
#resources/Lecture/Loria
*A relaxation of [[Lemma 9 - Integration Lemma for uniform asymptotic stability]]*

Consider: ![[Consider - NTV#^system]]
If:
- the origin $x=0$ is [[Lyapunov Stability#Stability (S)|uniformly globally stable]] (UGS)
and
- $\exists~\gamma:\mathbb{R}^{n_x}\mapsto\mathbb{R}_+$
	- that is positive definite
- $\forall r,\nu >0$ 
	- $\exists~\beta_{r\nu} >0:~\forall~(t_\circ\geq0,||x_\circ||\leq r)$
	$$(1):\quad \int_{t_\circ}^{\infty} \bigg( \gamma(x^\circ(t)) -\nu \bigg) ~dt \leq \beta_{r\nu}$$
then
- the origin is [[Lyapunov Stability#Asymptotic Stability (AS)|uniformly globally asymptotically stable]] (UGAS)



# Remarks
- To construct the integral bound (1), we may start with one smooth function:
	- $V_1:\mathbb{R}_+\times\mathbb{R}^{n_x}\mapsto\mathbb{R}$
	and
	- $\alpha_{1,2} \in \mathcal{K}_\infty$
	- $\alpha_3 \in\mathcal{K}$
	such that
	- $\alpha_1(||x||) \leq V_1(t,x) \leq \alpha_2(||x||)$
	- $\dot{V}_1(t,x) = \frac{\partial V}{\partial t} \frac{\partial V}{\partial x}f(t,x) \leq -\alpha_3(||x_1||) \leq 0$   *(note: bounded only $x_1$ )*
- Then one can construct bounds for the remaining states using more functions $V_2,V_3,\dots$ 