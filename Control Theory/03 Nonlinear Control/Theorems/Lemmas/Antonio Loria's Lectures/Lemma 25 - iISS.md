---
tags:
  - NonlinearSystems/Lemma
Note Author:
  - Trym A. Gabrielsen
Theory Author:
  - Antonio Loría
Reviewed By:
---
Consider: ![[Consider - Controlled NTI#^system]]
The system $\Sigma_\circ$ is ***[[iISS - Integral-input-to-state stability|iISS]]*** iff:
- $\exists\, V:\mathbb{R}^n\mapsto\mathbb{R}$ that is:
	- positive definite
	- radially unbounded
	- continuously differentiable
- $\exists\, \mu \in \mathcal{K}$
- $\exists\, \rho:\mathbb{R}\mapsto\mathbb{R}$ that:
	- is positive definite
	- satisfies: $$ \frac{\partial V}{\partial x}f(x,u) \leq -\rho(|x|) + \mu(|u|) $$

