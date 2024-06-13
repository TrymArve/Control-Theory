Notation: [[Optimization#Dynamic Optimization / MPC|here]]

An optimal control problem *(discrete)*, is a problem where:
- we wish to control a dynamical system, modelled as ![[Consider - Discrete NTV#^Discrete-NTV]]
- Out control efforts and system state must adhere to various constraints (actuator limitations, obstacles, etc.):
$$0\leq h(t_{k},x_{k},u_{k})\in \mathbb{R}^{n_{h}}$$

**OCP:**
$$\begin{align*}
\min_{U} & \quad\phi(\tilde{t},\tilde{x},\tilde{u},x^{ref},u^{ref})\\
\text{subject to:}\\
\tilde{x}_{i+1} &= f_{d}(t_{i}, \tilde{x}_{i},\tilde{u}_{i}) && \forall i \in \mathbb{Z}_{0,N-1}\\
0 &\leq h(t_{i},\tilde{x}_{i},\tilde{u}_{i}) && \forall i \in \mathbb{Z}_{0,N}
\end{align*}$$
^OCP

