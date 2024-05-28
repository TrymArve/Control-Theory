#Theory/Assumption 
#Theory/Consider/Feedback-Interconnection 
Consider: ![[Consider - Feedback Interconnection#^feedback-interconnected-system]]
Assume that 
- $\exists~\gamma:\mathbb{R}_+\mapsto\mathbb{R}_+$ that is
	- non-decreasing
such that the solutions, $x_2^\circ(t) \triangleq x_2(t,t_\circ,x_{2_\circ},x_1^\circ(t))$, of the parameterized system ![[Cascade Parameterization#^cascaded-parameterization]]
satisfy
$$ |x_2^\circ(t,x_1^\circ(t))| \leq \gamma(|x_{2_\circ}|)\quad \forall~t\in[t_\circ,t_{max}\rangle$$
with $\gamma$ independent on the initial conditions and the parameter $x_1^\circ(t)$.

# intuition
- If there exists a bound on the solutions of $\Sigma_2$ that is independent of the solution of $\Sigma_1$, then the feedback from $\Sigma_1$ will not affect the boundedness of the solutions of $\Sigma_2$.
- This means that $\Sigma_2$ will remain bounded *(even by the same amount)* regardless of the behavior of $\Sigma_1$.

