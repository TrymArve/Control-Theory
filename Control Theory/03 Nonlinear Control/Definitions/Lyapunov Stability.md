#NonlinearSystems/Definition 
# Definitions (using comparison functions)

## Stability (S) 
An equilibrium $x=0$ is *stable* iff
- $\forall ~ t_0$ 
	- $\exists ~ c > 0$
	- $\exists~\alpha:[0,c]\mapsto\mathbb{R} \quad s.t.\quad \alpha \in \mathcal{K}$
	- such that
$$ ||x(t_0)||\leq c \implies ||x(t)|| \leq \alpha(||x(t_0)||) \quad \forall t\geq t_0$$

## Asymptotic Stability (AS)
An equilibrium $x=0$ is *asymptotically stable* iff
- $\forall ~ t_0 \geq 0$ 
	- $\exists~\beta:[0,r]\times[0,\infty\rangle\mapsto\mathbb{R} \quad s.t.\quad \beta \in \mathcal{KL}$
	- $\exists ~ c > 0$
	- such that
$$ ||x(t_0)||\leq c \implies ||x(t)|| \leq \beta(||x(t_0)||,t) \quad \forall t\geq t_0 \geq 0$$
## Exponential Stability (ES)
An equilibrium $x=0$ is *exponentially stable* iff
- $\forall ~ t_0$ 
	- $\exists ~ c,k,\lambda > 0$
	- such that
$$ ||x(t_0)||\leq c \implies ||x(t)|| \leq k||x(t_0)||^{-\lambda(t-t_0)} \quad \forall t\geq t_0$$

## Uniformity in $t$
For all stability definitions above, uniformity in time, $t$, is achieved iff all bounds can be stated independently of initial time $t_0$. That is; exclude the "$\forall t_0$" at the beginning.
- Add "U" to acronym

## Globality
The stability notions above are said to be *"global"* iff the bound on initial state, $c$, can be arbitrarily large, and for S and AS, the comparison functions are class $\mathcal{K}_\infty$.
- Adds "G" to acronym
