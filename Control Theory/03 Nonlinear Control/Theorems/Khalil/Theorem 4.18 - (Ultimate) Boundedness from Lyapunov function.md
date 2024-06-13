#NonlinearSystems/Theorem 
Consider: ![[Consider - NTV#^system]]
If:
- $\exists~V:\mathbb{R}_+\times\mathbb{D}\subseteq\mathbb{R}^{n_x}\mapsto\mathbb{R}$ 
- $\exists~\alpha_{1,2} \in \mathcal{K}$
- $\exists~W_3:\mathbb{R}^{n_x}\mapsto\mathbb{R}$  that is
	- continuous
	- positive definite
- $\exists ~r>0 ,\mu>0:$
	- $\mathbb{B}_r\subseteq\mathbb{D}$
	- $\mu < \alpha_2^{-1}(\alpha_1(r))$
such that
- $\forall(t,x)\in \mathbb{R}\times\mathbb{D}$
	- $\alpha_1(||x||) \leq V(t,x) \leq \alpha_2(||x||)$
	- $\frac{\partial V(t,x)}{\partial t} + \frac{\partial V(t,x)}{\partial x}f(t,x) \leq -W_3(x) \quad \forall~||x||\geq \mu >0$  
then:
- $\exists~\beta \in \mathcal{KL}$
- $\forall x_\circ: ||x_\circ|| \leq \alpha_2^{-1}(\alpha_1(r))$ 
	- $\exists~T(x_\circ,\mu) \geq 0$
such that the solutions, $x^\circ(t)$, of $\Sigma_\circ$ satisfy
- $||x^\circ(t)|| \leq \beta(||x_\circ||,t-t_\circ) \quad \forall~t_\circ \leq t \leq t_\circ + T(x_\circ,\mu)$      *([[Boundedness#Boundedness|Boundedness]])*
- $||x^\circ(t)|| \leq \alpha_1^{-1}(\alpha_2(\mu)) \quad \forall~t\geq t_\circ + T(x_\circ,\mu)$                   *([[Boundedness#Ultimate Boundedness|Ultimate boundedness]])*





