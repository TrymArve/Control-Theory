#NonlinearSystems/Theorem 
Consider: ![[Consider - Controlled NTV#^system]]
If:
- $\exists~V:\mathbb{R}_+\times\mathbb{R}^{n_x}\mapsto\mathbb{R}$ 
- $\exists~\alpha_{1,2} \in \mathcal{K}_\infty$
- $\exists~\rho \in \mathcal{K}$
- $\exists~W_3:\mathbb{R}^{n_x}\mapsto\mathbb{R}$  that is
	- continuous
	- positive definite
such that
- $\forall(t,x,u)\in \mathbb{R}\times\mathbb{R}^{n_x}\times\mathbb{R}^{n_u}$
	- $\alpha_1(||x||) \leq V(t,x) \leq \alpha_2(||x||)$
	- $\frac{\partial V(t,x)}{\partial t} + \frac{\partial V(t,x)}{\partial x}f(t,x,u) \leq -W_3(x) \quad \forall~||x||\geq \rho(||u||) >0$  
then:
- system $\Sigma_\circ$ is [[ISS - Input-to-State Stability|Input-to-State Stable]] (ISS)


**Note:**
- The proof uses [[Theorem 4.18 - (Ultimate) Boundedness from Lyapunov function]]


