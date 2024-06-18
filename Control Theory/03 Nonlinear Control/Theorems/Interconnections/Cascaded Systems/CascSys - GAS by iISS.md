---
tags:
  - NonlinearSystems/Theorem
Note Author:
  - Trym A. Gabrielsen
Theory Author:
  - Antonio Loría
Reviewed By:
---
Consider: ![[Consider - Cascade Interconnection (Time-Invariant)#^cascade-interconnected-system]]

If:
- $\Sigma_2$ is GAS         ($x_2 \rightarrow 0$ from anywhere)
- $\Sigma_1$ is 0-GAS      (if $x_2 \equiv 0$, then $x_1 \rightarrow 0$ from anywhere)
- (For any $a\in \mathcal{K}_\infty) ~ (\exists\,\gamma \in \mathcal{K}_\infty \,,\, \delta>0) ~:~ |x_2(t)| \leq \delta \implies |x_2(t)| \leq \alpha(e^{-kt}\gamma(|x_2(0)|))$    
	- *(There should a ball $\mathbb{B}_\delta$ such that, when inside, the state can be bounded by an asymptotically, strictly decreasing value)* 
	- *(What is the difference between    $\alpha(e^{-kt}\gamma(|x_2(0)|))$    and     $\beta(|x_2(0)|,t) \in \mathcal{KL}$    ?)*
- $\Sigma_1$ is iISS with gain $\mu(\cdot)$ satisfying $$ \int_{0}^{1} \frac{\mu (\alpha(s))}{s} ds < \infty $$ Then:
- The cascaded system $\Sigma_2 \rightarrow \Sigma_1$ is GAS      ($(x_1,x_2) \rightarrow (0,0)$ from anywhere)
*(There is a trade-off between the input gain $\mu$, and the speed of convergence of $x_2(t)$)*



# Proof (Sketch)
Let $T^*\geq 0$ be such that $|x_2(T^*)| \leq 0$,
then for all $t\geq T^*$:
$$ \int_{T^*}^{\infty} \mu(|x_2(t)|) ~dt ~\leq~ \int_{T^*}^{\infty} \mu(\alpha(e^{-kt}\gamma(|x_2(0)|))) ~dt$$
Define: $s\triangleq e^{-kt}\gamma(|x_2(0)|)$ , such that $\frac{ds}{dt} = -ke^{-kt}\gamma(|x_2(0)|) \quad \implies dt = -\frac{1}{ke^{-kt}\gamma(|x_2(0)|)}ds = -\frac{1}{s}ds$. Then:
$$ \int_{T^*}^{\infty} \mu(|x_2(t)|) ~dt ~\leq~ -\frac{1}{k} \int_{e^{-k(t=T^*)}\gamma(|x_2(0)|)}^{e^{-k(t=\infty)}\gamma(|x_2(0)|)}  \frac{\mu(\alpha(s))}{s} ~ds = \frac{1}{k} \int_{0}^{e^{-kT^*}\gamma(|x_2(0)|)}  \frac{\mu(\alpha(s))}{s} ~ds$$
This *(the last integral expression)* is bounded ($<\infty$) by assumption, for at least one $\gamma\in\mathcal{K}_\infty$ (I think... ?).
Therefore, from the definition of [[iISS - Integral-input-to-state stability|iISS]], we have that 
$$ \omega(|x(t)|) \leq \beta(|x(0)|,t) + \int_{0}^{t} \mu(|v(\tau)|) ~d\tau \quad\forall t\geq 0$$
$$\implies \omega(|x_1(t)|) \leq \beta(|x_1(0)|,t) + \int_{0}^{t} \mu(|x_2(\tau)|) ~d\tau \quad\forall t\geq 0$$
$$\implies \omega(|x_1(t)|) \leq \beta(|x_1(0)|,t) + c\cdot\gamma(|x_2(t)|) < \infty \quad\forall t\geq 0$$
$$\implies \omega(|x_1(t)|) < \infty \quad\forall t\geq 0$$
Which means that the solutions are bounded.
- **Underlying idea:** Starting at some time $T^*$, the solutions $x_2(t)$ converge sufficiently fast, such that the $x_1(t)$ is not exited enough to stay away from the origin.


