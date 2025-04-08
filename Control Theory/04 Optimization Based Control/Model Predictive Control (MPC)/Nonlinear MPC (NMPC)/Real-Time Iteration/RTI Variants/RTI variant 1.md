---
tags:
  - Optimization/NMPC/RTI
Note Author:
  - Trym A. Gabrielsen
Theory Author:
  - Moritz Diehl
Reviewed By: 
Relevant Papers: '"Real-Time PDE Constrained Optimization"'
---
RTI variant 1 solves the RTI-variants QP:
![[RTI-Variants Overview#^RTI-QP-variants]]
with fixed Jacobians $H$, $B_{k}$, $C_{k}$ , and approximates the vectors
![[RTI-Variants Overview#^RTI-QP-variants-vectors]]
by using a constant approximation, which is simply the exact evaluation of the vectors at a reference solution $(z_{k}^{r},\bar{\lambda}_{k}^{r},\hat{\lambda}_{k}^{r})$:
$$
\text{RTI-Variant 1:}
\left\{
\begin{align*}
\bar{g}'_{k} &= \bar{g}(z_{k}^{r})\\
h'_{k} &= h(z_{k}^{r})\\
a_{k}^{\top} &= \nabla_{z} \mathcal{L}(z_{k}^{r},\bar{\lambda}_{k}^{r},\hat{\lambda}_{k}^{r})^{\top} + \bar{\lambda}^{r\top}_{k} B_{k} + \hat{\lambda}_{k}^{r\top}C_{k}
\end{align*}
\right.$$
^RTI-variant-1

**Condensing:**
Since the vectors are fixed, the condensing computations are reduced to a vector-matrix computation and an addition online.

**Remarks:**
- Note that when the reference solution is the solution at some reference trajectory, and the Jacobians are computed at the same reference, this variant is simply Linear MPC.
	- (if condensing is used, then it is equal to LMPC with condensing)
- It is desirable that the condensed Hessian $H^{c}$ is positive definite, to ensure a unique solution of the condensed QP.
	- This hessian might be adjusted online to ensure positive definiteness.
- Note that with this approach, there is no required transfer of information from one solution to the next.
	- It can be beneficial to transfer information about the active set, if f.ex. an active set solver is used.