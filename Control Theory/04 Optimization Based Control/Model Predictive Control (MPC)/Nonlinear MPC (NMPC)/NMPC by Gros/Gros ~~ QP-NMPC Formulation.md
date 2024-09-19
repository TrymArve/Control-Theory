---
tags:
  - Optimization/NMPC
  - Optimization/SQP
  - Optimization/QP
Note Author:
  - Trym A. Gabrielsen
Theory Author:
  - Sébastien Gros
Reviewed By:
---
$$\begin{gather*}
\text{QP}_{\text{NMPC}}^{i}(\hat{x}_{i},\tilde{x}^{i,g_{k}},\tilde{u}^{i,g_{k}},x^{ref,i},u^{ref,i}) \triangleq \hspace{3cm} \\[0.5cm]
\arg \min_{\Delta x^{i},\Delta u^{i}} \quad \sum\limits_{j=0}^{H-1}\frac{1}{2}\begin{bmatrix} \Delta x^{i}_{j} \\ \Delta u^{i}_{j}\end{bmatrix}^{\top} H^{i}_{j} \begin{bmatrix}\Delta x^{i}_{j} \\ \Delta u^{i}_{j}\end{bmatrix} + J^{i\top}_{j} \begin{bmatrix}\Delta x^{i}_{j} \\ \Delta u^{i}_{j}\end{bmatrix}\\[0.3cm]
\begin{aligned}
\text{subject to:}&\\
\Delta x^{i}_{0} & = \hat{x}_{i} - \tilde{x}^{i,g_{i}}_{0}\\
\Delta x^{i}_{j+1} & = A^{i}_{j}\Delta x^{i}_{j} + B^{i}_{j}\Delta u^{i}_{j} + r^{i}_{j} && \forall j \in \mathbb{N}_{0,H-1}\\
0 &\leq C^{i}_{j}\Delta x^{i}_{j} + D^{i}_{j}\Delta u^{i}_{j} + h^{i}_{j}  && \forall j \in \mathbb{N}_{0,H-1}
\end{aligned}
\end{gather*}$$
^QP
