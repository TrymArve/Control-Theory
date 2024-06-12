An [[General SQP Method|SQP]] strategy for NMPC as formulated by [[NMPC - by Gros|Gros]].
Notation: [[Optimization#Dynamic Optimization / MPC|here]]
Consider: ![[NMPC - by Gros#^NMPC-Gros]]

# SQP Strategy
- At time $t_{i}$, we wish to compute $$\text{NLP}_{\text{NMPC}}^{i}(\hat{x}_{i},x^{ref,i},u^{ref,i})$$ to acquire $\tilde{u}^{i}_{0}$.

1) First guess a solution; $(\tilde{x}^{i,g_{0}},\tilde{u}^{i,g_{0}})$
	-  This guess is wrong, and we must adjust it:
		- $(\tilde{x}^{i,g_{1}},\tilde{u}^{i,g_{1}}) = (\tilde{x}^{i,g_{0}},\tilde{u}^{i,g_{0}}) + \alpha(\Delta x^{i},\Delta u^{i})_{0}$
		to produce the next guess
2) Find the $k^{\text{th}}$ step of the search; $(\Delta x^{i},\Delta u^{i})_{k}$
	- We approximate $\text{NLP}^{i}_{\text{NMPC}}(\cdot)$ with a QP: $$\begin{gather*}
\text{QP}_{\text{NMPC}}^{i}(\hat{x}_{i},\tilde{x}^{i,g_{k}},\tilde{u}^{i,g_{k}},x^{ref,i},u^{ref,i}) \triangleq \hspace{5cm} \\[0.5cm]
\arg \min_{\Delta x^{i},\Delta u^{i}} \quad \sum\limits_{j=0}^{H-1}\frac{1}{2}\begin{bmatrix} \Delta x^{i}_{j} \\ \Delta u^{i}_{j}\end{bmatrix}^{\top} H^{i}_{j} \begin{bmatrix}\Delta x^{i}_{j} \\ \Delta u^{i}_{j}\end{bmatrix} + J^{i}_{j} \begin{bmatrix}\Delta x^{i}_{j} \\ \Delta u^{i}_{j}\end{bmatrix}\\[0.3cm]
\begin{aligned}
\text{subject to:}&\\
\Delta x^{i}_{0} & = \hat{x}_{i} - \tilde{x}^{i,g_{i}}_{0}\\
\Delta x^{i}_{j+1} & = A^{i}_{j}\Delta x^{i}_{j} + B^{i}_{j}\Delta u^{i}_{j} + r^{i}_{j} && \forall j \in \mathbb{N}_{0,N-1}\\
0 &\leq C^{i}_{j}\Delta x^{i}_{j} + D^{i}_{j}\Delta u^{i}_{j} + h^{i}_{j}  && \forall j \in \mathbb{N}_{0,N-1}
\end{aligned}
\end{gather*}$$ where $$\begin{align*}
r^{i}_{j} & \triangleq f_d(t_{i+j},\tilde{x}^{i,g_{k}}_{j},\tilde{u}^{i,g_{k}}_{j}) - \tilde{x}^{g_{k}}_{j+1}\\
h^{i}_{j} & \triangleq h(t_{i+j},\tilde{x}^{g_{k}}_{j},\tilde{u}^{g_{k}}_{j})
\end{align*}$$ and $$\begin{align*}
A^{i}_{j} = \left. \frac{\partial f_d}{\partial x}\right|_{\left(t_{i+j},~\tilde{x}^{i,g_{k}}_{j},~\tilde{u}^{i,g_{k}}_{j}\right)}~~, & \quad B^{i}_{j} = \left. \frac{\partial f_d}{\partial u}\right|_{\left(t_{i+j},~\tilde{x}^{i,g_{k}}_{j},~\tilde{u}^{i,g_{k}}_{j}\right)}\\
C^{i}_{j} = \left. \frac{\partial h}{\partial x}\right|_{\left(t_{i+j},~\tilde{x}^{i,g_{k}}_{j},~\tilde{u}^{i,g_{k}}_{j}\right)}~~, & \quad D^{i}_{j} = \left. \frac{\partial h}{\partial u}\right|_{\left(t_{i+j},~\tilde{x}^{i,g_{k}}_{j},~\tilde{u}^{i,g_{k}}_{j}\right)}\\
J^{i}_{j} &= W^{i}_{j}\begin{bmatrix} \tilde{x}^{i,g_{k}}_{j} - x^{ref,i}_{j}\\ \tilde{u}^{i,g_{k}}_{j} - u^{ref,i}_{j}\end{bmatrix}
\end{align*}$$ and 
		-  $H^{i}_{j} \approx \nabla^{2}\mathcal{L}^{i}_{j}$ is some approximation of the Hessian of the Lagrangian of the original NLP problem
		("Gauss-Newton Hessian approximation" $\rightarrow H^{i}_{j} = W^{i}_{j}$ in this case)
- Then $$(\Delta x^{i},\Delta u^{i})_{k} = \text{QP}_{\text{NMPC}}^{i}(\hat{x}_{i},\tilde{x}^{g_{k}},\tilde{u}^{g_{k}},x^{ref,i},u^{ref,i})$$
3) Use a [[Merit Function]] to find a step length; $\alpha$, that ensures progress
4) Repeat until convergence
	- that is: $(\tilde{x}^{i,g_{k}},\tilde{u}^{i,g_{k}}) \rightarrow (\tilde{x}^{i*},\tilde{u}^{i*})$
5) deploy $\tilde{u}^{i*}_{0}$ on your system

