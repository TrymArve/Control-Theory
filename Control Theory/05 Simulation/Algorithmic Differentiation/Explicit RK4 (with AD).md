---
tags:
  - Simulation
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By: 
Integration Order: 4
Explicit: true
---
---
# $[x_{k+1},A_{k},B_{k}] \leftarrow \text{xRK4}_{\text{AD}}(x_{k},u_{k},N) \triangleq$

1) $\text{Define:}$
	- $x^{+} = x_{k}$
	- $A_{k} = I$
	- $B_{k}= [0]$
	- $\delta t = \frac{\Delta t_{k}}{N}$
	- $t_{k,n} = t_{k}+n\delta t$
2) $\text{For:} ~~ n\in[0,N-1]$
	1) $\text{Stage 1:}$
		1) $x^{+}_{1} = x^{+}$
		2) $\Delta A_{k}^{0} = [0]$
		3) $\Delta B_{k}^{0} = [0]$
		4) $[f_{1},A_{k}^{1},B_{k}^{1}] \leftarrow \text{Stage}_{k,n}(x^{+}_{1},\Delta A_{k}^{0},\Delta B_{k}^{0})$
	2) $\text{Stage 2:}$
		1) $x^{+}_{2} = x^{+}_{1}+\frac{\delta t}{2} f_{1}$
		2) $\Delta A_{k}^{1} = \frac{\delta t}{2} A_{k}^{1}$
		3) $\Delta B_{k}^{1} = \frac{\delta t}{2} B_{k}^{1}$
		4) $[f_{2},A_{k}^{2},B_{k}^{2}] \leftarrow \text{Stage}_{k,n}(x^{+}_{2},\Delta A_{k}^{1},\Delta B_{k}^{1})$
	3) $\text{Stage 3:}$
		1) $x^{+}_{3} = x^{+}_{2}+\frac{\delta t}{2} f_{2}$
		2) $\Delta A_{k}^{2} = \frac{\delta t}{2} A_{k}^{2}$
		3) $\Delta B_{k}^{2} = \frac{\delta t}{2} B_{k}^{2}$
		4) $[f_{3},A_{k}^{3},B_{k}^{3}] \leftarrow \text{Stage}_{k,n}(x^{+}_{3},\Delta A_{k}^{2},\Delta B_{k}^{2})$
	4) $\text{Stage 4:}$
		1) $x^{+}_{4} = x^{+}_{3}+\delta t f_{3}$
		2) $\Delta A_{k}^{3} = \delta t A_{k}^{3}$
		3) $\Delta B_{k}^{3} = \delta t B_{k}^{3}$
		4) $[f_{4},A_{k}^{4},B_{k}^{4}] \leftarrow \text{Stage}_{k,n}(x^{+}_{4},\Delta A_{k}^{3},\Delta B_{k}^{3})$
	5) $\text{Update:}$
		- $x^{+} \leftarrow x^{+} + \frac{\delta t}{6}(f_{1}+ 2f_{2} + 2f_{3} + f_{4})$
		- $A_{k} \leftarrow A_{k} + \frac{\delta t}{6}(A_{k}^{1} + 2A_{k}^{2} + 2A_{k}^{3} + A_{k}^{4})$
		- $B_{k} \leftarrow B_{k} + \frac{\delta t}{6}(B_{k}^{1} + 2B_{k}^{2} + 2B_{k}^{3} + B_{k}^{4})$
3) $\text{Set:}$
	- $x_{k+1} = x^{+}$
4) $\text{Return:}$
	- $~x_{k+1} ~, ~A_{k} ~, ~B_{k}$
---

---
## $[f_{i},A_{k}^{i},B_{k}^{i}] \leftarrow \text{Stage}_{k,n}(x^{+}_{i},\Delta A_{k}^{i-1},\Delta B_{k}^{i-1})$
1) $f_{i} = f(t_{k,n},x^{+}_{i},u_{k})$
2) $A_{k}^{i} = \left.\frac{\partial f}{\partial x}\right|_{(t_{k,n},x^{+}_{i},u_{k})} (A_{k} + \Delta A_{k}^{i-1})$
3) $B_{k}^{i} = \left.\frac{\partial f}{\partial x}\right|_{(t_{k,n},x^{+}_{i},u_{k})} (B_{k}+\Delta B_{k}^{i-1}) + \left.\frac{\partial f}{\partial u}\right|_{(t_{k,n},x^{+}_{i},u_{k})}$
4) $\text{Return:}~~[f_{i},A_{k}^{i},B_{k}^{i}]$
---


**Remarks:**
- This algorithm is a shooting method for integrating an ODE
- From some state $x_{k}$, this algorithm provides the next state $x_{k+1}$ after some time $\Delta t_{k}$ has passed, given a constant $u_{k}$ control input over the interval.
- The algorithm also return the equivalent linear system that yields the same step.
- That is: $$x_{k+1} = A_{k}x_{k} + B_{k}u_{k}$$
- Thus it also yields the [[Sensitivity|"sensitivities"]]: $$\Delta x_{k+1}= A_{k}\Delta x_{k}+ B_{k}\Delta u_{k}$$
	- That is, how much the next state value changes, based on some changes to the current state and the constant input
- For small changes, we see that, in fact:
	- $\frac{\partial x_{k+1}}{\partial x_{k}} = A_{k}$
	- $\frac{\partial x_{k+1}}{\partial u_{k}} = B_{k}$
	which is useful in optimization based control methods
- **Note** that this is an ***exact*** differentiation of the integration itself!!
	- The integration itself is *not exact*,
	- but for small changes of $x_{k}$, the $x_{k+1}$ that this integration scheme produces will change ***exactly*** according to the sensitivities provided.
- $N$ is the number of integration steps within the shooting interval
	- larger $N$ (smaller $\delta t$) $\implies$ higher integration accuracy
	- Integration Order:$$||f_{d}(x_{k},u_{k}) - f_{xEuler}(x_{k},u_{k})|| = \mathcal{O}(\delta t^{4})$$

