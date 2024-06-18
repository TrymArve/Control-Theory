---
tags:
  - NonlinearSystems/Theorem
Note Author:
  - Trym A. Gabrielsen
Theory Author:
  - Antonio Loría
Reviewed By:
---
Consider: ![[Consider - Controlled NTI#^system]]
If $\Sigma_\circ$
- is passive on the map $u \mapsto y$
	- with *energy/storage* function $x\mapsto V(x)$
- is [[Zero-State Detectability|zero-state detectable]]
then
- the controller $u = -k_d(y)$
where
- $k_d(y)$ is [[Definiteness#Half-Definiteness (Trym's definition)|half-definite]]
asymptotically stabilizes the origin; $x=0$.


**Intuition**
- We notice that since the system is passive, we have
	- $\dot{V}(x(t)) \leq u(t)^\top y(t)$ 
	- (storage: $V(x(t)) \leq V(x(t_\circ)) + \big|\int_{t_\circ}^t u(\tau)^\top y(\tau) ~d\tau\big|$)
- with the given controller
	- $\dot{V}(x(t)) \leq -k_d(y(t))^\top y(t) < 0$ 
- [[Barbalat's Lemma]] gives us: $y\rightarrow0$
- And zero-state detectability then gives $x\rightarrow0$


**Reference:** 
*C. Byrnes, A. Isidori, and J. C. Willems. Passivity, feedback equivalence, and the*
*global stabilization of minimum phase nonlinear systems. IEEE Trans. on Automatic*
*Control, AC-36(11):1228{1240, 1991.*