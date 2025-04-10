---
tags:
  - Optimization/NMPC
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By: 
Relevant Papers: '"The advanced-step NMPC controller: Optimality, stability and robustness", "Nonlinear predictive control and moving horizon estimation: An introductory overview"'
---
Consider the discrete system:
![[Consider - Discrete NTI#^system]]

Assume that the real plant follows the dynamics:
$$x_{k+1} = f_{d}(x_{k},u_{k}) + g(x_{k},u_{k},w_{k})$$
such that any disturbances and model mismatch is captured by $g(\cdot)$.

Consider the [[Dynamic Optimization|dynamic optimization problem]]
![[Basic NMPC-NLP#^NLP]]
with cost
![[Basic Cost Function#^cost]]
^idealNMPC

Then the *Ideal NMPC (iNMPC) controller* defines the feedback control law
$$\begin{align*}
u_{k} = h_{\text{iNMPC}}(\hat{x}_{k}) = u^{k,*}_{0}\\
u^{k,*}\triangleq\text{NLP}_{\text{NMPC}}^{k}(\hat{x}_{k})
\end{align*}$$
And does so without any computational delay.