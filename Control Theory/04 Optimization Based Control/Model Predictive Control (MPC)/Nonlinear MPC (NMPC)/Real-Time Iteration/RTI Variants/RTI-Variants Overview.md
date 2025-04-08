---
tags:
  - Optimization/NMPC/RTI
Note Author:
  - Trym A. Gabrielsen
Theory Author:
  - Moritz Diehl
Reviewed By: 
Relevant Papers: '"Real-Time PDE-Constrained Optimization" (book, 2007), "Multi-level Iterations for Economic Nonlinear Model Predictive Control" (2021)'
---
# RTI Variants
The standard Real-Time Iterations (RTI) scheme is a way to approximate the classical NMPC controller, while achieving much higher control rates. It does so by only performing one Newton step between samples, and thus continually providing approximate control signals, instead of providing optimal control signals that are only updated with some relatively large interval.

The idea of the **RTI Variants** is to make the control rate even faster, though at the expense of worse approximations. This is done by, rather than evaluating the exact Hessian and Jacobian matrices that appear in the [[Gros ~~ QP-NMPC Formulation|RTI-QP]], they are only approximated, and are kept constant, allowing them to be precomputed, saving valuable computation time online. The Hessians and Jacobians are computed in advance about some chosen reference trajectory, similarly to LMPC. The remaining vectors in [[Gros ~~ QP-NMPC Formulation|RTI-QP]] are computed online, but depending on the "variant", they are approximated to varying accuracy.
The difference between the variants is the amount of computation that is done online, which subsequently gives varying degrees of accuracy and control rates.

