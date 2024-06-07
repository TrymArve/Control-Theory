#Theory/Theorem 
Consider: ![[Consider - Control Affine System#^system]]
Let:
- $\mathbb{D}\subseteq\mathbb{R}^{n_x}$
- $h:\mathbb{D}\mapsto\mathbb{R}$   s.t.
	- $h(x)\geq0 \implies x\in\mathbb{D}$
	- $h\in\mathcal{C}^1$
- $\mathbb{S} =\{x\in\mathbb{R}^{n_x}|h(x)\geq0\} \subseteq \mathbb{D}$
- $\mathbb{K}_{CBF}(x) = \{u\in \mathbb{U}:L_f h(x) + L_g h(x)u \geq -\alpha(h(x))$

If:
- $h$ is a [[Control Barrier Function]] on $\mathbb{D}$
- $\frac{\partial h}{\partial x}\Big|_{x\in\partial\mathbb{S}} \not= 0$
Then
- any controller $u(x)$  s.t.
	- $u(x)$ is [[Lipschitz#(Globally) Lipschitz|Lipschitz continuous]]
	- $u(x) \in \mathbb{K}_{CBF}(x)$
	renders the safe-set; $\mathbb{S}$, safe *(positively invariant)*.
- the set $\mathbb{S}$ is asymptotically stable in $\mathbb{D}$.

