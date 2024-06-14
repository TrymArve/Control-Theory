---
tags:
  - Optimization/LMPC
Note Author:
  - Trym A. Gabrielsen
Theory Author:
  - Sébastien Gros
Reviewed By:
---
Notation: [[Optimization#Dynamic Optimization / MPC|here]]
OCP: ![[Optimal Control Problem#^OCP]]

**LMPC Controller:**
$$u_{i}^{LMPC} \triangleq u^{ref,i}_{0} + \Delta u^{i}_{0}~,\qquad \Delta u^{i}_{0} \leftarrow \text{QP}_\text{LMPC}^{i}(\hat{x}_{i},x^{ref,i},u^{ref,i})$$
![[Gros ~~ QP-LMPC Formulation#^QP]]

**Where** 
- $0 \prec W^{i}_{j} = W^{i^{\top}}_{j} \in \mathbb{R}^{n_{x}\times n_{x}}$  is a weight matrix
- The (discrete) dynamics and constraints are linearized about the reference trajectory as follows: ![[Gros ~~ QP-LMPC Linearizations#^Linearizations]]
- The correction terms are defined by ![[Gros ~~ QP-LMPC Correction Terms#^Corrections]]



**Remark:**
- Note that if the reference, $(x^{ref},u^{ref})$, remains the constant through operation, we have that $$\begin{align*}
A^{i}_{H} = A^{i+1}_{H-1} = A^{i+2}_{H-2} = \cdots = A^{i+H-1}_{1} = A^{i+H}_{0}\\
B^{i}_{H} = B^{i+1}_{H-1} = B^{i+2}_{H-2} = \cdots = B^{i+H-1}_{1} = B^{i+H}_{0}\\
C^{i}_{H} = C^{i+1}_{H-1} = C^{i+2}_{H-2} = \cdots = C^{i+H-1}_{1} = C^{i+H}_{0}\\
D^{i}_{H} = D^{i+1}_{H-1} = D^{i+2}_{H-2} = \cdots = D^{i+H-1}_{1} = D^{i+H}_{0}
\end{align*}$$
- The reference trajectory at time $t_{i}$, that is; $x^{ref,i}$, does not have to simply be the previous reference; $x^{ref,i-1}$, shifted by one. If the original reference; $x^{ref}$, remains the same, then this is the case. But in many practical cases, one might change the reference from time to time, slightly, to adjust based on new information.
- Note that there is no cost/constraint associated with the last state within the horizon; $x^{i}_{H_{i}}$, which should be accounted for in an implementation.