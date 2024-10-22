---
tags:
  - Theorem
  - Optimization/NMPC/Suboptimal
Note Author:
  - Trym A. Gabrielsen
Theory Author:
  - P. O. M. Scokaert
  - D. Q. Mayne
  - J. B. Rawlings
Reviewed By: 
Relevant Paper: '"Suboptimal Model Predictive Control (Feasibility Implies Stability)"'
---
Consider a controlled discrete system
$$\Sigma_{d}: \quad x_{k+1} = f(x_{k},u)$$
where
- $f:\mathbb{R}^{n_{x}}\times\mathbb{R}^{n_{u}} \mapsto \mathbb{R}^{n_{x}}$  is continuous at the origin
- $f(0,0) = 0$
- $u$ is a control signal

We consider a discrete state trajectory:
$$\mathcal{X}(x_{0}) =\{x_{0}, x_{1}, x_{2}, \cdots \}$$
satisfying $\Sigma_{d}$, where the $k^{th}$ step is denoted $x_{k}$ for $k \in \mathbb{N}_{0}$.
Consider a controller map
$$\mathbb{U}: \mathbb{R}^{n_{x}} \mapsto \mathbb{R}^{n_{u}N}$$
where $\mathbb{U}(x)\subseteq \mathbb{R}^{n_{u}N}$ is the set of feasible control trajectories;
$$\{u_{0}, u_{1}, \cdots, u_{N-1}\}$$
$N$ steps into the future, such that the $N+1$ first elements of $\mathcal{X}(x)$ are feasible with respect to some constraints.
Denote by superscript $k$ a feasible control trajectory from the state $x_{k}$ , that is:
$$u^{k} = \{u^{k}_{0}, u^{k}_{1}, \cdots, u^{k}_{N-1}\} \in \mathbb{U}(x_{k})$$




**Theorem:**
If:
- $\exists$
	- $\alpha \in \mathcal{K}$ [[Class K function|(class K function)]]
	- $V:\mathbb{R}^{n_{x}}\times \mathbb{U} \mapsto \mathbb{R}$ 
	- $\text{s.t.}$
		- $V(0,0) \in \mathcal{C}^{0}$ *(continuous at the origin)*
		- $V(0,0) = 0$
		- $\forall (x,u) \in \mathbb{R}^{n_{x}}\times \mathbb{U}(x)$
			- $V(x,u) \geq \alpha(||x||)$
- $\exists$
	- $\mathbb{D} \subseteq \mathbb{R}^{n_{x}}$
	- $\gamma \in \mathcal{K}$
	- $\text{s.t.}$
		- $\exists \xi >0:\mathbb{B}^{n_{x}}_{\xi} \subset \mathbb{D}$ *(contains an open neighborhood of the origin)*
		- $x_{k}\in \mathbb{D} \implies \forall~u^{k}\in\mathbb{U}(x_{k})$
			- $x_{k+1}\in \mathbb{D}$  [[Invariant Set|(invariance)]]
			- $V(x_{k+1},u^{k+1}) \leq  V(x_{k},u^{k}) -\gamma(||(x_{k},u^{k}_{0})||)$
- $\exists$
	- $r>0$ 
	- $\sigma\in \mathcal{K}$
	- $\text{s.t.}$
		- $\forall~u^{k}\in\mathbb{U}(x^{k})$
			- $x_{k}\in \mathbb{B}^{n_{x}}_{r} \implies ||u^{k}||\leq\sigma(||x_{k}||)$

Then:
- the controlled system is asymptotically stable at the origin, with region of attraction: $\mathcal{R}_{A} \supseteq \mathbb{D}$




##### Proof

###### Stability

