---
tags:
  - NonlinearSystems/Definition
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
**NB!** "Lipschitz Continuous" is the full name, and we often only say "Lipschitz", as done here.

**Note:** 
- The notion of "Locally Lipschitz" can be understood as a property of a function at a point in the domain, and and a property of a subset of the domain.
- Saying that a function is "Locally Lipschitz on $\mathbb{D}$" is short-hand for saying that the function is locally Lipschitz at all points in $\mathbb{D}$.

# Locally Lipschitz "at $(t_\circ,x_\circ)$"
A function $f:\mathbb{R}\times\mathbb{R}^n\mapsto\mathbb{R}^m$ is **(Locally) Lipschitz at $(t_\circ,x_\circ)$**  iff:
- $\exists~L$ :     *(a constant $L$ that is independent of $(t,x)$ )*
	- $\forall~(t,x)\in\mathcal{N}_\circ$  (where $\mathcal{N}_\circ$ is a neighborhood of $(t_\circ,x_\circ)$)
		- $||f(t,x) - f(t_{\circ},x_{\circ})||_p \leq L||(t,x)-(t_\circ,x_\circ)||_p$

# Locally Lipschitz (on domain)
A function $f:\mathbb{R}^n\mapsto\mathbb{R}^{m}$ is **Locally Lipschitz** (not at a specific point) on $\mathbb{D}\subseteq\mathbb{R}^n$ iff:
- $\forall~x_\circ\in\mathbb{D}$
	- $f$ is locally Lipschitz at $x_\circ$


%% OLD DEFINITION: (its equivalent)
# (Globally) Lipschitz (on domain)
A function $f:\mathbb{R}^n\mapsto\mathbb{R}^{m}$ is **(Globally) Lipschitz** iff:
- $\exists~L$ :     *(a constant $L$ that is independent of the set $\mathbb{K}$ )*
	- $\forall~\mathbb{K}\subset\mathbb{R}^n$  : $\mathbb{K}$ is compact
		- $||f(x) - f(y)||_p \leq L||x-y||_p~, \quad \forall x,y \in\mathbb{K}$

%%
# (Globally) Lipschitz (on domain)
A function $f:\mathbb{R}^n\mapsto\mathbb{R}^{m}$ is **(Globally) Lipschitz** iff:
- $\exists~L$ :
	- $\forall x,y \in\mathbb{R}^{n}$
		- $||f(x) - f(y)||_p \leq L||x-y||_p$

**Note:** 
- When only specifying "Lipschitz", we mean "Globally Lipschitz".
- By default, a function is Lipschitz in all parameters/dimensions, with the same Lipschitz constant.
- To specify Lipschitz Continuity in a specific argument, add "in x", or say that $f(t,\cdot)$ is Lipschitz for all t.

