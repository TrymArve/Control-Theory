**Reference:**
- Gros, S., Zanon, M., Quirynen, R., Bemporad, A. and Diehl, M., 2020. From linear to nonlinear MPC: bridging the gap via the real-time iteration. _International Journal of Control_, _93_(1), pp.62-80.

Notation: [[Optimization#Dynamic Optimization / MPC]]

# Control Problem
Consider the discrete *prediction model* ![[Consider - Discrete NTV#^Discrete-NTV]]and following constraints (actuator limitations, obstacles, etc.):
$$0\leq h(t_{k},x_{k},u_{k})\in \mathbb{R}^{n_{h}}$$

# LMPC Controller
At every time instant; $t_{i}$ , the control input is given by $$u_{i}^{LMPC} = u^{ref,i}_{0} + \Delta u^{i}_{0}$$
where $\Delta u^{i}_{0}$ is found by $$(\Delta x_{i},\Delta u_{i}) = \text{QP}_\text{LMPC}^{i}(\hat{x}_{i},x^{ref,i},u^{ref,i})$$
with $$\begin{align*}
\text{QP}_\text{LMPC}^{i}(\hat{x}_{i},x^{ref,i},u^{ref,i}) & \triangleq
\arg \min_{\Delta x^{i},\Delta u^{i}} \sum\limits_{j=0}^{H_{i}-1}\frac{1}{2} \begin{bmatrix} \Delta x^{i}_{j} \\ \Delta u^{i}_{j}\end{bmatrix}^{\top} W^{i}_{j} \begin{bmatrix} \Delta x^{i}_{j} \\ \Delta u^{i}_{j}\end{bmatrix} \\
\text{subject to:} \\
\Delta x^{i}_{0} & =  \hat{x}_{i} - x^{ref,i}_{0}\\
\Delta x^{i}_{j+1} & = A^{i}_{j} \Delta x^{i}_{j} + B^{i}_{j} \Delta u^{i}_{j} + r^{i}_{j} & \forall j \in \mathbb{Z}_{0,H_{i}-1} \\
0 & \leq C^{i}_{j} \Delta x^{i}_{j} + D^{i}_{j} \Delta u^{i}_{j} + h^{i}_{j} & \forall j \in \mathbb{Z}_{0,H_{i}-1}
\end{align*}$$ ^LMPC-Problem

where 
- $0 \prec W^{i}_{j} = W^{i^{\top}}_{j} \in \mathbb{R}^{n_{x}\times n_{x}}$  is a weight matrix
- $A^{i}_{j},~ B^{i}_{j}~~$ are the linearized *(discrete)* dynamics for time $t_{i+j}$, as computed at time $t_{i}$
	- The dynamics are linearized about the reference trajectory; see [[Basic LMPC - By Gros#Linearization|Linearization]]
	- Note that if the reference, $(x^{ref},u^{ref})$, remains the constant through operation, we have that $$A^{i}_{H} = A^{i+1}_{H-1} = A^{i+2}_{H-2} = \cdots = A^{i+H-1}_{1} = A^{i+H}_{0}$$
	- and similar for $B^{i}_{j}$
- $C^{i}_{j},~~D^{i}_{j}~~$ are the linearized state and input constraints for time $t_{i+j}$, as computed at time $t_{i}$
- $r^{i}_{j}$ is the difference between the next reference state, and the next state predicted by the linearized model
	- That is: $r^{i}_{j} \triangleq A^{i}_{j} \Delta x^{ref,i}_{j} + B^{i}_{j}\Delta u^{ref,i}_{j} - x^{ref,i}_{j}$
- $h^{i}_{j}$ is the constraint-function evaluated at the reference
	- That is: $h^{i}_{j} \triangleq h(t_{i+j},x^{ref,i}_{j},u^{ref,i}_{j})$

**Remark:**
- The reference trajectory at time $t_{i}$, that is; $x^{ref,i}$, does not have to simply be the previous reference; $x^{ref,i-1}$, shifted by one. If the original reference; $x^{ref}$, remains the same, then this is the case. But in many practical cases, one might change the reference from time to time, slightly, to adjust based on new information.
- Note that there is no cost associated with the last state within the horizon; $x^{i}_{H_{i}}$
	- This is not considered here, but it is common to account for the "terminal" state via
		- "Terminal costs"
		- or "Terminal constraints"


## Linearization
The dynamics and constraints are linearized about the reference trajectory as follows:

$$\begin{align*}
A^{i}_{j} = \left. \frac{\partial f_d}{\partial x}\right|_{\left(t_{i+j},~x^{ref,i}_{j},~u^{ref,i}_{j}\right)}~~, & \quad B^{i}_{j} = \left. \frac{\partial f_d}{\partial u}\right|_{\left(t_{i+j},~x^{ref,i}_{j},~u^{ref,i}_{j}\right)}\\
C^{i}_{j} = \left. \frac{\partial h}{\partial x}\right|_{\left(t_{i+j},~x^{ref,i}_{j},~u^{ref,i}_{j}\right)}~~, & \quad D^{i}_{j} = \left. \frac{\partial h}{\partial u}\right|_{\left(t_{i+j},~x^{ref,i}_{j},~u^{ref,i}_{j}\right)}
\end{align*}$$

^LMPC-Linearizations

