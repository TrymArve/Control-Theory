## Equivalent Characterizations of [[ISS - Input-to-State Stability|ISS]]
Consider: ![[Consider - Controlled NTI#^system]]
**By global stability properties:**
-  ISS  $\Leftrightarrow$  (GS  or   0-GAS) + [[Asymptotic Gain|AG property]]

**By class $\mathcal{K}$ functions:**
- A system, $\dot{x}_1 = f_1(x_1,x_2)$, with input $x_2$, is **ISS** iff there exists a
	- Positive definite proper function $V$
	- and two class $\mathcal{K}$ functions $\alpha_1$ and $\alpha_2$ 
	such that for each $(x_1,x_2) \in \mathbb{R}^n \times \mathbb{R}^m$ :
	$$ |x_1| \geq \alpha_1(|x_2|) \implies \begin{Bmatrix} \frac{\partial V}{\partial x_1}f_1(x_1,x_2) \leq -\alpha_2(|x_1|) \end{Bmatrix}$$
	**Intuition:**
	- If the size of the state, $x_1$, is large *(larger than some $\mathcal{K}$ function of the input)*, then the Lyapunov function V will decrease asymptotically on the solution $x_1(t)$.
	- When the state is inside some ball defined by the input, V no longer has to decrease.
	- When the input goes to zero, $x_2 \rightarrow 0$, the non-decreasing ball goes away, and the state must converge to zero.
	- **Simply put:** *The ISS property means that the system must converge to $\mathbb{B}_{\alpha(u)}$ for each constant $u$*

## Relevant Implications
Clearly, if the system is ISS, the it is also 0-GAS, and also BIBO stable if the state is considered the output of the system:

- ISS $\implies$ [[0-GAS]]
- ISS $\implies$ [[BIBO Stability|BIBO stable]] (if the state is considered the output: $y = x$)
- 0-GAS $\implies$ Local ISS