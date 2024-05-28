#Theory/Theorem 
#resources/Book/Khalil 
Consider: ![[Consider - NTV#^system]]
If:
- $x = 0$ is an equilibrium of $\Sigma_\circ$
-  on a domain $\mathbb{B}_r = \{x\in\mathbb{R}^{n_x}\big|~ ||x||_2 < r\}$
	- $f:[0,\infty\rangle\times\mathbb{B}_r\mapsto\mathbb{R}^{n_x}$ is 
		- continuously differentiable
	- $\frac{\partial f}{\partial x}$ is
		- [[Boundedness|bounded]] *(uniformly in t)*
		- [[Lipschitz#Locally Lipschitz (on domain)|Lipschitz]] *(uniformly in t)*
then:
$$\text{the origin of $\Sigma_\circ$ is ES  } \Longleftrightarrow \text{  The linearization is ES}$$
where the linearized system is
$$\dot{x} = \frac{\partial f}{\partial x}\Bigg|_{x=0}x$$


