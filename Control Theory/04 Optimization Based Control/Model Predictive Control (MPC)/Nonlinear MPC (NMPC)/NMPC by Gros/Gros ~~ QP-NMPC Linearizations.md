---
tags:
  - Optimization/NMPC
Note Author:
  - Trym A. Gabrielsen
Theory Author:
  - Sébastien Gros
Reviewed By:
---
$$
\begin{gather}
\begin{aligned}
A^{i}_{j} = \left. \frac{\partial f_d}{\partial x}\right|_{\left(t_{i+j},~\tilde{x}^{i,g_{k}}_{j},~\tilde{u}^{i,g_{k}}_{j}\right)}~~, & \quad B^{i}_{j} = \left. \frac{\partial f_d}{\partial u}\right|_{\left(t_{i+j},~\tilde{x}^{i,g_{k}}_{j},~\tilde{u}^{i,g_{k}}_{j}\right)}\\
C^{i}_{j} = \left. \frac{\partial h}{\partial x}\right|_{\left(t_{i+j},~\tilde{x}^{i,g_{k}}_{j},~\tilde{u}^{i,g_{k}}_{j}\right)}~~, & \quad D^{i}_{j} = \left. \frac{\partial h}{\partial u}\right|_{\left(t_{i+j},~\tilde{x}^{i,g_{k}}_{j},~\tilde{u}^{i,g_{k}}_{j}\right)}\\
J^{i}_{j} = W^{i}_{j}\begin{bmatrix} \tilde{x}^{i,g_{k}}_{j} - x^{ref,i}_{j}\\ \tilde{u}^{i,g_{k}}_{j} - u^{ref,i}_{j}\end{bmatrix}~~, & \quad W^{i}_{j} = \nabla^{2}_{[x;u]} \phi (x^{i}_{j},u^{i}_{j})
\end{aligned}\\
H^{i}_{j} \approx \nabla^{2} \mathcal{L}(x^{i}_{j},u^{i}_{j},\lambda^{i}_{j})
\end{gather}
$$
^Linearizations

**Remarks:**
- $W^{i}_{j}$ is the hessian of the original NLP cost, which has been assumed to be quadratic. Although, this is not necessary, and in the case of a non-quadratic cost, $W^{i}_{j}$ remains the hessian of the cost:
$$W^{i}_{j} = \nabla^{2}_{[x;u]} \phi (x^{i}_{j},u^{i}_{j})$$
