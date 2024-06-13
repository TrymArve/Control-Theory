#NonlinearSystems/Definition 
Consider: ![[Consider - Control Affine System#^system]]
with $f,G$ [[Lipschitz#"$f$ is locally Lipschitz"|locally Lipschitz]].

Let
- $\mathbb{D}\subseteq\mathbb{R}^{n_x}$
- $\mathbb{U}\subseteq\mathbb{R}^{n_u}$     *(permissible inputs)*
- $\mathbb{S}\triangleq\{x\in\mathbb{R}^{n_x}|\geq0\}$
- $h:\mathbb{R}_+\times\mathbb{D}\times\mathbb{U}\mapsto\mathbb{R}$
	- be s.t.
		- $h\in\mathcal{C}^1$
		- $\mathbb{S} \subseteq \mathbb{D}$      *(i.e. the safe set must be entirely contained in the domain.)*
		- $\forall x\in\mathbb{D}$
			- $sign(h(t^0,x,u^0)) = sign(h(t^1,x,u^1))\quad \forall(t^{0,1},u^{0,1})\in\mathbb{R}_+\times U$ 
			- i.e. $\mathbb{S}$ is independent of $(t,u)$

Iff:
- $\exists \alpha \in \mathcal{K}^e_\infty:$       *([[Class K function#Extended-Class $ mathcal{K} e_ infty$|extended class K]])*
	- $\forall x\in\mathbb{D}$
$$\sup_{u\in \mathbb{U}}\big[L_fh(t,x,u) + L_Gh(t,x,u)u\big] \geq -\alpha(h(t,x,u)) \quad \forall~(x,t)\in\mathbb{R}^{n_x}\times\mathbb{R}$$
Then
-  $h$ is a Control Barrier Function (CBF)

