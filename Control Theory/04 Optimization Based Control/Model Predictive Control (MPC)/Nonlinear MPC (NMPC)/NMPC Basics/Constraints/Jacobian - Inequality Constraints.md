---
tags: []
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By: 
Relevant Papers:
---
Consider:
![[Inequality Vector#^def]]
![[Decision Variables#^definition-of-z]]

**Jacobian of h:**
$$\frac{\partial h_{h}}{\partial z^{k}}=\begin{bmatrix}
C^{k}_{0} & D^{k}_{0}  \\[0.5em]
&& C^{k}_{1} & D^{k}_{1}   \\[0.5em]
&&&& \tiny\ddots \\
&&&&& C^{k}_{N-2} & D^{k}_{N-2}  \\[0.5em]
&&&&&&& C^{k}_{N-1} & D^{k}_{N-1} \\[0.5em]
&&&&&&&&&\frac{\partial}{\partial \tilde x^{k}} ( \hat{\mathcal{T}}(\tilde x^{k}_{N}))
\end{bmatrix}$$
^Jacobian-of-inequality

where
![[Jacobian of Stage Inequality#^def]]


# Derivation
$$
\frac{\partial h_{h}}{\partial z^{k}} = 
\begin{bmatrix}
\frac{\partial}{\partial z^{k}} h_{0}\\[0.5em]
\vdots\\[0.5em]
\frac{\partial}{\partial z^{k}} h_{N-1}\\[0.5em]
\frac{\partial}{\partial z^{k}} ( \hat{\mathcal{T}}(\tilde x^{k}_{N}))
\end{bmatrix}
$$
$$=\begin{bmatrix}
\frac{\partial}{\partial z^{k}_{0}} h_{0} \\[0.5em]
& \tiny\ddots \\
&&\frac{\partial}{\partial z^{k}_{N-1}} h_{N-1} \\[0.5em]
&&&\frac{\partial}{\partial z^{k}} ( \hat{\mathcal{T}}(\tilde x^{k}_{N}))
\end{bmatrix}$$
then we use:
$$\frac{\partial}{\partial z^{k}_{j}} h_{j} = \begin{bmatrix}\frac{\partial}{\partial \tilde x^{k}_{j}} h_{j} & \frac{\partial}{\partial \tilde u^{k}_{j}} h_{j}\end{bmatrix}  \quad\forall j\in \mathbb{Z}_{0,N}$$
$$z^{k}_{N} = \tilde x^{k}_{N}$$
to get
$$=\begin{bmatrix}
\frac{\partial}{\partial \tilde x^{k}_{0}} h_{0} & \frac{\partial}{\partial \tilde u^{k}_{0}} h_{0} \\[0.5em]
&& \frac{\partial}{\partial \tilde x^{k}_{1}} h_{1} & \frac{\partial}{\partial \tilde u^{k}_{1}} h_{1} \\[0.5em]
&&&& \tiny\ddots \\
&&&&&\frac{\partial}{\partial \tilde x^{k}_{N-2}} h_{N-2} & \frac{\partial}{\partial \tilde u^{k}_{N-2}} h_{N-2} \\[0.5em]
&&&&&&&\frac{\partial}{\partial \tilde x^{k}_{N-1}} h_{N-1} & \frac{\partial}{\partial \tilde u^{k}_{N-1}} h_{N-1} \\[0.5em]
&&&&&&&&&\frac{\partial}{\partial \tilde x^{k}} ( \hat{\mathcal{T}}(\tilde x^{k}_{N}))
\end{bmatrix}$$
Also, we rewrite as
![[Jacobian of Stage Inequality#^def]]
to get
$$=\begin{bmatrix}
C^{k}_{0} & D^{k}_{0}  \\[0.5em]
&& C^{k}_{1} & D^{k}_{1}   \\[0.5em]
&&&& \tiny\ddots \\
&&&&& C^{k}_{N-2} & D^{k}_{N-2}  \\[0.5em]
&&&&&&& C^{k}_{N-1} & D^{k}_{N-1} \\[0.5em]
&&&&&&&&&\frac{\partial}{\partial \tilde x^{k}} ( \hat{\mathcal{T}}(\tilde x^{k}_{N}))
\end{bmatrix}$$