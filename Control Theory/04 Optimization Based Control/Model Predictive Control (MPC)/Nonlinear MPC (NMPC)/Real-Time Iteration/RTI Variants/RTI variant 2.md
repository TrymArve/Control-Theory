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
RTI variant 2 solves the RTI-variants QP:
![[RTI-Variants Overview#^RTI-QP-variants]]
with fixed Jacobians $H$, $B_{k}$, $C_{k}$ , and approximates the vectors
![[RTI-Variants Overview#^RTI-QP-variants-vectors]]
by evaluating the exact vectors $\bar{g}$ and $h$, and using a first order approximation $a_{k}$ of the cost-vector:
$$
\begin{align*}
\text{RTI-Variant 2:}
& \left\{ 
\begin{aligned}
\bar{g}'_{k} &= \bar{g}(z_{k})\\
h'_{k} &= h(z_{k})\\
a_{k} &= a + H(z_{k} - z_{k}^{r})
\end{aligned}
\right.
\\[0.4em]
a & \triangleq \nabla_{z} \mathcal{L}(z_{k}^{r},\bar{\lambda}_{k}^{r},\hat{\lambda}_{k}^{r})^{\top} + \bar{\lambda}^{r\top}_{k} B_{k} + \hat{\lambda}_{k}^{r\top}C_{k}
\end{align*}
$$
^RTI-variant-2


#### Condensing:
The condensed vectors $m(\bar{g}')$, $a^{c}_{k}$ and $h^{c}_{k}$ are not constant, as for variant 1, and must be computed online.
We can compute $m$ by recursion as follows: 
1. Consider $$\begin{align*} m(\bar{g}') &= \begin{bmatrix}m_{0}^{x}, m_{0}^{z}, m^{u}_{0}, m_{1}^{x}, m_{1}^{z}, m^{u}_{1},\cdots, m_{N}^{x}\end{bmatrix} \\ \bar{g}' &= \begin{bmatrix}b_{0}^{x}, b_{0}^{z}, b_{1}^{x}, b_{1}^{z},\cdots, b_{N}^{x}\end{bmatrix}\end{align*}$$
2. Start with $$m_{0}^{x} \triangleq b_{0}^{x}$$
3. Then, for $i \in \{0,1,\dots,N-1\}$, compute $$\begin{align*}
m_{i}^{u} &\triangleq 0 \\
m_{i}^{z} &\triangleq -(Z^{z}_{i})^{-1}(b_{i}^{z} + Z^{x}_{i}m^{x}_{i}) \\
m^{x}_{i+1} &\triangleq b^{x}_{i+1} + X^{x}_{i}m^{x}_{i} + X^{z}_{i}m^{z}_{i}
\end{align*}$$
*(What is $Z$ and $X$ ?)*
Then, the remaining vectors are computed as $$\begin{align*}
a^{c}_{k} &= M^{\top}(H\cdot m(\bar{g}') + a_{k})\\[0.2em]
h^{c}_{k} &= C\cdot m(\bar{g}') + h'_{k}
\end{align*}$$

#### Remarks:
- The full decision vector of the previous solution must be reconstructed in the preparation phase: ![[RTI-Variants Overview#^condensing-reconstructing-z]]which requires to perform a matrix-vector multiplication and two additions online.
- When this RTI step is applied iteratively on the same problem, that is; if the initial condition does not change, then the sequence of solutions converge to the solution of a perturbed QP problem: $$\begin{gather*}
\min_{z} \quad \frac{1}{2} (z-z^{r})^{\top}\, H \, (z-z^{r}) + (a_{k}-e)^{\top}z\\[0.3cm]
\begin{aligned}
\text{subject to:}&\\
g(z) & = 0\\
h(z) & \geq 0
\end{aligned}
\end{gather*}$$where the perturbed term $e$ is linear in the constraint Jacobian errors: $$e \triangleq (\nabla_{z}g(z^{*}) - B^{\top})\bar{\lambda}^{*} + (\nabla_{z}h(z^{*}) - C^{\top})\hat{\lambda}^{*}$$with $(z^{*},\bar{\lambda}^{*},\hat{\lambda}^{*})$ begin the solution of the perturbed QP.
- Proof: the KKT conditions of the perturbed QP are satisfied.

