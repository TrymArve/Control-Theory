---
tags:
  - NonlinearSystems/Definition
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---

A function $\alpha:[0,a\rangle\mapsto[0,\infty\rangle$ is said to be **class $\mathcal{K}$** iff:
- it is strictly increasing
- $\alpha(0) = 0$



**Note:**
- "strictly increasing" means:
	- $x<y \implies \alpha(x) < \alpha(y) \quad\forall x,y\in[0,a\rangle$   *(correct)*
	and not
	- $\alpha'(x)>0 \quad\forall x\in[0,a\rangle$    *(not correct)*
- This means that the quadratic function is a class $K$ function:
	- $f(x) = x^2 \quad \in\mathcal{K}$
	even though
	- $f'(x) = x \implies f'(0)=0$
- In fact:
	- $f(x) = x^n\in \mathcal{K},\quad \forall~n\geq1$



## Class $\mathcal{K}_\infty$ function
A function $\alpha$ is said to be class $\mathcal{K}_\infty$ iff:
- $\alpha$ is class $\mathcal{K}$ with $a=\infty$
- $r \rightarrow \infty \implies \alpha(r) \rightarrow \infty$


# Extended-Class $\mathcal{K}^e$
A function $\alpha:\langle a_0,a\rangle\mapsto[0,\infty\rangle$ is said to be an extended class $\mathcal{K}$ ($\mathcal{K}^e$)function iff:
- it is strictly increasing
- $\alpha(0) = 0$

## Extended-Class $\mathcal{K}^e_\infty$
A function $\alpha$ is said to be extended class $\mathcal{K}_\infty$ ($\mathcal{K}^e_\infty$) iff:
- $\alpha$ is extended class $\mathcal{K}$ with $a_0,a=\infty$
- $r \rightarrow \infty \implies \alpha(r) \rightarrow \infty$
- $r \rightarrow -\infty \implies \alpha(r) \rightarrow -\infty$


