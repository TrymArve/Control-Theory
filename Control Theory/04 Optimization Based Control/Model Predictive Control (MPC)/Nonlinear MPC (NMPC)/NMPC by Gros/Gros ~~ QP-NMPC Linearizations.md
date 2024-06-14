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
C^{i}_{j} = \left. \frac{\partial h}{\partial x}\right|_{\left(t_{i+j},~\tilde{x}^{i,g_{k}}_{j},~\tilde{u}^{i,g_{k}}_{j}\right)}~~, & \quad D^{i}_{j} = \left. \frac{\partial h}{\partial u}\right|_{\left(t_{i+j},~\tilde{x}^{i,g_{k}}_{j},~\tilde{u}^{i,g_{k}}_{j}\right)}
\end{aligned}\\
J^{i}_{j} = W^{i}_{j}\begin{bmatrix} \tilde{x}^{i,g_{k}}_{j} - x^{ref,i}_{j}\\ \tilde{u}^{i,g_{k}}_{j} - u^{ref,i}_{j}\end{bmatrix}
\end{gather}
$$
^Linearizations
