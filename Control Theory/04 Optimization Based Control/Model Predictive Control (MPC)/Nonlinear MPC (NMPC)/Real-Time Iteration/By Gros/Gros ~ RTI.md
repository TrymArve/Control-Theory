---
tags:
  - Optimization/NMPC/RTI
Note Author:
  - Trym A. Gabrielsen
Theory Author:
  - Sébastien Gros
  - Moritz Diehl
Reviewed By:
---

---
# $\text{RTI}^{i}(\tilde{x}^{i-1*},\tilde{u}^{i-1*},x^{ref,i},u^{ref,i};~\hat{x}_{i}) \triangleq$
## $\text{Preparation Phase:}~[t_{i-1},t_{i}\rangle$
- **input:** $(\tilde{x}^{i-1*},\tilde{u}^{i-1*},x^{ref,i},u^{ref,i})$
1) $\text{Shift Previous Solution:}$  *(see [[Shifting Procedure]])*
	- $\tilde{x}^{i,g_{0}} = \{\tilde{x}^{i-1*}_{1,\dots,H_{i}}~,~~\tilde{x}^{i}_{>H_{i-1}}\}$
	- $\tilde{u}^{i,g_{0}} = \{\tilde{u}^{i-1*}_{1,\dots,H_{i}-1}~,~~\tilde{u}^{i}_{>H_{i-1}-1}\}$
2) $\text{Evaluate at}~(x^{i,g_{0}},u^{i,g_{0}}):$ *([[Gros ~~ QP-NMPC Linearizations|linearize]], [[Gros ~~ QP-NMPC Correction Terms|correction]])*
	- $r^{i}_{j},\quad h^{i}_{j}$
	- $A^{i}_{j},\quad B^{i}_{j}$
	- $C^{i}_{j},\quad D^{i}_{j}$
	- $J^{i}_{j},\quad H^{i}_{j}$
1) $\text{Construct:}$
	- $\text{QP}^{i}_{\text{NMPC}}\quad$ *(see [[Gros ~~ QP-NMPC Formulation|QP-NMPC]])*
	- *(prepare all possible computations that don't require $\hat{x}_{i}$)*
		- *condensing*
		- *matrix factorizations*
		- *etc.*
## $\text{Feedback Phase:}~ [t_{i}]$
- **input:** $(\hat{x}_{i})$
4) $\text{Finish Constructing:}$
	- $\text{QP}^{i}_{\text{NMPC}}$
5) $\text{Solve:}$
	- $(\Delta x^{i}, \Delta u^{i})_{0} = \text{QP}^{i}_{\text{NMPC}}(\hat{x}_{i},\tilde{x}^{i,g_{0}},\tilde{u}^{i,g_{0}},x^{ref,i},u^{ref,i})$
6) $\text{Update Guess:}$
	- $(\tilde{x}^{i,g_{1}},\tilde{u}^{i,g_{1}}) = (\tilde{x}^{i,g_{0}},\tilde{u}^{i,g_{0}}) + \alpha(\Delta x^{i}, \Delta u^{i})$
7) $\text{Return:} ~~ (\tilde{x}^{i,g_{1}},\tilde{u}^{i,g_{1}})$

---
**Inputs:**
- $(\tilde{x}^{i-1*},\tilde{u}^{i-1*})$ - the previous NMPC-NLP solution (or estimate thereof)
- $(x^{ref,i},u^{ref,i})$ - reference trajectory on current horizon
- $\hat{x}_{i}$ - current state estimate, provided in the middle of the algorithm, to ensure the most up to date estimate possible.


**Remarks:**
- The delay introduced by feedback *(from receiving new estimate to the respective control is applied)* can be accommodated by introducing a corresponding prediction of the state estimate.
- the sampling time $\Delta t_{i} = t_{i+1}-t_{i}$ is limited by the sum of the time spent in the 'preparation' and 'feedback' phases.
- The time spend in the 'feedback' phase is practically the same as the time it takes to solve the [[Gros ~ LMPC|LMPC]] problem
- The preparation of step 5) that does not require knowledge of the initial state (the parameter), can be moved to the 'preparation' phase:
	- f.ex. the "[[Condensing]]" of the problem can be done prior to knowing the state
- The increase in sampling time, $\Delta t$, required to perform the RTI scheme, from that of [[Gros ~ LMPC|Linear MPC]], is only determined by the preparation phase
- It is desirable to minimize the 'feedback time'
	- that is, move as much as possible from the feedback phase to the preparation phase
	- Because the preparation phase can often fit in the time after the previous feedback phase and before the next state estimate is available, RTI-NMPC can in many cases be applied at the same sampling frequency as that of Linear MPC based on a model that is pre-linearized off-line.