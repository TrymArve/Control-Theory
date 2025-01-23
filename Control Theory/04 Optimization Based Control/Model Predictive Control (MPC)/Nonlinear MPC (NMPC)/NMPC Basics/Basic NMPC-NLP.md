---
tags: []
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
$$\begin{align*}
\text{NLP}_{\text{NMPC}}^{k}(\hat{x}_{k}) \triangleq \arg\min_{u^{k}} & \quad J(\hat{x}_{k},u^{k})\\
\text{subject to:}\\
\tilde{x}^{k}_{0} &= \hat{x}_{k} \\
\tilde{x}^{k}_{j+1} &= f_{d}(t_{k+j}, \tilde{x}^{k}_{j},\tilde{u}^{k}_{j}) && \forall j \in \mathbb{Z}_{0,N-1}\\
\tilde{x}^{k}_{j} &\in \mathbb{X} && \forall j \in \mathbb{Z}_{0,N-1}\\
\tilde{u}^{k}_{j} &\in \mathbb{U} && \forall j \in \mathbb{Z}_{0,N-1}\\
\tilde{x}^{k}_{N} &\in \mathbb{X}_{T}\\
0 &\leq h(t_{j},\tilde{x}^{k}_{j},\tilde{u}^{k}_{j}) && \forall j \in \mathbb{Z}_{0,N-1}
\end{align*}$$
^NLP

where $J$ is defined as
![[Basic Cost Function#^cost]]
