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
# $[x_{k+1},A_{k},B_{k}] \leftarrow \text{xRK4}(x_{k},u_{k},N) \triangleq$

1) $\text{Define:}$
	- $x^{+} = x_{k}$
	- $\delta t = \frac{\Delta t_{k}}{N}$
	- $t_{k,n} = t_{k}+n\delta t$
2) $\text{For:} ~~ n\in[0,N-1]$
	1) $\text{Stage 1:}$
		1) $x^{+}_{1} = x^{+}$
		4) $f_{1} = f(t_{k,n},x^{+}_{1},u_{k})$
	2) $\text{Stage 2:}$
		1) $x^{+}_{2} = x^{+}_{1}+\frac{\delta t}{2} f_{1}$
		4) $f_{2} = f(t_{k,n},x^{+}_{2},u_{k})$
	3) $\text{Stage 3:}$
		1) $x^{+}_{3} = x^{+}_{2}+\frac{\delta t}{2} f_{2}$
		2) $f_{3} = f(t_{k,n},x^{+}_{3},u_{k})$
	4) $\text{Stage 4:}$
		1) $x^{+}_{4} = x^{+}_{3}+\delta t f_{3}$
		2) $f_{4} = f(t_{k,n},x^{+}_{4},u_{k})$
	5) $\text{Update:}$
		- $x^{+} \leftarrow x^{+} + \frac{\delta t}{6}(f_{1}+ 2f_{2} + 2f_{3} + f_{4})$
1) $\text{Set:}$
	- $x_{k+1} = x^{+}$
2) $\text{Return:}$
	- $~x_{k+1}$
---


**Remarks:**
- This is only **one** example of an Explicit RK4 scheme, with a particular Butcher Tableau:
	- BT: #Unfinished 
	- Though this is a common version
- This algorithm is a shooting method for integrating an ODE
- From some state $x_{k}$, this algorithm provides the next state $x_{k+1}$ after some time $\Delta t_{k}$ has passed, given a constant $u_{k}$ control input over the interval.
- $N$ is the number of integration steps within the shooting interval
	- larger $N$ (smaller $\delta t$) $\implies$ higher integration accuracy
	- Integration Order:$$||f_{d}(x_{k},u_{k}) - f_{xEuler}(x_{k},u_{k})|| = \mathcal{O}(\delta t^{4})$$

