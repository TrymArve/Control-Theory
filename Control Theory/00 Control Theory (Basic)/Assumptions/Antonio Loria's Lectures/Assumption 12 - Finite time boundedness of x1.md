#Theory/Assumption

Consider:
![[Consider - Feedback Interconnection#^feedback-interconnected-system]]
Assume that there exists
- a function $\tilde{V}: \mathbb{R}_+\times \mathbb{R}^{n_1}\mapsto \mathbb{R}_+$, that is
	- $\mathcal{C}^1$
	- positive definite
	- radially  unbounded
- a function $\alpha_1 \in \mathcal{K}_\infty$
- and $\alpha_4,\alpha_4':\mathbb{R}_+\mapsto\mathbb{R}_+$, that are
	- continuous
	- non-decreasing
such that

$$
(1):\quad  \tilde{V}(t,x_1) \geq \alpha_1(|x_1|)
$$

^bijection

and for each $x_2$;
$$ \begin{gather} 
(2):\quad \dot{\tilde{V}}_{\Sigma_1}(t,x_1) \triangleq \frac{\partial \tilde{V}}{\partial t} + \frac{\partial\tilde{V}}{\partial x_1}\bigg(f_1(t,x_1)+g(t,x_1,x_2)\bigg) \leq \alpha_4(|x_1|)\alpha_4'(|x_2|) 
\\[0.5cm] 
(3):\quad \int_{a}^{\infty} \frac{1}{\alpha_4(\alpha_1^{-1}(\tilde{v}))} ~d\tilde{v} = \infty 
\end{gather}$$

^growth-bound


# Intuition
- (1) - Standard Lyapunov-like function for system $\Sigma_1$, where $\alpha_1 \in \mathcal{K}_\infty$.
- (2) - For each constant input $x_2$, the Lyapunov-like function $\tilde{V}$ has bounded rate of increase on the solutions of system $\Sigma_1$.
	- That is, $\alpha_4,\alpha_4'$ are both continuous, non-decreasing and defined on the whole positive real line.
	- Therefore they cannot be unbounded for finite input. (no asymptotes)
	- The only way for them to grow unbounded, is to do so as the input goes to infinity.
	- This means that the Lyapunov-like function cannot grow infinitely fast unless either $|x_1|$ or $|x_2|$ is unbounded.
	- This, in turn, means that the value of the Lyapunov-like function cannot go to infinity unless either system $\Sigma_2$ or $\Sigma_1$ does as well.
- (3) - We have
	- $\tilde{V}\geq \alpha_1(|x_1|) \implies \alpha_1^{-1}(\tilde{V})\geq |x_1| \implies \alpha_4(\alpha_1^{-1}(\tilde{V})) \geq \alpha_4(|x_1|)$ 
	- Also, $$ \int_{a}^{\infty} \frac{1}{\alpha_4(\alpha_1^{-1}(\tilde{v}))} ~d\tilde{v} = \infty  $$ implies that $\alpha_4(\alpha_1^{-1}(\cdot))$ cannot grow too fast after some value $a$, as the integral would not be zero if it grows too fast.
	- After some value $a$, the expression $\alpha_4(\alpha_1^{-1}(\tilde{V}))$ cannot grow faster than $\mathcal{O}(\tilde{V})$ (i think...)
	- $\implies \alpha_4(|x_1|)\leq\mathcal{O}(\tilde{V})$, which again bounds the growth rate of $\tilde{V}$ on the solutions of $\Sigma_1$ for constant inputs $x_2$. $$\dot{\tilde{V}}_{\Sigma_1}(t,x_1) \leq \alpha_4(|x_1|)\alpha_4'(|x_2|) \leq \mathcal{O}(\tilde{V}_{\Sigma_1}) $$
	- Notice that the worst case is $\dot{\tilde{V}}_{\Sigma_1} = \lambda_2\tilde{V}_{\Sigma_1}$ , where $\lambda_2$ is a constant $\lambda_2=\alpha_4'(|x_2|)$.
	- Which amounts to exponential growth: $\tilde{V}_{\Sigma_1} = \tilde{V}_{\Sigma_1}(t_\circ,x_{1_\circ}) e^{\lambda_2(t-t_\circ)}$ 
	- So the upper bound on the [[Assumption 12 - Finite time boundedness of x1#^bijection|bijection]] of $x_1$ cannot grow faster than an exponential, and therefore $x_1$ ***cannot grow unbounded in finite time***.