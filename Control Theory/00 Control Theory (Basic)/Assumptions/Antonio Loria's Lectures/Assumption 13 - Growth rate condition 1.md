#Theory/Assumption

Consider: ![[Consider - Feedback Interconnection#^feedback-interconnected-system]]
Assume that we know functions
- $V:\mathbb{R}_+\times\mathbb{R}^{n_1}\mapsto\mathbb{R}_+$ s.t. $V\in\mathcal{C}^1$
- $\alpha_1,\alpha_2 \in\mathcal{K}_\infty$
- $W$ is positive semi-definite
such that 
- $\forall~t\geq t_\circ$
- $\forall~x_1 \in \mathbb{R}^{n_1}$
we have
$$
\begin{align}
(1): \quad && \alpha_1(|x_1|) \leq V(t,x_1) \leq &~ \alpha_2(|x_1|) \\
(2): \quad && \frac{\partial V(t,x_1)}{\partial t}+\frac{\partial V(t,x_1)}{\partial x_1}f_1(t,x_1) \leq & -W(x_1)
\end{align}
$$
