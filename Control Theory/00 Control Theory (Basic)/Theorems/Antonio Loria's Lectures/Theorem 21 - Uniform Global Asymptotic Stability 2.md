#Theory/Theorem
#Theory/Consider/Feedback-Interconnection 
#resources/Lecture/Loria

*"case 2:  $g(t,\cdot,x_2) = \mathcal{O}(f_1(t,\cdot))$"*

Consider: ![[Consider - Feedback Interconnection#^feedback-interconnected-system]]
If 
- the origin of $\dot{x}_1 = f_1(t,x_1)$ is UGAS
- Assumption [[Assumption 12 - Finite time boundedness of x1|12]], [[Assumption 13 - Growth rate condition 1|13]] and [[Assumption 15 - Attractivity|15]] hold
- $\exists~\alpha_5,\alpha_5'\in\mathcal{K}$   s.t.
	- $|[L_gV]| \leq \alpha_5(|x_1|)\alpha_5'(|x_2|)$
	- $\forall ~r > 0$
		- $\exists~\lambda_r,\eta_r >0$  s.t.
	$$ (~t\geq0 ~\wedge~ |x_1|\geq \eta_r~) \implies \alpha_5(|x_1|)\leq\lambda_rW(x_1)$$
Then
- the origin, $(x_1,x_2)=(0,0)$, is **uniformly globally asymptotically stable** (UGAS).