## The Standard RTI scheme
In the standard RTI scheme, the Hessian of the Lagrangian (w.r.t. primal) is approximated (may also be exact), and the following QP is constructed to provide a Newton-Type step:
![[Gros ~~ QP-NMPC Formulation#^QP]]
where
![[Gros ~~ QP-NMPC Linearizations#^Linearizations]]
and
![[Gros ~~ QP-NMPC Correction Terms#^Correction-Terms]]


## Convenient QP Formulation:
In "Real-Time PDE constrained optimization" (2007), for convenience, they write a standard QP-based Newton-type step as:
$$\begin{gather*}
\min_{\Delta z} \quad \frac{1}{2} \Delta z^{\top}\, H \, \Delta z + \begin{pmatrix}\nabla_{z} \mathcal{L}(z_{k},\bar{\lambda}_{k},\hat{\lambda}_{k})^{\top} + \bar{\lambda}^{\top}_{k}B_{k} + \hat{\lambda}_{k}^{\top}C_{k}\end{pmatrix} \Delta z\\[0.3cm]
\begin{aligned}
\text{subject to:}&\\
g(z_{k},\hat{x}_{k}) + B_{k}\Delta z & = 0\\
h(z_{k}) + C_{k}\Delta z & \geq 0
\end{aligned}
\end{gather*}$$
^RTI-QP-convenient

where
$$\begin{align*}
H_{k} &\approx \nabla^{2}_{z} \mathcal{L}(z_{k},\bar{\lambda}_{k},\hat{\lambda}_{k}) \\
B_{k} &\approx \nabla_{z}g(z_{k},\hat{x}_{k}) \\
C_{k} &\approx \nabla_{z}h(z_{k})
\end{align*}$$
^RTI-QP-convenient-matrices


## RTI Variants QP with inexact Jacobians
In the RTI variants, with inexact Jacobians, we instead solve the following QP:
$$\begin{gather*}
\min_{\Delta z} \quad \frac{1}{2} \Delta z^{\top}\, H \, \Delta z + a_{k}^{\top} \Delta z\\[0.3cm]
\begin{aligned}
\text{subject to:}&\\
\bar{g}'_{k} + L \hat{x}_{k} + B_{k}\Delta z & = 0\\
h' + C_{k}\Delta z & \geq 0
\end{aligned}
\end{gather*}$$
^RTI-QP-variants

with $L \triangleq \begin{bmatrix}I & 0 & \cdots & 0\end{bmatrix}^{\top}$
where
$$\begin{align*}
\bar{g}'_{k} &\approx \bar{g}(z_{k}) = \begin{bmatrix}0 \\ \vdots \\ 0  \\ g_{nx+1}(z_{k}) \\ \vdots \\ g_{end}(z_{k})\end{bmatrix} ~~ \text{(g without initial value embedding)}\\
h'_{k} &\approx h(z_{k})\\
a_{k}^{\top} &\approx \nabla_{z} \mathcal{L}(z_{k},\bar{\lambda}_{k},\hat{\lambda}_{k})^{\top} + \bar{\lambda}^{\top}_{k} B_{k} + \hat{\lambda}_{k}^{\top}C_{k}
\end{align*}$$
^RTI-QP-variants-vectors

### Choice of Constant Jacobian approximations:
Often, a good choice of approximations $H$, $B$, and $C$, are:
$$\begin{align*}
H_{k} &= \nabla^{2}_{z} \mathcal{L}(z^{r}_{k}, \bar{\lambda}^{r}_{k}, \hat{\lambda}^{r}_{k}) \\
B_{k} &= \nabla_{z} g(z_{k}^{r})^{\top}\\
C_{k} &= \nabla_{z} h(z_{k})^{\top}
\end{align*}$$
^RTI-QP-variants-jacobians-reference


about some reference solution $(z_{k}^{r},\bar{\lambda}_{k}^{r},\hat{\lambda}_{k}^{r})$.



### Condensed QP
In all RTI schemes, it is standard to [[Condensing|condense]] the QP before solving it. This is done by rewriting the state step variables $\Delta x$ as a function of the input step variables $\Delta u$, via the [[Gros ~~ QP-NMPC Linearizations|linearized system dynamics]]. One can then find matrices $M$ and $\tilde{L}$, and a function $m(\bar{g}'_{k})$, such that the complete decision vector can then be reconstructed as:

$$\Delta z(\Delta u) = m(\bar{g}'_{k}) + \tilde{L}\hat{x}_{k}+ M \Delta u$$
^condensing-reconstructing-z


The condensed QP then looks like:
$$\begin{gather*}
\min_{\Delta u} \quad \frac{1}{2} \Delta u^{\top}\, H^{c} \, \Delta u + (a^{c}_{k} + \tilde{H}\hat{x}_{k} )^{\top} \Delta u\\[0.3cm]
\begin{aligned}
\text{subject to:}&\\
(h^{c}_{k} + \tilde{C}_{k}\hat{x}_{k}) + C^{c}\Delta u & \geq 0
\end{aligned}
\end{gather*}$$
^condensing-QP

where
$$\begin{align*}
H^{c} &\triangleq M^{\top}HM\\
\tilde{H} &\triangleq M^{\top}H\tilde{L}\\
\tilde{C} &\triangleq C\tilde{L}\\
C^{c} &\triangleq CM
\end{align*}$$
^condensing-matrices

The online computational burden is then reduced to evaluating:
$$\begin{gather*}
m(\bar{g}'_{k})\\
a^{c}_{k}(a_{k},\bar{g}'_{k}) + \tilde{H}\hat{x}_{k}\\
h^{c}_{k}(a_{k},\bar{g}'_{k}) + \tilde{C}_{k}\hat{x}_{k}
\end{gather*}$$
^condensing-online-computation

### RTI Variants
What differentiates the different RTI variants is the method of approximating [[RTI-Variants Overview#^RTI-QP-variants-vectors|the vectors]] $\bar{g}'_{k}$, $h'_{k}$, and $a_{k}^{\top}$.


#### Variant 1 - Linear MPC
Uses constant approximation of all vectors:
![[RTI variant 1#^RTI-variant-1]]

#### Variant 2 - Feasibility Improvement
Computes the exact constraint vectors, and a first order approximation of the optimality vector:
![[RTI variant 2#^RTI-variant-2]]

#### Variant 3 - Least Squares
Variant 3 is a special case of variant 2, tailored for Least Squares problems: ![[RTI variant 3#^Least-Squares]]
where the hessian is approximated as ![[RTI variant 3#^Hessian-approximation]]typically with $R\triangleq \nabla_{z} r(z^{r})^{\top}$.
The vectors are then evaluated as:
![[RTI variant 3#^RTI-variant-3]]

#### Variant 4 - Optimality Improvement
In variant 4, all vectors are evaluated exactly, leaving only the fixed Jacobians inexact:
![[RTI variant 4#^RTI-variant-4]]

### Summary
![[RTI-Variants summary.png]]
