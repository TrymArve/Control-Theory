---
tags:
  - NonlinearSystems/Definition
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---


Consider: ![[Consider - Controlled NTI#^system]]
where:
- $\boldsymbol{u}$ is a Lebesgue measurable essentially bounded external input
- $\boldsymbol{f}$ is a Lipschitz continuous function w.r.t. the first argument uniformly w.r.t. the second one. 
	- *(This ensures that there exists a unique absolutely continuous solution of the system.)*

**Definition ISS**
System $\Sigma_\circ$ is called **input-to-state stable (ISS)** if there exist function $\gamma \in \mathcal{K}$ and $\beta \in \mathcal{KL}$ so that for all initial values $x_\circ$, all admissible inputs $u$ and all times $t\geq0$ the following inequality holds
$$ ||x(t)|| \leq \beta(||x_\circ||,t) + \gamma(||u||_{\mathcal{L}_\infty}). $$

**Remarks:**
- $\gamma$ is referred to as the "gain".