Linear Quadratic (LQ) Problems are a class of [[Optimal Control Problem|optimal control problems]] where
- the control objective is a quadratic function of the system state and inputs
	- *(deviations from reference)*
- the system dynamics are linear

**LQ Problem**
$$\begin{align*}
\min_{U} & \sum\limits_{i=1}^{H}\frac{1}{2}\Delta x_{i}^{\top}Q_{i}\Delta x_{i} + \sum\limits_{i=0}^{H-1}\frac{1}{2}\Delta u_{i}^{\top}R_{i}\Delta u_{i}\\
\text{subject to:}\\
\tilde{x}_{i+1} &= A_{i}\tilde{x}_{i} + B_{i}\tilde{u}_{i} \quad \forall i \in \mathbb{Z}_{0,H-1}\\
0 & \leq C_{i}\tilde{x}_{i} + D_{i}\tilde{u}_{i} \quad \forall i \in \mathbb{Z}_{0,H}
\end{align*}$$
^LQ-Problem
