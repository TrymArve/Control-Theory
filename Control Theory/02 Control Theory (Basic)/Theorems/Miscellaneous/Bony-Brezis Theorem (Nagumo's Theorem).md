#Theory/Theorem 

Let 
- $F$ be a closed subset of a $\mathcal{C}^2$ manifold $M$
- $X$ be a vector field on $M$, which is
	- [[Lipschitz#(Globally) Lipschitz|Lipschitz continuous]]
Then the following conditions are equivalent:
- Every integral curve of $X$ starting in $F$, remains in $F$
- $(X(m),v) \leq 0$ for every exterior normal vector $v$ at a point $m$ in $F$


**In human understandable form, for nonlinear systems theory:**
Let
- $\mathbb{F}\subseteq\mathbb{D}\subseteq\mathbb{R}^{n_x}$ be a closed set   *($\mathbb{R}^{n_x}$ is a twice differentiable manifold)*
- $f:\mathbb{D}\mapsto\mathbb{R}_{n_x}$ be [[Lipschitz#(Globally) Lipschitz|Lipschitz]]
Then,
- iff
	- $(~x^\circ(t) \in \mathbb{F} \quad \forall~t\geq t_\circ~)\quad \forall (t_\circ,x_\circ)\in\mathbb{R}_+\times\mathbb{F}$
		- (where $x^\circ(t)$ is the unique solution to the IVP: $\dot{x} = f(t,x),\quad x(t_\circ) = x_\circ$)
- then
	- ????


# From *"Control Barrier Functions - Theory and Applications"*
Consider: ![[Consider - NTI#^system]]
If:
- $b:\mathbb{R}^{n_x}\mapsto\mathbb{R}$ is
	- smooth
- $\mathcal{C} = \{x\in\mathbb{R}^{n_x}|b(x)\geq0\}$   *(safe set)*
- $\frac{\partial b(x)}{\partial x}\bigg|_{x\in\partial\mathcal{C}}\not=0$ 
Then
- Iff:
	- $\frac{db(x)}{dt}\big|_{x^\circ(t)} \geq 0 \quad \forall x\in \partial\mathcal{C}$
- then
	- $\mathcal{C}$ is positively invariant


