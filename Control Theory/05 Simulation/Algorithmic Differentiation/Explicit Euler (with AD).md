---
tags:
  - Algorithm
  - Simulation
  - Algorithmic-Differentiation
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By: 
Integration Order: 1
Explicit: true
---
---
# $[x_{k+1},A_{k},B_{k}] \leftarrow \text{xEuler}_{\text{AD}}(x_{k},u_{k},N) \triangleq$

1) $\text{Define:}$
	- $x^{+} = x_{k}$
	- $A_{k} = I$
	- $B_{k}= [0]$
	- $\delta t = \frac{\Delta t_{k}}{N}$
	- $t_{k,n} = t_{k}+n\delta t$
2) $\text{For:} ~~ n\in[0,N-1]$
	1) $x^{+} \leftarrow x^{+}+ \delta t f(t_{k,n},x^{+},u_{k})$
	2) $A_{k} \leftarrow \left(I+\delta t \left.\frac{\partial f}{\partial x}\right|_{(t_{k,n},x^{+},u_{k})}\right) A_{k}$
	3) $B_{k} \leftarrow \left(I+\delta t \left.\frac{\partial f}{\partial x}\right|_{(t_{k,n},x^{+},u_{k})}\right) B_{k} + \delta t \left.\frac{\partial f}{\partial u}\right|_{(t_{k,n},x^{+},u_{k})}$
3) $\text{Set:}$
	- $x_{k+1} = x^{+}$
4) $\text{Return:}$
	- $~x_{k+1} ~, ~A_{k} ~, ~B_{k}$
---



**Remarks:**
- This algorithm is a shooting method for integrating an ODE
- From some state $x_{k}$, this algorithm provides the next state $x_{k+1}$ after some time $\Delta t_{k}$ has passed, given a constant $u_{k}$ control input over the interval.
- The algorithm also return the equivalent linear system that yields the same step.
- That is: $$x_{k+1} = A_{k}x_{k} + B_{k}u_{k}$$
- Thus it also yields the "sensitivities": $$\Delta x_{k+1}= A_{k}\Delta x_{k}+ B_{k}\Delta u_{k}$$
	- That is, how much the next state value changes, based on some changes to the current state and the constant input
- For small changes, we see that, in fact:
	- $\frac{\partial x_{k+1}}{\partial x_{k}} = A_{k}$
	- $\frac{\partial x_{k+1}}{\partial u_{k}} = B_{k}$
	which is useful in optimization based control methods
- **Note** that this is an ***exact*** differentiation of the integration itself!!
	- The integration itself is *not exact*,
	- but for small changes of $x_{k}$, the $x_{k+1}$ that this integration scheme produces will change ***exactly*** according to the sensitivities provided.
- $N$ is the number of integration steps within the shooting interval
	- larger $N$ $\implies$ higher integration accuracy
	- Integration Order:$$||f_{d}(x_{k},u_{k}) - f_{xEuler}(x_{k},u_{k})|| = \mathcal{O}(\delta t)$$

