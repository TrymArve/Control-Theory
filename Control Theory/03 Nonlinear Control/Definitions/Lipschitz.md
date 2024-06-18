---
tags:
  - NonlinearSystems/Definition
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---

# Locally Lipschitz "at $(t_\circ,x_\circ)$"
A function $f:\mathbb{R}\times\mathbb{R}^n\mapsto\mathbb{R}^m$ is **(Locally) Lipschitz at $(t_\circ,x_\circ)$**  iff:
- $\exists~L$ :     *(a constant $L$ that is independent of $(t,x)$ )*
	- $\forall~(t,x)\in\mathcal{N}_\circ$  (where $\mathcal{N}_\circ$ is a neighborhood of $(t_\circ,x_\circ)$)
		- $||f(t,x) - f(t,y)||_p \leq L||x-y||_p$


# (Globally) Lipschitz
A function $f:\mathbb{R}^n\mapsto\mathbb{R}^{m}$ is **(Globally) Lipschitz** iff:
- $\exists~L$ :     *(a constant $L$ that is independent of the set $\mathbb{K}$ )*
	- $\forall~\mathbb{K}\subset\mathbb{R}^n$  : $\mathbb{K}$ is compact
		- $||f(x) - f(y)||_p \leq L||x-y||_p~, \quad \forall(x,y)\in\mathbb{K}$

**Note:** If a function is globally Lipschitz in all parameters, we that is is *Lipschitz Continuous*.

# Locally Lipschitz (on domain)
A function $f:\mathbb{R}^n\mapsto\mathbb{R}^{m}$ is **Locally Lipschitz** (not at a specific point) on $\mathbb{D}\subseteq\mathbb{R}^n$ iff:
- $\forall~x_\circ\in\mathbb{D}$
	- $f$ is locally Lipschitz at $x_\circ$


# Locally Lipschitz Continuous
A function $f:\mathbb{R}\times\mathbb{R}^n\mapsto\mathbb{R}^{m}$ is **(Locally) Lipschitz Continuous** in the second argument, uniformly in $t$, iff:
- $\forall~\mathbb{D}\subseteq(\mathbb{R}\times\mathbb{R}^n)$ $$L_{\mathbb{D}} = \sup_{(t,x)\not=(t,y)\in\mathbb{D}} \frac{||f(t,x)-f(t,y)||}{||x-y||} < \infty$$

