---
tags: []
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By: 
Relevant Papers:
---
Consider:
![[Dynamic Constraints#^dynamic-vector]]
![[Decision Variables#^definition-of-z]]

**Jacobian of g:**
$$
\frac{\partial g}{\partial z^{k}} =\begin{bmatrix}
I &  &  & \\[0.5em]
-A^{k}_{0} &
-B^{k}_{0} & I &  &  & \\[0.5em]
& 
&-A^{k}_{1} &
-B^{k}_{1}
&I & &  \\[0.5em]
 &  & 
&&-A^{k}_{2} &
-B^{k}_{2}
& I &  \\[0.5em]
&&&&&& \tiny\ddots \\
&&&&&&& I\\
&&&&&&&-A^{k}_{N-1} &
-B^{k}_{N-1}
&I &\\[0.5em]
&&&&&&&&&\frac{\partial}{\partial \tilde x^{k}_{N}} ( \bar{\mathcal{T}}(\tilde x^{k}_{N}))
\end{bmatrix}$$

where
![[Jacobian of Dynamics#^def]]

# Transpose:
$$\frac{\partial g^{\top}}{\partial z^{k}} = \nabla_{z^{k}}g(z^{k})
=
\begin{bmatrix}
I & -A^{k\top}_{0}  &  & \\[0.5em]
&
-B^{k\top}_{0} &  &  & \\[0.5em]
& I & -A^{k\top}_{1} \\[0.5em]
&& -B^{k\top}_{1}  \\[0.5em]
&& I & -A^{k\top}_{2} \\[0.5em]
&&&-B^{k\top}_{2} \\[0.5em]
&&& I \\[0.5em]
&&&& \tiny\ddots \\
&&&&& -A^{k\top}_{N-1}  \\[0.5em]
&&&&& -B^{k\top}_{N-1}  \\[0.5em]
&&&&&  I & \nabla_{\tilde x^{k}_{N}}\bar{\mathcal{T}}(\tilde x^{k}_{N})
\end{bmatrix}$$
# Derivation:
$$
\frac{\partial g}{\partial z^{k}} = 
\begin{bmatrix}
\frac{\partial}{\partial z^{k}} ( \tilde x^{k}_{0} - \hat x_{k} )\\[0.5em]
\frac{\partial}{\partial z^{k}} ( \tilde x^{k}_{1} - f_{d}(t_{k},\tilde x^{k}_{0}, \tilde u^{k}_{0})) \\[0.5em]
\vdots \\[0.5em]
\frac{\partial}{\partial z^{k}} ( \tilde x^{k}_{j+1} - f_{d}(t_{k+j},\tilde x^{k}_{j}, \tilde u^{k}_{j})) \\[0.5em]
\vdots  \\[0.5em]
\frac{\partial}{\partial z^{k}} ( \tilde x^{k}_{N} - f_{d}(t_{k+N-1},\tilde x^{k}_{N-1}, \tilde u^{k}_{N-1})) \\[0.5em]
\frac{\partial}{\partial z^{k}} ( \bar{\mathcal{T}}(\tilde x^{k}_{N}))
\end{bmatrix}
$$
$$=\begin{bmatrix}
\frac{\partial}{\partial z^{k}_{0}} ( \tilde x^{k}_{0} - \hat x_{k} ) & [0] & \cdots\\[0.5em]
\frac{\partial}{\partial z^{k}_{0}} ( \tilde x^{k}_{1} - f_{d}(t_{k},\tilde x^{k}_{0}, \tilde u^{k}_{0})) & \frac{\partial}{\partial z^{k}_{1}} ( \tilde x^{k}_{1} - f_{d}(t_{k},\tilde x^{k}_{0}, \tilde u^{k}_{0})) & [0] & \cdots\\[0.5em]
[0] & \frac{\partial}{\partial z^{k}_{1}} ( \tilde x^{k}_{2} - f_{d}(t_{k+1},\tilde x^{k}_{1}, \tilde u^{k}_{1})) & \frac{\partial}{\partial z^{k}_{2}} ( \tilde x^{k}_{2} - f_{d}(t_{k+1},\tilde x^{k}_{1}, \tilde u^{k}_{1})) & [0] \\[0.5em]
\vdots & [0] & \frac{\partial}{\partial z^{k}_{2}} ( \tilde x^{k}_{3} - f_{d}(t_{k+2},\tilde x^{k}_{2}, \tilde u^{k}_{2})) & \frac{\partial}{\partial z^{k}_{3}} ( \tilde x^{k}_{3} - f_{d}(t_{k+2},\tilde x^{k}_{2}, \tilde u^{k}_{2})) \\[0.5em]
&&&& \tiny\ddots \\
&&&&&\frac{\partial}{\partial z^{k}_{N-1}} ( \tilde x^{k}_{N} - f_{d}(t_{k+N-1},\tilde x^{k}_{N-1}, \tilde u^{k}_{N-1})) & \frac{\partial}{\partial z^{k}_{N}} ( \tilde x^{k}_{N} - f_{d}(t_{k+N-1},\tilde x^{k}_{N-1}, \tilde u^{k}_{N-1})) \\[0.5em]
&&&&&[0]&\frac{\partial}{\partial z^{k}} ( \bar{\mathcal{T}}(\tilde x^{k}_{N}))
\end{bmatrix}$$
$$=\begin{bmatrix}
\frac{\partial}{\partial z^{k}_{0}} (\tilde x^{k}_{0}) & [0] & \cdots\\[0.5em]
-\frac{\partial}{\partial z^{k}_{0}} f_{d}(t_{k},\tilde x^{k}_{0}, \tilde u^{k}_{0}) & \frac{\partial}{\partial z^{k}_{1}} ( \tilde x^{k}_{1}) & [0] & \cdots\\[0.5em]
[0] & -\frac{\partial}{\partial z^{k}_{1}} f_{d}(t_{k+1},\tilde x^{k}_{1}, \tilde u^{k}_{1}) & \frac{\partial}{\partial z^{k}_{2}} ( \tilde x^{k}_{2}) & [0] \\[0.5em]
\vdots & [0] & -\frac{\partial}{\partial z^{k}_{2}} f_{d}(t_{k+2},\tilde x^{k}_{2}, \tilde u^{k}_{2}) & \frac{\partial}{\partial z^{k}_{3}} ( \tilde x^{k}_{3}) \\[0.5em]
&&&& \tiny\ddots \\
&&&&&-\frac{\partial}{\partial z^{k}_{N-1}} f_{d}(t_{k+N-1},\tilde x^{k}_{N-1}, \tilde u^{k}_{N-1}) & \frac{\partial}{\partial z^{k}_{N}} ( \tilde x^{k}_{N}) \\[0.5em]
&&&&&[0]&\frac{\partial}{\partial z^{k}_{N}} ( \bar{\mathcal{T}}(\tilde x^{k}_{N}))
\end{bmatrix}$$
We have
$$\frac{\partial}{\partial z^{k}_{j}} \tilde x^{k}_{j} = \begin{bmatrix}\frac{\partial}{\partial \tilde x^{k}_{j}} \tilde x^{k}_{j} & \frac{\partial}{\partial \tilde u^{k}_{j}} \tilde x^{k}_{j}\end{bmatrix} = \begin{bmatrix}I & [0]\,\end{bmatrix} \quad\forall j\in \mathbb{Z}_{0,N}$$
and by using 
![[Jacobian of Dynamics#^def]]
we also have that
$$\frac{\partial}{\partial z^{k}_{j}}~ f_{d}(t_{k+j},\tilde x^{k}_{j}, \tilde u^{k}_{j}) = 
\begin{bmatrix}
\frac{\partial}{\partial \tilde x^{k}_{j}}~ f_{d}(t_{k+j},\tilde x^{k}_{j}, \tilde u^{k}_{j}) &
\frac{\partial}{\partial \tilde u^{k}_{j}}~ f_{d}(t_{k+j},\tilde x^{k}_{j}, \tilde u^{k}_{j})
\end{bmatrix}
= 
\begin{bmatrix}
A^{k}_{j} &
B^{k}_{j}
\end{bmatrix}
$$
and note
$$z^{k}_{N} = \tilde x^{k}_{N}$$
Then we finally get
$$
\frac{\partial g}{\partial z^{k}} 
=\begin{bmatrix}
\begin{bmatrix}I & [0]\,\end{bmatrix}& [0] & \cdots\\[0.5em]
-\begin{bmatrix}
A^{k}_{0} &
B^{k}_{0}
\end{bmatrix}& \begin{bmatrix}I & [0]\,\end{bmatrix} & [0] & \cdots\\[0.5em]
[0] & -\begin{bmatrix}
A^{k}_{1} &
B^{k}_{1}
\end{bmatrix} &\begin{bmatrix}I & [0]\,\end{bmatrix} & [0] \\[0.5em]
\vdots & [0] & -\begin{bmatrix}
A^{k}_{2} &
B^{k}_{2}
\end{bmatrix} & \begin{bmatrix}I & [0]\,\end{bmatrix} \\[0.5em]
&&&& \tiny\ddots \\
&&&&&-\begin{bmatrix}
A^{k}_{N-1} &
B^{k}_{N-1}
\end{bmatrix} & I \\[0.5em]
&&&&&[0]&\frac{\partial}{\partial \tilde x^{k}_{N}} ( \bar{\mathcal{T}}(\tilde x^{k}_{N}))
\end{bmatrix}$$
simplify:
$$
\frac{\partial g}{\partial z^{k}} =\begin{bmatrix}
I &  &  & \\[0.5em]
-A^{k}_{0} &
-B^{k}_{0} & I &  &  & \\[0.5em]
& 
&-A^{k}_{1} &
-B^{k}_{1}
&I & &  \\[0.5em]
 &  & 
&&-A^{k}_{2} &
-B^{k}_{2}
& I &  \\[0.5em]
&&&&&& \tiny\ddots \\
&&&&&&& I\\
&&&&&&&-A^{k}_{N-1} &
-B^{k}_{N-1}
&I &\\[0.5em]
&&&&&&&&&\frac{\partial}{\partial \tilde x^{k}_{N}} ( \bar{\mathcal{T}}(\tilde x^{k}_{N}))
\end{bmatrix}$$