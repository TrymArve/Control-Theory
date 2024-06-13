%% #Optimization/LMPC %%
%% **Reference:** Gros, S., Zanon, M., Quirynen, R., Bemporad, A. and Diehl, M., 2020. From linear to nonlinear MPC: bridging the gap via the real-time iteration. _International Journal of Control_, _93_(1), pp.62-80. %%
Notation: [[Optimization#Dynamic Optimization / MPC|here]]
OCP: ![[Optimal Control Problem#^OCP]]



# LMPC Controller:
At every time instant; $t_{i}$ , the control input is given by $$u_{i}^{LMPC} = u^{ref,i}_{0} + \Delta u^{i}_{0}$$
where $\Delta u^{i}_{0}$ is found by $$(\Delta x_{i},\Delta u_{i}) = \text{QP}_\text{LMPC}^{i}(\hat{x}_{i},x^{ref,i},u^{ref,i})$$with ![[QP-LMPC Formulation#^QP]]

## where 
- $0 \prec W^{i}_{j} = W^{i^{\top}}_{j} \in \mathbb{R}^{n_{x}\times n_{x}}$  is a weight matrix
- $A^{i}_{j},~ B^{i}_{j}~~$ are the linearized *(discrete)* dynamics for time $t_{i+j}$, as computed at time $t_{i}$
	- The dynamics are linearized about the reference trajectory; see [[Gros ~ LMPC#Linearization|Linearization]]
	- Note that if the reference, $(x^{ref},u^{ref})$, remains the constant through operation, we have that $$A^{i}_{H} = A^{i+1}_{H-1} = A^{i+2}_{H-2} = \cdots = A^{i+H-1}_{1} = A^{i+H}_{0}$$
	- and similar for $B^{i}_{j}$
- $C^{i}_{j},~~D^{i}_{j}~~$ are the linearized state and input constraints for time $t_{i+j}$, as computed at time $t_{i}$
- $r^{i}_{j}$ is the difference between the next reference state, and the next state predicted by the linearized model
	- That is: $r^{i}_{j} \triangleq A^{i}_{j} x^{ref,i}_{j} + B^{i}_{j}u^{ref,i}_{j} - x^{ref,i}_{j+1}$
- $h^{i}_{j}$ is the constraint-function evaluated at the reference
	- That is: $h^{i}_{j} \triangleq h(t_{i+j},x^{ref,i}_{j},u^{ref,i}_{j})$


**Linearization**
The dynamics and constraints are linearized about the reference trajectory as follows: ![[QP-LMPC Linearizations#^Linearizations]]

**Remark:**
- The reference trajectory at time $t_{i}$, that is; $x^{ref,i}$, does not have to simply be the previous reference; $x^{ref,i-1}$, shifted by one. If the original reference; $x^{ref}$, remains the same, then this is the case. But in many practical cases, one might change the reference from time to time, slightly, to adjust based on new information.
- Note that there is no cost associated with the last state within the horizon; $x^{i}_{H_{i}}$
	- This is not considered here, but it is common to account for the "terminal" state via
		- "Terminal costs"
		- or "Terminal constraints"