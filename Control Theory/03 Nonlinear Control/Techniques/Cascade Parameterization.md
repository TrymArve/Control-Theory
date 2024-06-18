---
tags:
  - NonlinearSystems/Technique
Note Author:
  - Trym A. Gabrielsen
Theory Author:
  - Antonio Loría
Reviewed By:
---
Consider: ![[Consider - Feedback Interconnection#^feedback-interconnected-system]]
To break the loop, we can view system $\Sigma_2$ as being parameterized by the solution $x_1^\circ(t)$ to system $\Sigma_1$. 
This is despite the solution of $\Sigma_1$ being dependent on the solution of $\Sigma_2$. We sort of pretend that we know what the solution $x_1^\circ(t)$ looks like for any trajectory $x_2^\circ(t)$. Then we just insert that solution into the dynamics of $\Sigma_2$, and end up with an uncontrolled system:
$$\Sigma_2':\quad \dot{x}_2 = f_2(t,x_1^\circ(t),x_2)$$
That then feeds into system $\Sigma_1$, to create a cascaded system instead:

$$
\begin{align}
& \Sigma_1 \quad : \quad \dot{x}_1 = f_1(t,x_1) + g(t,x_1,x_2) \\
& \Sigma_2' \quad : \quad \dot{x}_2 = f_2(t,x_1^\circ(t),x_2)
\end{align}
$$
^cascaded-parameterization

A remark about this observation is that we now see that we can use methods for cascaded systems to analyze feedback-interconnected systems, provided that we have [[Forward Completeness]].