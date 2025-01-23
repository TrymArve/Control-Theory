---
tags:
  - Unfinished
  - Theorem
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
Consider the moving horizon problem
![[Basic NMPC-NLP#^NLP]]

If:
- the following assumptions hold:
	- [[Assumption - Nominal Stability of iNMPC]]
	- [[Assumption - Instantaneous feedback of iNMPC]]

Then:
- $J$ is a [[Control Lyapunov Function|Lyapunov function]] for the controlled system
- the closed loop system under the [[ideal NMPC]] controller
$$x_{k+1} = f_{d}(x_{k},u_{\text{iNMPC}}(x_{k}))$$
	is [[Lyapunov Stability|asymptotically stable]]

