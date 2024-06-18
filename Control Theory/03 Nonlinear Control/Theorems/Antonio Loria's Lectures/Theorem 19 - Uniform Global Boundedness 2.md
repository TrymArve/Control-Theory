---
tags:
  - NonlinearSystems/Theorem
Note Author:
  - Trym A. Gabrielsen
Theory Author:
  - Antonio Loría
Reviewed By:
---
From Loria's Growth Comparisons:
- *"Case 2: $f_1(t,\cdot)$ is of the same order as $g(t,\cdot,x_2)$"

Consider: ![[Consider - Feedback Interconnection#^feedback-interconnected-system]]
If 
- Assumption [[Assumption 12 - Finite time boundedness of x1|12]], [[Assumption 13 - Growth rate condition 1|13]] and [[Assumption 15 - Attractivity|15]] hold
- $\exists~\alpha_5,\alpha_5'\in\mathcal{K}$   s.t.
	- $|[L_gV]| \leq \alpha_5(|x_1|)\alpha_5'(|x_2|)$
	- $\forall ~r > 0$
		- $\exists~\lambda_r,\eta_r >0$  s.t.
	$$ (~t\geq0 ~\wedge~ |x_1|\geq \eta_r~) \implies \alpha_5(|x_1|)\leq\lambda_rW(x_1)$$
then
- the solutions of $\Sigma_1$ and $\Sigma_2$ are uniformly globally bounded.


# Remarks
- This theorem covers the case where the growth rate of the *state dynamics*; $f_1$, is similar to the *input dynamics*; $g$.