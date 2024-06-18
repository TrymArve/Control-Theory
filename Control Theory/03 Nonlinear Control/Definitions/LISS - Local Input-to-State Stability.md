---
tags:
  - NonlinearSystems/Definition
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
 
A system is called **Locally ISS*** iff:
- $\exists~\rho>0$
- $\exists~\gamma\in\mathcal{K}$
- $\exists~\beta\in\mathcal{KL}$
such that
- $\forall~x_0 \leq \rho$
- $\forall~u(t):||u(t)||_{\mathcal{L}_\infty} \leq \rho$
- $\forall~t \geq t_0$
we have that
$$ ||x(t)|| \leq \beta(||x_0||,t) + \gamma(||u||_{\mathcal{L}_\infty})$$


**Remarks:** 
- This is essentially just that the [[ISS - Input-to-State Stability|ISS]] property hold in some region around the origin and for small input values.
- Antonio Loria, in his lectures, states that "Malkin's total stability is better known as LISS". (Although, I'm not sure if these definitions are equivalent...)