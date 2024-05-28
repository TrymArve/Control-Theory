#Theory/Theorem 
#Theory/Consider/Feedback-Interconnection 
#resources/Lecture/Loria

*"case 1: $f_1(t,\cdot)$ dominates over $g(t,\cdot,x_2)$"*

Consider: ![[Consider - Feedback Interconnection#^feedback-interconnected-system]]
If 
- Assumption [[Assumption 13 - Growth rate condition 1|13]] holds, i.e.:
	- $\dot{x}_1 = f_1(t,x_1)$ is UGAS
	- and:$$
\begin{align}
(1): \quad && \alpha_1(|x_1|) \leq V(t,x_1) \leq &~ \alpha_2(|x_1|) \\
(2): \quad && \frac{\partial V(t,x_1)}{\partial t}+\frac{\partial V(t,x_1)}{\partial x_1}f_1(t,x_1) \leq & -W(x_1)
\end{align}
$$
- Assumption [[Assumption 15 - Attractivity|15]] holds
- $\forall~(x_2,t)\in\mathbb{R}^{n_2}\times\mathbb{R}_+$ 
	$$ \frac{\partial V(t,x_1)}{\partial x_1}g(t,x_1,x_2) = o(W(x_1))$$
Then
- the origin, $(x_1,x_2)=(0,0)$, is **uniformly globally asymptotically stable** (UGAS).

