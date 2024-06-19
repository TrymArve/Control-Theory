---
tags:
  - Definition
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
Consider the solution $$x^{\circ}(t)$$ to the IVP $$\frac{dx^{\circ}(t)}{dt} = f(t,x^{\circ}(t)), \quad x^{\circ}(t_{\circ}) = x_{\circ}$$
The ***sensitivity*** of this solution is how the values along the solution; $x^{\circ}(t)$, changes with a change in the *initial condition*; $x_{\circ}$. That is: $$\text{Sensitivity:} \quad \frac{\partial x^{\circ}(t)}{\partial x_\circ}$$
For controlled systems: ![[Consider - Controlled NTV#^system]]***sensitivity*** can also be with respect to the control inputs.
For continuous control inputs; $u(t)$, this is not as straight forward as for the initial value, but if we use a constant input; $$u(t)\equiv u_{\circ} \forall t \in [t_{\circ},t_\circ+T]$$ then the control sensitivity becomes $$\text{Control Sensitivity:} \quad \frac{\partial x^{\circ}(t)}{\partial u_\circ}$$

**Remarks:**
- Sensitivities of a solution as found by a particular [[Integrator]] can often be computed at the same time as the integration happens.
	- see [[Algorithmic Differentiation]]
- Sensitivities are used in [[Dynamic Optimization]] to adjust the controls / initial values
- Control sensitivities are useful for integrators using small [[Shooting Method|shooting intervals]] with constant control input on the interval.