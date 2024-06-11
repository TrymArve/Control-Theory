In a practical LMPC setting, we wish to reduce the computation time as much as possible to allow faster regulation, with longer prediction horizons and higher resolution discretization.

**Preparing Matrices**
Whenever possible, we want to compute parameters/matrices offline, in advance.
- **Reference:** the reference trajectory can of course be computed offline, with various techniques.
	- often, an open-loop dynamic optimization problem is used to generate optimal reference trajectories.
- **Matrices (prediction model):** the prediction model matrices are linearization of the nonlinear dynamics, evaluated at the reference, which are both known, thus they can also be computed offline.
	- That is, we can find: $\frac{\partial f_{d}(t,x,u)}{\partial x}, \quad \frac{\partial f_{d}(t,x,u)}{\partial u}$
	- and we have chosen a reference $x^{ref}(t), u^{ref}(t)$ and sampling times $t_{k}~\forall k \in \mathbb{Z}_{0,N}$ 
		- alternatively chosen the samples directly: $x^{ref}= \{x^{ref}_{0},x^{ref}_{1},\dots\}$
	- Thus we can compute:$$\left.\frac{\partial f_{d}(t,x,u)}{\partial x}\right|_{(t_{k},x^{ref}_{k}, u^{ref}_{k})}, \quad \left.\frac{\partial f_{d}(t,x,u)}{\partial u}\right|_{(t_{k},x^{ref}_{k}, u^{ref}_{k})}$$ in advance, for all points along the trajectory.
- **Inequality Constraints:** similarly we know the constraint functions, and the reference, where the constraint functions are evaluated, thus we can pre-compute;$$\left.\frac{\partial h(t,x,u)}{\partial x}\right|_{(t_{k},x^{ref}_{k}, u^{ref}_{k})}, \quad \left.\frac{\partial h(t,x,u)}{\partial u}\right|_{(t_{k},x^{ref}_{k}, u^{ref}_{k})}$$ for all points along the trajectory.


Therefore, Linear MPC is very fast, since the only computation needed is only the $\text{QP}_\text{LMPC}$: [[LMPC - By Gros#^LMPC-Problem|QP-LMPC]] at each sample.