Discussion on LMPC, as a continuation of [[Gros ~ LMPC]].

# Discussion

## Prediction model, and correction term
- We can use Linear MPC when we have a **LINEAR SYSTEM 
	- In this case we notice that the linearization is equal to the original model:$$f_{d}(t_{k},x_{k},u_{k}) = A_{k}x_{k}+ B_{k}u_{k}$$
	- It is important to note that the linear prediction model, provides the deviation between the next predicted state, and the next reference state ***as computed by the model***.
		- That is, we want: $\Delta x_{k+1} = \tilde{x}_{k+1} - x^{ref}_{k+1} = A_{k}\tilde{x}_{k}+B_{k}\tilde{u}_{k} - x^{ref}_{k+1}$
		- but, we assume $x^{ref}_{k+1} = A_{k}x^{ref}_{k} + B_{k}u^{ref}_{k}$
		- to get: $\Delta x_{k+1} = A_{k}\tilde{x}_{k}+B_{k}\tilde{u}_{k} - A_{k}x^{ref}_{k} - B_{k}u^{ref}_{k} = A_{k}\Delta x_{k}+ B_{k}\Delta u_{k}$
	- If the reference trajectory is not feasible with respect to the linear prediction model, that is $x^{ref}_{k+1} \centernot= A_{k}x^{ref}_{k} + B_{k}u^{ref}_{k}$, then we must account for the error, $r_k$, defined such that $$x^{ref}_{k+1} = A_{k}x^{ref}_{k} + B_{k}u^{ref}_{k} - r_k$$
		- We then get the 'deviation form reference' prediction model: $$\Delta x_{k+1} = A_{k}\tilde{x}_{k}+B_{k}\tilde{u}_{k} - A_{k}x^{ref}_{k} - B_{k}u^{ref}_{k} + r_{k} = A_{k}\Delta x_{k}+ B_{k}\Delta u_{k} + r_{k}$$
	- This is illustrated in [[Reference Trajectory - Model Offset.pdf]] *(also seen below)*

- We can also use LMPC to control a **NONLINEAR SYSTEM**
	- In this case we even if we compute a reference that is feasible with respect to the nonlinear model of the system, it is not feasible with respect to the linearized prediction model. Therefore, again have: $$x^{ref}_{k+1} \centernot= A_{k}x^{ref}_{k} + B_{k}u^{ref}_{k}$$ and need to correct the model with a correction term: $$\begin{align*}
x^{ref}_{k+1} = f_{d}(t_{k},x_{k},u_{k}) ~& \centernot= A_{k}x^{ref}_{k} + B_{k}u^{ref}_{k} \\[0.2cm]
x^{ref}_{k+1} =f_{d}(t_{k},x_{k},u_{k}) &= A_{k}x^{ref}_{k} + B_{k}u^{ref}_{k} - r_k
\end{align*}$$
	- We end up with the same LMPC formulation as when controlling a linear system, with infeasible reference trajectory

- In either case, the correction term is computed using the difference between the next reference state and the next reference as predicted by the linearized model:
	- $r^{k} \triangleq A^{k} x^{ref}_{k} + B^{k} u^{ref}_{k} - x^{ref}_{k+1}$

- Below is an illustration of the deviation model and the correction term:
![[Reference Trajectory - Model Offset.pdf]]



## Inequality Constraints
- We also have linear constraints on the form: $$C_{k}\Delta x_{k} + D_{k}\Delta u_{k} + h_{k} \geq 0$$
- These are linearizations of the original nonlinear constraint (the original constraints may also be linear): $$h(t,x,u) \geq 0 $$
- But, on deviation form:$$\begin{align*}
h_{\Delta}(t,\tilde{x}_{k}-x^{ref}_{k},\tilde{u}_{k}-u^{ref}_{k}) & \geq 0\\
=h_{\Delta}(t,\Delta x_{k},\Delta u_{k}) & \geq 0
\end{align*}$$
- This is linearized about $(t,\Delta x,\Delta u) = (t_k,0,0)$ using standard linear [[Taylor Series Approximation]]:$$h_{\Delta}(t_{k},\Delta x_{k},\Delta u_{k}) \approx \left.\frac{\partial h_{\Delta}}{\partial x}\right|_{(t_{k},0,0)}\Delta x_{k}+ \left.\frac{\partial h_{\Delta}}{\partial u}\right|_{(t_{k},0,0)}\Delta u_{k}+ h_{\Delta}(t_{k},0,0)$$
	- Notice that $(t,\Delta x,\Delta u) = (t_{k},0,0)\implies (t,x,u) = (t_{k},x^{ref}_{k},u^{ref}_{k})$
	  thus we have: $$h(t_{k},x^{ref}_{k},u^{ref}_{k}) \approx \underbrace{  \left.\frac{\partial h}{\partial x}\right|_{(t_{k},x^{ref}_{k},u^{ref}_{k})}  }_{C_{k}} \Delta x_{k}+ \underbrace{\left.\frac{\partial h}{\partial u}\right|_{(t_{k},x^{ref}_{k},u^{ref}_{k})}}_{D_{k}}\Delta u_{k}+ \underbrace{h(t_{k},x^{ref}_{k},u^{ref}_{k})}_{h_k}$$
	  - Close to the reference; $(\Delta x,\Delta u) \approx (0,0)$, we have that the linear approximation is a decent approximation, given that the constraints are sufficiently smooth.