Let 
$$x^{\circ} = \{x^{\circ}_{0},x^{\circ}_{1},x^{\circ}_{2},\dots\}, \quad  x^{\circ}_{0} = x_{0} \in \mathbb{D} $$
be the true system trajectory, occurring as a result of the control signals $u^{k}_{0}$
Since $V$
- is continuous at the origin
- and $V(0,0) = 0$
we have
$$\exists (r_{1} > 0 ,~ \beta\in \mathcal{K}) \quad : \quad (~~V(x,u) \leq \beta(||(x,u)||) \quad \forall (x,~ u) \in \mathbb{B}^{n_{x}}_{r_{1}}\times\mathbb{B}^{n_{u}N}_{r_{1}}~~)$$
Also, since $\{0\}\subset \text{int}(\mathbb{D})$, we have that 
$$\exists r_{2}>0 : \mathbb{B}^{n_{x}}_{r_{2}} \subseteq \mathbb{D}$$
We have
- $\forall \epsilon > 0$
	- $\exists \delta >0:$
		- $\delta \leq \min(r,r_{1},r_{2})$
		- $\sigma(\delta) \leq r_{1}$
		- $\beta(\delta+\sigma(\delta)) < \alpha(\epsilon)$

Such a $\delta > 0$  exists because
- $\alpha(\epsilon) > 0$
- $\sigma(\delta) \rightarrow 0 ~\text{as}~ \delta \rightarrow 0$
- $\implies \beta(\delta + \sigma(\delta)) \rightarrow 0 ~\text{as}~ \delta \rightarrow 0$

Suppose 
$$||x^{\circ}_{0}|| \leq \delta$$
then 
$$||u^{0}|| \leq \sigma(\delta)$$
and 
$$\begin{align} 
V(x^{\circ}_{0},u^{0}) & \leq \beta(||(x^{\circ}_{0},u^{0})||) \\
& \leq \beta(||x^{\circ}_{0}|| + ||u^{0}||) \\
& \leq \beta(\delta + \sigma(\delta)) \\
& < \alpha(\epsilon)
\end{align}$$
Moreover, since $||x^{\circ}_{0}|| \leq \delta$ , we have that $x^{\circ}_{0} \in \mathbb{B}^{n_{x}}_{r_{2}} \subset \mathbb{D}$, thus
$$V(x^{\circ}_{k},u^{k}) \leq V(x^{\circ}_{0},u^{0}) < \alpha(\epsilon) \quad \forall k \geq 0$$
and by definition of $\alpha$, we have:
$$\alpha(||x^{\circ}_{k}||) \leq V(x^{\circ}_{k},u^{k}) \quad \forall k \geq 0$$
Which means that 
$$\alpha(||x^{\circ}_{k}||) < \alpha(\epsilon)$$
which implies
$$||x_{k}|| < \epsilon \quad \forall k\geq0 \quad_\blacksquare$$

###### Attraction
First of all, we have 
$$V(x,u) \geq 0 \quad \forall (x,u) \in \mathbb{R}^{n_{x}}\times \mathbb{U}(x)$$
Furthermore, the requirement that
$$x_{0}\in \mathbb{D} \implies V(x_{k+1},u^{k+1}) \leq  V(x_{k},u^{k}) -\gamma(||(x_{k},u^{k}_{0})||)$$
means that $V$ decreases on the trajectory $x^\circ$.
Therefore, since it is decreasing and has a lower bound, we can conclude that
$$V(x_{k},u^{k}) \rightarrow V^{*} ~~\text{as}~~ k \rightarrow \infty$$
where $V^*\geq0$ is a constant.
Therefore, similarly to  [[Barbalat's Lemma]], we see that 
$$V(x_{k},u^{k}) - V(x_{k+1},u^{k+1})\rightarrow 0 ~~\text{as}~~ k \rightarrow\infty$$
An together with 
$$V(x_{k},u^{k}) - V(x_{k+1},u^{k+1}) \geq \gamma(||(x_{k},u^{k}_{0})||)$$
gives
$$\gamma(||(x_{k},u^{k}_{0})||) \rightarrow 0 ~~\text{as}~~ k \rightarrow\infty$$
which, since $\gamma \in \mathcal{K}$, ultimately gives
$$||(x_{k},u^{k}_{0})|| \rightarrow 0 ~~\text{as}~~ k \rightarrow\infty \quad _\blacksquare$$
