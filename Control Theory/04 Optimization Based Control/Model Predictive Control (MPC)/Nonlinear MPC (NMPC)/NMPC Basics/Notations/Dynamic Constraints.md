---
tags: []
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By: 
Relevant Papers:
---
We define the dynamic constraint vector:
$$g \triangleq 
\begin{bmatrix}
\begin{align*}
g_{-1} \triangleq &~~ \tilde x^{k}_{0} - \hat x_{k} \\[0.5em]
g_{0} \triangleq &~~ \tilde x^{k}_{1} - f_{d}(t_{k},\tilde x^{k}_{0}, \tilde u^{k}_{0}) \\[0.5em]
&\vdots \\[0.5em]
g_{j} \triangleq &~~ \tilde x^{k}_{j+1} - f_{d}(t_{k+j},\tilde x^{k}_{j}, \tilde u^{k}_{j}) \\[0.5em]
&\vdots  \\[0.5em]
g_{N-1} \triangleq &~~ \tilde x^{k}_{N} - f_{d}(t_{k+N-1},\tilde x^{k}_{N-1}, \tilde u^{k}_{N-1}) \\[0.5em]
g_{N} \triangleq &~~ \bar{\mathcal{T}}(\tilde x^{k}_{N})
\end{align*}
\end{bmatrix}$$

^dynamic-vector

