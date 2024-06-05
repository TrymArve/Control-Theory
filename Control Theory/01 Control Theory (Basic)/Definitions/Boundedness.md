#Theory/Definition
Consider:
$$(1)\qquad  \dot{x} = f(x,u,t), \quad x(t_0) = x_0$$
whose trajectory is denoted:   $x^0(t), ~t\geq t_0$.
## Boundedness
The solutions $x^0(t)$ of (1) are bounded iff
- $\forall a\in\langle0,c(t)\rangle,~c(t)>0,~\exists:$
	- $b(t,a)>0$
- such that
$$ ||x^0(t_0)|| \leq a \leq c(t_0)  \implies ||x^0(t)|| \leq b(t_0,a) \quad\forall t\geq t_0$$
### (with comparison function)
The solutions $x^0(t)$ of (1) are bounded iff
- $\forall t_0$
	- $\exists~a > 0$
	- $\exists~\gamma:[0,a]\mapsto\mathbb{R} \quad s.t. \quad \gamma \in \mathcal{K}$
	- $\exists~c > 0$
- such that
$$ ||x^0(t)|| \leq \gamma(||x_0||) + c \quad \forall ||x_0||\leq a \quad\forall t\geq t_0\geq0$$

## Ultimate Boundedness
The solutions $x^0(t)$ of (1) are ultimately bounded iff
-  $\forall a\in\langle0,c(t)\rangle,~c(t)>0,~\exists:$
	- $b(t,a)>0$
	- $T(t,a,b) > 0$
- such that
$$ ||x^0(t_0)|| \leq a \leq c(t_0)  \implies ||x^0(t)|| \leq b(t_0,a) \quad\forall t\geq t_0 + T(t_0,a,b)$$

## Global (Ultimate) Boundedness
- is achieved if the solution is (ultimately) bounded with arbitrarily large $a$.

## Uniform (Ultimate) Boundedness
- is achieved then the bounds $c,b$ (and T) are not dependent on the initial time $t_0$.