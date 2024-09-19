---
tags: 
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
The boundary value problem consists of finding solutions $$y:\mathbb{R}^{n_{x}}\mapsto \mathbb{R}^{n_{y}}$$of a differential equation; $$f\left(y(x),\frac{\partial y(x)}{\partial x},x\right) \equiv 0$$ subject to constraints/*"boundary conditions"*.
There are different types of possible constraints:
- **Dirichlet Constraints:**$$\begin{align*}
y(x_{\circ}) &= y_{\circ}\\
y(x_{\circ\circ}) &= y_{\circ\circ}\\
y(x_{\circ\circ\circ}) &= y_{\circ\circ\circ}\\
&\vdots
\end{align*}$$
- **Neumann Constraints:** $$\begin{align*}
\frac{\partial y(x_{\circ})}{\partial x} &= Y_{\circ}\\
\frac{\partial y(x_{\circ\circ})}{\partial x} &= Y_{\circ\circ}\\
\frac{\partial y(x_{\circ\circ\circ})}{\partial x} &= Y_{\circ\circ\circ}\\
&\vdots
\end{align*}$$
- **Robin Constraints:** $$\begin{align*}
C_{1}y(x_{\circ}) + C_{2}\frac{\partial y(x_{\circ})}{\partial x} &= Y_{\circ}\\
C_{3}y(x_{\circ}) + C_{4}\frac{\partial y(x_{\circ\circ})}{\partial x} &= Y_{\circ\circ}\\
C_{5}y(x_{\circ}) + C_{6}\frac{\partial y(x_{\circ\circ\circ})}{\partial x} &= Y_{\circ\circ\circ}\\
&\vdots
\end{align*}$$
- **Mixed:** *Dirichlet + Robin* 
- **Cauchy:** *Dirichlet + Neumann*


