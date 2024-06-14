---
tags:
  - Optimization/LMPC
  - Optimization/QP
Note Author:
  - Trym A. Gabrielsen
Theory Author:
  - Sébastien Gros
Reviewed By:
---

$$
\begin{gather*}
\text{QP}_\text{LMPC}^{i}(\hat{x}_{i},x^{ref,i},u^{ref,i}) \triangleq \hspace{3cm} \\[0.5cm]
\arg \min_{\Delta x^{i},\Delta u^{i}} \sum\limits_{j=0}^{H_{i}-1}\frac{1}{2} \begin{bmatrix} \Delta x^{i}_{j} \\ \Delta u^{i}_{j}\end{bmatrix}^{\top} W^{i}_{j} \begin{bmatrix} \Delta x^{i}_{j} \\ \Delta u^{i}_{j}\end{bmatrix} \\[0.3cm]
\begin{aligned}
\text{subject to:} \\
\Delta x^{i}_{0} & =  \hat{x}_{i} - x^{ref,i}_{0}\\
\Delta x^{i}_{j+1} & = A^{i}_{j} \Delta x^{i}_{j} + B^{i}_{j} \Delta u^{i}_{j} + r^{i}_{j} & \forall j \in \mathbb{Z}_{0,H_{i}-1} \\
0 & \leq C^{i}_{j} \Delta x^{i}_{j} + D^{i}_{j} \Delta u^{i}_{j} + h^{i}_{j} & \forall j \in \mathbb{Z}_{0,H_{i}-1}
\end{aligned}
\end{gather*}
$$
^QP
