# Basic Optimization Notation
- $\phi(\cdot)$ - objective/cost function
	- not $f$, to distinguish from dynamic constraints
- $z$ - decision/optimization variable
	- not $x$, to distinguish from state variables in dynamic opt.problems
	- $z^*$  -  used to denote a [[Solution]]
	- $z^{**}$  - used to specify a [[Solution#Global Solution|global solution]]
	- $z^{***}$ - used to specify a [[Solution#Unique Solution|unique solution]]
	- $z^{g}$ - used to denote a "guess" during iteration
		- $z^{g_{i}}$ - denotes the $i^{\text{th}}$ guess during iteration
- $\mathcal{L}$ - [[Lagrangian]]
- $\lambda$ - Lagrangian multipliers for equality constraints
	- $\bar{\lambda}$ - to specify equality constraints
	- $\hat{\lambda}$ - to specify inequality constraints
	- Unless otherwise specified, we use $\lambda^{\top} \triangleq [\bar{\lambda}^{\top}, \hat{\lambda}^{\top}]$
- $g(\cdot)$ - equality constraints
- $h(\cdot)$ - inequality constraints ($h(\cdot) \geq 0$)

## LP/QP Specific



# Dynamic Optimization / MPC
Consider the system to be controlled/simulated: ![[Consider - Controlled NTI#^system]]
![[Consider - reference trajectory]]

**where:**
- $T$ is the total time of operation. (i.e. the total duration over which we plan to control/operate the process/system, for which we also have a reference trajectory)
- $\tilde{t} = \{t_{0},t_{1},\dots,t_{N}\}$  is the set of sampling times
- $x$ is the system state
- $u$ is the control input
- $x^{\circ}(t)$ is the true trajectory of the system, as controlled by our controller, and starting at $x_{\circ}$
- $x^{\circ} = \{x^{\circ}_{0},x^{\circ}_{1},\dots,x^{\circ}_{N}\}$ is the true evolution of the system state on $\tilde{t}$
- $u^{\circ} = \{u^{\circ}_{0},u^{\circ}_{1},\dots,u^{\circ}_{N-1}\}$ is the true evolution of the control input on $\tilde{t}$
- $x^{ref}(t)$ is the state reference
- $u^{ref}(t)$ is the input reference
- $x_{i}^{ref}$ is the state reference value at time $t_{i}$
- $u_{i}^{ref}$ is the input reference value at time $t_{i}$
- $N$ is the number of reference trajectory samples. (i.e. the coarseness/resolution of the discretized/transcribed reference trajectory)
	- does not include initial value (thus num. point are $N+1$)
- $x^{ref}$ is the set of state reference values at times $\{t_{0},t_{1},\dots,t_{N}\}$
- $u^{ref}$ is the set of input reference values at times $\{t_{0},t_{1},\dots,t_{N}\}$
- $H$ is the number of steps in the prediction horizon. (not including the initial value, thus num. are $H+1$)
	- use $H_{i}$ for the horizon used at time $t_{i}$
- $x^{ref,i}$ is a state reference horizon, starting at $x^{ref}_{i}$ (i.e. a subset of the discretized reference trajectory, starting at $x^{ref}_{i}$, extending $H$ samples into the future; until $x^{ref}_{i+H}$)
	- we have $x^{ref,i}_{j} = x^{ref}_{i+j}$
	- $x^{ref,i} \triangleq \{x^{ref,i}_{0},x^{ref,i}_{1},\dots,x^{ref,i}_{H}\}$
- $u^{ref,i}$ is a input reference horizon, starting at $u^{ref}_{i}$
	- we have $u^{ref,i}_{j} = u^{ref}_{i+j}$
	- $u^{ref,i} \triangleq \{u^{ref,i}_{0},u^{ref,i}_{1},\dots,u^{ref,i}_{H-1}\}$   (extends only to $H-1$)
- $\hat{x}_{i}$ is the estimate of the system state at time $t_{i}$ (i.e. $\hat{x}_{i} \approx x^{\circ}(t_{i})$)
- $\tilde{x}^{i}_{j}$ is the predicted system state, predicted to occur at time $t_{i+j}$, as predicted at time $t_{i}$ (i.e. at time $t_{i}$, we predict the state $j$ samples into the future)
- $\tilde{x}^{i} \triangleq \{\tilde{x}^{i}_{0},\tilde{x}^{i}_{1},\dots,\tilde{x}^{i}_{H_{i}}\}$
- $\tilde{u}^{i}_{j}$ is the predicted control input, predicted to be imposed at time $t_{i+j}$, as predicted at time $t_{i}$ (i.e. at time $t_{i}$, we predict the input $j$ samples into the future)
- $\tilde{u}^{i} \triangleq \{\tilde{u}^{i}_{0},\tilde{u}^{i}_{1},\dots,\tilde{u}^{i}_{H_{i}-1}\}$
- $\tilde{x} = \{\tilde{x}_{0},\tilde{x}_{1},\dots,\tilde{x}_{N}\}$ is used to refer to the entire predicted state trajectory on $\tilde{t}$, as predicted off-line
- $\tilde{u} = \{\tilde{u}_{0},\tilde{u}_{1},\dots,\tilde{u}_{N-1}\}$ is used to refer to the entire predicted input trajectory on $\tilde{t}$, as predicted off-line
- $\Delta x^{i}_j$ is the difference between the predicted state and reference state
	- that is: $\Delta x^{i}_{j} \triangleq \tilde{x}^{i}_{j} - x^{ref,i}_{j} = \tilde{x}^{i}_{j} - x^{ref}_{i+j}$
- $\Delta u^{i}_j$ is the difference between the predicted input and reference input
	- that is: $\Delta u^{i}_{j} \triangleq \tilde{u}^{i}_{j} - u^{ref,i}_{j}=\tilde{u}^{i}_{j} - u^{ref}_{i+j}$
- $\Delta x^{i} \triangleq \{\Delta x^{i}_{0},\Delta x^{i}_{1},\dots,\Delta x^{i}_{H}\}$
- $\Delta u^{i} \triangleq \{\Delta u^{i}_{0},\Delta u^{i}_{1},\dots,\Delta u^{i}_{H-1}\}$
![[MPC Trajectory Notation.pdf]]

