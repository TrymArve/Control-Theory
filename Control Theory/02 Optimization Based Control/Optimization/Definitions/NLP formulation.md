$$\text{(NLP):} \qquad  \min_{z\in\mathbb{R}^{n_z}} ~\phi(z)\quad s.t. \quad g(z) = 0\, , \quad h(z) \geq 0$$ ^59f1b4


where
- $z\in \mathbb{R}^{n_z}$ is the decision vector
- $\phi:\mathbb{R}^{n_z}\mapsto\mathbb{R}$ is the cost/objective function
- $g:\mathbb{R}^{n_{z}}\mapsto\mathbb{R}^{n_{eq}}$ is the equality constraint function
- $h:\mathbb{R}^{n_{z}}\mapsto\mathbb{R}^{n_{in}}$ is the inequality constraint function

**Remarks:**
- Total number of constraints is: $n_{con} = n_{eq} + n_{in}$
- $\phi,g,h$ are usually continuously differentiable if not specified otherwise.
	- though this is not necessarily the case.
- inequality constraints may be specified as $h(z) \leq 0$ sometimes in literature, but we consistently use the positive formulation above in this vault.