---
tags:
  - Optimization/NMPC
  - Optimization/NLP
Note Author:
  - Trym A. Gabrielsen
Theory Author:
  - Sébastien Gros
Reviewed By:
---

$$\begin{gather*}
\text{NLP}_{\text{NMPC}}^{i}(\hat{x}_{i},x^{ref,i},u^{ref,i}) \triangleq \hspace{4cm} \\[0.5cm]
\arg \min_{\tilde{x}^{i},\tilde{u}^{i}} \quad \sum\limits_{j=0}^{H-1}\frac{1}{2}\begin{bmatrix}\tilde{x}^{i}_{j}-x^{ref,i}_{j} \\ \tilde{u}^{i}_{j}-u^{ref,i}_{j}\end{bmatrix}^{\top} W^{i}_{j} \begin{bmatrix}\tilde{x}^{i}_{j}-x^{ref,i}_{j} \\ \tilde{u}^{i}_{j}-u^{ref,i}_{j}\end{bmatrix}\\[0.3cm]
\begin{aligned}
\text{subject to:}&\\
\tilde{x}^{i}_{0} & = \hat{x}_{i}\\
\tilde{x}^{i}_{j+1} & = f_d(t_{j},\tilde{x}^{i}_{j},\tilde{u}^{i}_{j}) && \forall j \in \mathbb{N}_{0,N-1}\\
0 &\leq h(t_{j},\tilde{x}^{i}_{j},\tilde{u}^{i}_{j})  && \forall j \in \mathbb{N}_{0,N-1}
\end{aligned}
\end{gather*}$$
^NLP

**Remarks:**
- The cost is assumed to be quadratic, although this is not necessary in general. 
	- If the cost is non-quadratic, the $W$ is taken to be the hessian of the cost.