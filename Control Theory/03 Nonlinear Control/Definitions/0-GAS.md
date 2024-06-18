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
*This ensures that there exists a unique absolutely continuous solution of the system.*

**0-GAS:**
System $\Sigma_\circ$ is called **globally asymptotically stable at zero (0-GAS)** if the corresponding system with zero input
$$ \dot{\boldsymbol{x}} = \boldsymbol{f}(\boldsymbol{x}, \boldsymbol{0}) $$
is globally asymptotically stable.

### Summary
$$\dot{x} = f(x,0)\quad\text{is~~~GAS}\quad \implies \quad \dot{x} = f(x,u)\quad\text{is~~~~0-GAS}$$