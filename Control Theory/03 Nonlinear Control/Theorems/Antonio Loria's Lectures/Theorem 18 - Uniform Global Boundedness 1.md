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
- *"Case 1: $f_1(t,\cdot)$ dominates over $g(t,\cdot,x_2)$"*

Consider: ![[Consider - Feedback Interconnection#^feedback-interconnected-system]]
If 
- Assumption [[Assumption 13 - Growth rate condition 1|13]] and [[Assumption 14 - Growth rate condition 2|14]] hold
- for each
	- $x_2\in\mathbb{R}^{n_2}$
	- $t\geq0$
	$$ \frac{\partial V(t,x_1)}{\partial x_1}g(t,x_1,x_2) = o(W(x_1)) ,$$
then
- the solutions of $\Sigma_1$ and $\Sigma_2$ are [[Boundedness|uniformly globally bounded]].




# Remarks
- $o(\cdot)$ refers to "small o"-notation (from computer science) ??
	- A function that is bounded from above by a $\mathcal{O}(\cdot)$ function ?
- This theorem covers the case where the growth rate of the *state dynamics*; $f_1$, dominate the *input dynamics*; $g$.
# Example (ISS systems)
Consider:
$$
\begin{align}
\dot{x}_1 & = -2x_1^3 + x_1x_2^2 \\
\dot{x}_2 & = -[1+x_(t)^2]x_2
\end{align}
$$
We see that
- $|x_2(t)|\leq |x_{2_\circ}| \forall t\in[t_\circ,t_{max}\rangle$,
since the $\Sigma_2$ dynamics is has the form 
- $-ax_2,~a\geq1$.
Let
- $V_1(x_1)\triangleq \frac{1}{2}x_1^2$
then
- $\dot{V}_1 = x_1\dot{x_1} = x_1(-2x_1^3 + x_1x_2^2) = -2x_1^4 + x_1^2x_2^2 \leq x_1^2x_2^2 \leq x_1^2|x_{2_\circ}|^2$ 
by integrating both sides over $[t_\circ,t_{max}\rangle$ we get
$$ \int_{t_\circ}^{t} \dot{V}_1(x_1(\tau))~d\tau \leq \int_{t_\circ}^{t} x_1^2(\tau)|x_{2_\circ}|^2~d\tau = |x_{2_\circ}|^2\int_{t_\circ}^{t} x_1^2(\tau)~d\tau = 2|x_{2_\circ}|^2\int_{t_\circ}^{t} V_1(x_1(\tau))~d\tau$$
$$ \implies  V_1(x_t(t))\leq  2|x_{2_\circ}|^2V_1(x_1(t_\circ))e^{t-t_\circ} = \alpha(x_\circ)e^{t-t_\circ}\quad\forall t\in[t_\circ,t_{max}\rangle$$
Thus we see that $x_1^\circ(t)$ cannot grow unbounded on the interval $[t_\circ,t_{max}\rangle$.