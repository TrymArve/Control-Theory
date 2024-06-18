---
tags:
  - Simulation
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By: 
Integration Order: 4
Explicit:
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
		4) $[f_{1},A_{k}^{1},B_{k}^{1}] \leftarrow \text{Stage}(x^{+}_{1},\Delta A_{k}^{0},\Delta B_{k}^{0})$
	2) $\text{Stage 2:}$
		1) $x^{+}_{2} = x^{+}_{1}+\frac{\delta t}{2} f_{1}$
		2) $\Delta A_{k}^{1} = \frac{\delta t}{2} A_{k}^{1}$
		3) $\Delta B_{k}^{1} = \frac{\delta t}{2} B_{k}^{1}$
		4) $[f_{2},A_{k}^{2},B_{k}^{2}] \leftarrow \text{Stage}(x^{+}_{2},\Delta A_{k}^{1},\Delta B_{k}^{1})$
	3) $\text{Stage 3:}$
		1) $x^{+}_{3} = x^{+}_{2}+\frac{\delta t}{2} f_{2}$
		2) $\Delta A_{k}^{2} = \frac{\delta t}{2} A_{k}^{2}$
		3) $\Delta B_{k}^{2} = \frac{\delta t}{2} B_{k}^{2}$
		4) $[f_{3},A_{k}^{3},B_{k}^{3}] \leftarrow \text{Stage}(x^{+}_{3},\Delta A_{k}^{2},\Delta B_{k}^{2})$
	4) $\text{Stage 4:}$
		1) $x^{+}_{4} = x^{+}_{3}+\delta t f_{3}$
		2) $\Delta A_{k}^{3} = \delta t A_{k}^{3}$
		3) $\Delta B_{k}^{3} = \delta t B_{k}^{3}$
		4) $[f_{4},A_{k}^{4},B_{k}^{4}] \leftarrow \text{Stage}(x^{+}_{4},\Delta A_{k}^{3},\Delta B_{k}^{3})$
	5) $\text{Update:}$
		- $x^{+} \leftarrow x^{+} + \frac{\delta t}{6}(f_{1}+ 2f_{2} + 2f_{3} + f_{4})$
		- finish this!!! A_k = 
1) $\text{Set:}$
	- $x_{k+1} = x^{+}$
2) $\text{Return:}$
	- $~x_{k+1} ~, ~A_{k} ~, ~B_{k}$
---

---
## $[f_{i},A_{k}^{i},B_{k}^{i}] \leftarrow \text{Stage}(x^{+}_{i},\Delta A_{k}^{i-1},\Delta B_{k}^{i-1})$
1) $f_{i} = f(t_{k,n},x^{+}_{i},u_{k})$
2) $A_{k}^{i} = \left.\frac{\partial f}{\partial x}\right|_{(t_{k,n},x^{+}_{i},u_{k})} (A_{k} + \Delta A_{k}^{i-1})$
3) $B_{k}^{i} \leftarrow \left.\frac{\partial f}{\partial x}\right|_{(t_{k,n},x^{+}_{i},u_{k})} (B_{k}+\Delta B_{k}^{i-1}) + \left.\frac{\partial f}{\partial u}\right|_{(t_{k,n},x^{+}_{i},u_{k})}$
4) $\text{Return:}~~[f_{i},A_{k}^{i},B_{k}^{i}]$
---


#Unfinished 