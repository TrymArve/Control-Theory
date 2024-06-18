---
tags:
  - Optimization/LMPC
  - Optimization/SQP
  - Optimization/NMPC/RTI
Note Author:
  - Trym A. Gabrielsen
Theory Author:
  - Sébastien Gros
Reviewed By:
---
#Unfinished 
Based on [[Gros ~ LMPC]], [[Gros ~ NMPC]], and [[Gros ~ SQP for NMPC]].


# Similar QP formulations
By
- [[Lemma - (QP for NMPC) vs. (LMPC)]], 
we have that the first iteration of the 
- [[Gros ~ SQP for NMPC|SQP-like algorithm for NMPC]], 
is equal to the step taken in LPMC, if one uses the reference as the initial guess for the SQP step. *(given the same step size $\alpha$)*

That is: $$u^{\text{NMPC}}_{i} = u^{\text{LMPC}}_{i}$$ whenever $$\begin{align*}
u^{\text{NMPC}}_{i} & = \tilde{u}^{i}_{0}\\
u^{\text{LMPC}}_{i} & = u^{ref,i}_{0} + \Delta u^ {i}_{0}\\[0.5cm]
\text{where:}\\
\Delta u^ {i}_{0} &\leftarrow \text{QP}_\text{LMPC}^{i}(\hat{x}_{i},x^{ref,i},u^{ref,i})\\
\tilde{u}^{i}_{0} & \leftarrow \text{SQP}^{i}_{\text{NMPC}}(\hat{x}_{i},\tilde{x}^{i,g_{0}},\tilde{u}^{i,g_{0}},x^{ref,i},u^{ref,i},k_{max})\\[0.5cm]
\text{with:}\\
\tilde{x}^{i,g_{0}} &= x^{ref,i}\\
\tilde{u}^{i,g_{0}} &= u^{ref,i}\\
k_{max} &= 1
\end{align*}$$


The figure below shown this phenomenon for a simple dynamical system: ![[LMPC vs NMPC - 1 SQP step.png|400]]
*Image from "From Linear to Nonlinear MPC: Bridging the Gap via Real-Time Iteration" by Gros, Zanon, Quirynen, Bemporad, and Diehl*


The [[Gros ~ RTI (simplified version)|simplified RTI algorithm]] shows that an Real-Time Iteration scheme, taking only one full newton step of of the [[Gros ~~ SQP-NMPC Algorithm|SQP algorithm for NMPC]] each sample, we obtain an algorithm very similar to LMPC. In fact, when following a reference precisely, the two algorithms are the same.

The [[Gros ~ RTI|full RTI algorithm]] takes advantage of the fact that the dynamics are linearized at the previous guess, **which is known!**, and starts evaluating the linearized system matrices in advance of receiving a system estimate at the next sampling time. This makes it so that like in LMPC, the linearizations are already known at the time of receiving a state estimate, and only the solution to the QP must be obtained. Therefore, an RTI scheme can achieve almost the sampling frequency as LMPC.