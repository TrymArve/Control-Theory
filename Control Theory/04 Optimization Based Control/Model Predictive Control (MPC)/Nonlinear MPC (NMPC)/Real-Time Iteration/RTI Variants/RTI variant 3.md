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
RTI variant 3 is a special variant, that acts as an alternative to [[RTI variant 2]] when the problem is a Least-Squares problem:
$$\begin{gather*}
\min_{z} \quad \frac{1}{2}  ||r(z)||^{2}_{2} \\[0.3cm]
\begin{aligned}
\text{subject to:}&\\
g(z) & = 0\\
h(z) & \geq 0
\end{aligned}
\end{gather*}$$
^Least-Squares

for some $r: \mathbb{R}^{n_{z}} \mapsto \mathbb{R}^{n_{r}}$.

The RTI-variants QP:
![[RTI-Variants Overview#^RTI-QP-variants]]
![[RTI-Variants Overview#^RTI-QP-variants-vectors]]
is then constructed with fixed Jacobians $H$, $B_{k}$, $C_{k}$ , where 

$$H \triangleq R^{\top}R$$
^Hessian-approximation

for some reasonable $R$, f.ex. $R\triangleq \nabla_{z} r(z^{r})^{\top}$. The vector approximations are then:
$$
\text{RTI-Variant 3:}
\left\{ 
\begin{align*}
\bar{g}'_{k} &= \bar{g}(z_{k})\\
h'_{k} &= h(z_{k})\\
a_{k} &= R^{\top}r(z_{k})
\end{align*}
\right.
$$
^RTI-variant-3


