---
tags:
  - Definition
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
The shooting method is a method of solving the [[Boundary Value Problem (BVP)]].
The method reduces the BVP to an [[Initial Value Problem (IVP)|IVP]];
1) Guess an initial value
2) Solve the corresponding IVP
3) Check if the remaining boundary conditions are satisfied
4) If the BVP is not solved:
	1) Adjust the initial condition
	2) Repeat from 2)

There are methods for adjusting the initial value based on information about the solution to that was found, such as using sensitivities of the solution;$$\frac{\partial y^{\circ}(t)}{\partial y_{\circ}}$$
# Example
Consider the BVP $$\frac{dy}{dt} = f(t,y) \in\mathbb{R}^{2}, \quad y_{1}(t_{\circ}) = y_{1,\circ}, \quad y_{2}(t_{\circ\circ}) = y_{2,\circ\circ}$$
We start by guessing 
- $y(t_\circ) = [y_{1,\circ},~y_{2,\circ}]^{\top}$ 
and solve the IVP $$\frac{dy}{dt} = f(t,y) , \quad y(t_\circ) = [y_{1,\circ},~y_{2,\circ}]^{\top}$$
to obtain a value $\hat{y} = y(t_{\circ\circ})$. We then check if 
- $\hat{y}_{2}= y_{2,\circ\circ}$
If this boundary condition is not satisfied, we can use the [[Sensitivity|sensitivity]] of the solution at $t_{\circ\circ}$: $$\frac{\partial y^{\circ}(t_{\circ\circ})}{\partial y_{\circ}}$$ to adjust the initial value. For example as: $$\begin{align*}
\left(y^{\circ}(t_{\circ\circ})-\begin{bmatrix}0\\ y_{2,\circ\circ}\end{bmatrix}\right) &= \frac{\partial y^{\circ}(t_{\circ\circ})}{\partial y_{\circ}}\Delta y_{\circ}\\
y_{\circ} & \leftarrow y_{\circ} + \Delta y_{\circ}
\end{align*}$$
