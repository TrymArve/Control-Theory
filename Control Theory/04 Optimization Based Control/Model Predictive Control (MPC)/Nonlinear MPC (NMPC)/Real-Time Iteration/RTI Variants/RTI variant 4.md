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
RTI variant 4 solves the RTI-variants QP:
![[RTI-Variants Overview#^RTI-QP-variants]]
with fixed Jacobians $H$, $B_{k}$, $C_{k}$ , and approximates the vectors
![[RTI-Variants Overview#^RTI-QP-variants-vectors]]
by evaluating the exact vectors $\bar{g}$, $h$, and $a_{k}$:
$$
\text{RTI-Variant 4:}
\left\{ 
\begin{align*}
\bar{g}'_{k} &= \bar{g}(z_{k})\\
h'_{k} &= h(z_{k})\\
a_{k} &= \nabla_{z} \mathcal{L}(z_{k},\bar{\lambda}_{k},\hat{\lambda}_{k}) +  B_{k}^{\top}\bar{\lambda}_{k} + C_{k}^{\top}\hat{\lambda}_{k}
\end{align*}
\right.
$$
^RTI-variant-4


**Remarks:**
- The full decision vector of the previous solution must be reconstructed in the preparation phase: ![[RTI-Variants Overview#^condensing-reconstructing-z]]which requires to perform a matrix-vector multiplication and two additions online.
- Furthermore, the Lagrangian multipliers must be reconstructed form the previous condensed QP solution, in order to evaluate $a_{k}$.
	- The inequality multipliers are the same for the condensed an non-condensed QPs
	- The equality multipliers can be computed as: 

$$\bar{\lambda}_{k} = (BS^{\top})^{-\top}S(H \Delta z_{k} + a_{k} - C^{\top}\hat{\lambda}_{k})$$^reconstructing-ineq-multipliers


	- This can be done efficiently by recursion: 


$$\begin{align*}
&a \triangleq S(H \Delta z_{k} + a_{k} - C^{\top}\hat{\lambda}_{k}) = \begin{bmatrix}a^{x}_{0}, a^{z}_{0},a^{x}_{1},a^{z}_{1},\dots , a^{x}_{N}\end{bmatrix} \\
&\bar{\lambda} = \begin{bmatrix}\lambda^{x}_{0}, \lambda^{z}_{0},\lambda^{x}_{1},\lambda^{z}_{1},\dots , \lambda^{x}_{N}\end{bmatrix} \\[1.5em]
&\text{(1):}~~ \lambda_{N}^{x} = a_{N}^{x}\\[0.5em]
&\text{(2):}~~ \left. \begin{aligned} \lambda_{i}^{z} &= (Z^{z}_{i})^{-\top}(a_{i}^{z} + (X^{z}_{i})^{\top}\lambda_{i+1}^{x}) \\[0.2em] \lambda_{i}^{x} &= a_{i}^{x} + (X^{x}_{i})^{\top}\lambda_{i+1}^{x} - (Z^{x}_{i})^{\top}\lambda_{i}^{z}\end{aligned}\right\} \forall i = \{N-1, N-2, \dots, 0\}
\end{align*}$$
^reconstructing-eq-multipliers

