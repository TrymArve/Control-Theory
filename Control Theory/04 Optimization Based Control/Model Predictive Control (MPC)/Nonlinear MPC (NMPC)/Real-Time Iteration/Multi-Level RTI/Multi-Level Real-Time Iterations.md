---
tags:
  - Unfinished
Note Author:
  - Trym A. Gabrielsen
Theory Author:
  - Moritz Diehl
Reviewed By: 
Relevant Papers: '"Real-Time PDE Constrained Optimization"'
---
The multi-level RTI scheme uses a combination of the various [[RTI-Variants Overview|RTI-variants]] and the standard [[Gros ~ RTI|RTI]] scheme. The controller uses RTI iterations at 4 different 'levels'; A, B, C, and D, each corresponding to an RTI variant, each level using cruder and cruder approximations of the under lying NLP, though achieving faster and faster control rates as going from the slowest layer, D, to the fastest, A.

The idea is that, because varying evaluations take different amounts of time, the fast evaluations can be used for control during the time the slower evaluations are computed. This results in an asynchronous QP data updating scheme, where the QP Jacobians/vectors are computed and updated on the fly. By controlling this way, the RTI scheme with the control rate of LMPC is uninterrupted, yet continually updated to yield higher accuracy control than LMPC, nearing that of NMPC.
#### Level A - (RTI variant 1 / LMPC)
The fastest level, A, is simply [[RTI variant 1]], solving:
![[RTI-Variants Overview#^RTI-QP-variants]]
which is a constant QP, only with varying initial condition $\hat{x}_{k}$.
The matrices and vectors are provided by the higher levels.

#### Level B - (RTI variant 2 / feasibility improvement)
The second fastest level, B, evaluates and updated QP the vectors 
![[RTI variant 2#^RTI-variant-2]]
at the solution $z_{k}$ of level A, at iterate $k=k_{b}\cdot n_{a/b}$. Note: $$\begin{align*}
k_{b} &\text{ - level B iteration}\\
n_{a/b} &\text{ - number of A iterations per B iteration}
\end{align*}$$
The solution must first be reconstructed:
$$\begin{align*}
\Delta z_{k} &= m(\bar{g}'_{(k_{b}-1)n_{a/b}}) + \tilde{L}\hat{x}_{k}+ M \Delta u_{k}\\
z_{k} &= z_{(k_{b}-1)n_{b}} + \Delta z_{k}
\end{align*}$$
where $(k_{b}-1)n_{a/b}$ is the iteration number of level A, at the previous iterate in level B.
The vectors can then be evaluated, where $z_{k}^{r}$ is provided by level C.
Lastly, the QP must be [[RTI variant 2#Condensing|recondensed]], which should be completed in time, such that the QP is updated by the next B iteration $(k_{b}+1)n_{a/b}$.

#### Level C - (RTI variant 4 / optimality improvement)
Level C is even slower than B, and regularly updates the optimality vector:
$$a_{k} = \nabla_{z} \mathcal{L}(z_{k},\bar{\lambda}_{k},\hat{\lambda}_{k}) +  B_{k}^{\top}\bar{\lambda}_{k} + C_{k}^{\top}\hat{\lambda}_{k}$$
which is similar to an extension to RTI variant 4:![[RTI variant 4#^RTI-variant-4]]
At iteration $k = k_{c}\cdot n_{a/b}n_{b/c}$, from the reconstruction of $z_{k}$ in level B, use ![[RTI variant 4#^reconstructing-ineq-multipliers]]![[RTI variant 4#^reconstructing-eq-multipliers]]
to compute the Lagrangian multipliers. Then evaluate the optimality vector. We then provide the solution $z_{k}^{r}$ *(which was reconstructed in level B)*, and the optimality vector $a_{k}$ as, respectively, the reference solution and $a$ vector used in level B until the next level C iterate $k = (k_{c}+1)n_{a/b}n_{b/c}$.

#### Level D - (Standard RTI / Jacobian updates)
The last and slowest level, D, regularly computes new linearizations to update the Hessian and Jacobians $H$, $B$, and $C$, according to ![[RTI-Variants Overview#^RTI-QP-convenient-matrices]]
where the solution $(z_{k},\bar{\lambda}_{k},\hat{\lambda}_{k})$ is provided by level C at iterate $k = k_{d}\cdot n_{a/b}n_{b/c}n_{c/d}$.
An exact evaluation or an approximation of these matrices may be used.
Furthermore, the condensing matrices must be updated as well: $M$, $\tilde{L}$, and ![[RTI-Variants Overview#^condensing-matrices]]
All computations should be completed such that the QP is updated by iteration $k = k_{d}\cdot n_{a/b}n_{b/c}n_{c/d}$, at which point the level begin evaluating the next Jacobians immediately.