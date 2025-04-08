---
tags: 
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
**Also known as:** *'Karush–Kuhn–Tucker'* conditions

Consider ![[NLP formulation#^NLP]]
and ![[Lagrangian#^Lagrangian]]
**Definition:**
For a given solution $z^{*}$, and Lagrangian multipliers $\lambda^{*}$, the *KKT conditions* are:
$$\begin{align*}
\text{(KKT-1):} \qquad && \nabla_{z}\mathcal{L}(z^{*},\lambda^{*})&=0 &\text{(Dual Feasibility)}\\
\text{(KKT-2):} \qquad && g(z^{*})&=0 &\text{(Primal Feasibility)}\\
\text{(KKT-3):} \qquad && h(z^{*})&\geq0 &\text{(Primal Feasibility)}\\
\text{(KKT-4):} \qquad && \hat{\lambda}^{*}&\geq0 &\text{(Dual Feasibility)}\\
\text{(KKT-5):} \qquad && \hat{\lambda}^{*}_{i}h_{i}(z^{*}) &=0 \quad \forall i \in \mathbb{Z}_{1,n_{in}} & \text{(Complimentarity Slackness)}
\end{align*}$$

^KKT-conditions

**Remarks:**
- Notation for the Lagrange multipliers: $\lambda = [\bar\lambda; \hat\lambda]$
- The KKT conditions are guaranteed to hold in a local optimum if the problem is [[Regularity|regular]]
	- OBS: the converse does not hold:
		- A point that satisfies the KKT conditions is NOT necessarily a local optimum.
	- Nevertheless, many NLP-solvers primarily attempt to find a point that satisfies the KKT conditions, and it is up to the user to make sure that it is actually an optimum. (f.ex. via [[Second Order Sufficient Condition (SOSC)|SOSC]])

- For equality constrained NLPs, we can reconstruct the KKT conditions via the [[KKT-Vector]]
- 