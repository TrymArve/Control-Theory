---
tags: []
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By: 
Relevant Papers:
---
**Definition:**
The *KKT system* is the following linear system of equations obtained when linearizing the [[KKT Conditions (First-Order Necessary Conditions)|KKT conditions]]:
$$\underbrace{\begin{bmatrix*}
\nabla_{z}^{2}\mathcal{L}(z,\lambda) & -\nabla_{z}g(z) & -\nabla_{z}h_{\mathbb{A}}(z) \\
-\nabla_{z}g^{\top}(z) &  0 & 0\\
-\nabla_{z}h_{\mathbb{A}}^{\top}(z) & 0 & 0
\end{bmatrix*}}_{K(z,\lambda)}
\cdot 
\begin{bmatrix} \Delta z \\ \bar\lambda^{+}  \\ \hat\lambda^{+} \end{bmatrix}
=
\begin{bmatrix} -\nabla_{z}\phi(z)  \\  g(z)  \\  h_{\mathbb{A}}(z)\end{bmatrix}
$$
**Remarks:**
- $z^{+} = z + \Delta z,\quad \lambda^{+} = \lambda + \Delta \lambda$
- The KKT system assumes an equality constrained problem, and any inequality constraints $h_{i}(z)$ that are assumed to be active are included. Otherwise, we typically only see the equality constraints $g(z)$ present.
- Alternatively, one can view it as adding the assumed active inequalities into the equality vector.
- This system appears often:
	- [[Solving EQP]]
	- [[Newton Method]] for solving an [[NLP formulation|NLP]] (solving the KKT condition...)
		- See [[Interior Point Methods]] and [[General SQP Method]]
	- [[Parameter Sensitivities]]


**Derivation:**
Consider:
$$\min_{z\in\mathbb{R}^{n_z}} ~\phi(z)\quad s.t. \quad g(z) = 0$$
The Lagrangian is:
$$\mathcal{L}(z,\lambda) \triangleq \phi(z) - \lambda^{\top}g(z)$$
If we define the function
$$\mathcal{K}(z,\lambda) \triangleq \begin{bmatrix} \nabla_{z}\mathcal{L}(z,\lambda)  \\  g(z) \end{bmatrix}$$
then the KKT conditions are
$$\mathcal{K}(z^{*},\lambda^{*}) = 0$$


The first order Taylor approximation of the KKT conditions about point $(z^{\circ},\lambda^{\circ})$ are
$$\mathcal{K}(z,\lambda)\approx \underbrace{\left[ \left.\frac{\partial \mathcal{K}}{\partial z}\right|_{(z^{\circ},\lambda^{\circ})}  \quad \left.\frac{\partial \mathcal{K}}{\partial \lambda}\right|_{(z^{\circ},\lambda^{\circ})}  \right]}_{\text{KKT matrix (almost...)}}
\begin{bmatrix}z - z^{\circ}  \\  \lambda - \lambda^{\circ} \end{bmatrix}
+ \mathcal{K}(z^{\circ},\lambda^{\circ})$$
We have
$$
\begin{align*}
\frac{\partial \mathcal{K}}{\partial z} &= \begin{bmatrix}\nabla_{z}^{2}\mathcal{L}(z,\lambda)  \\  \nabla_{z}g^{\top}(z)\end{bmatrix}\\
\frac{\partial \mathcal{K}}{\partial \lambda} &= \begin{bmatrix}\nabla_{z,\lambda}\mathcal{L}(z,\lambda)  \\  \nabla_{\lambda}g(z)\end{bmatrix} = \begin{bmatrix}\cancel{\nabla_{z,\lambda} \phi(z)} - \nabla_{z,\lambda}(\lambda^{\top}g(z)) \\  \cancel{\nabla_{\lambda}g(z)} \end{bmatrix} = \begin{bmatrix} - \nabla_{z}g(z) \\  0 \end{bmatrix}
\end{align*}
$$
and
$$\mathcal{K}(z^{\circ},\lambda^{\circ}) = \begin{bmatrix} \nabla_{z}\mathcal{L}(z^{\circ},\lambda^{\circ})  \\  g(z^{\circ}) \end{bmatrix}
= \begin{bmatrix} \nabla_{z}\phi(z^{\circ}) -  \nabla_{z}(\lambda^{\circ\top}g(z^{\circ}))  \\  g(z^{\circ}) \end{bmatrix}
$$
Thus the Taylor approximation can be written as
$$\mathcal{K}(z,\lambda)\approx\begin{bmatrix}\nabla_{z}^{2}\mathcal{L}(z^{\circ},\lambda^{\circ}) & -\nabla_{z}g(z^{\circ})  \\  \nabla_{z}g^{\top}(z^{\circ}) & 0 \end{bmatrix}
\cdot \begin{bmatrix}z - z^{\circ}  \\  \lambda - \lambda^{\circ} \end{bmatrix}
+ \begin{bmatrix} \nabla_{z}\phi(z^{\circ}) -  \nabla_{z}g(z^{\circ})\lambda^{\circ}  \\  g(z^{\circ}) \end{bmatrix}$$
We can rewrite the top equation as
$$\begin{align*}
\nabla_{z}^{2}\mathcal{L}(z^{\circ},\lambda^{\circ})(z-z^{\circ}) & -\nabla_{z}g(z^{\circ})(\lambda - \lambda^{\circ}) &&+ \nabla_{z}\phi(z^{\circ}) - \nabla_{z}g(z^{\circ})\lambda^{\circ}\\
\nabla_{z}^{2}\mathcal{L}(z^{\circ},\lambda^{\circ})(z-z^{\circ})  &-\nabla_{z}g(z^{\circ})(\lambda - \lambda^{\circ}) - \nabla_{z}g(z^{\circ})\lambda^{\circ} &&+ \nabla_{z}\phi(z^{\circ})\\
\nabla_{z}^{2}\mathcal{L}(z^{\circ},\lambda^{\circ})(z-z^{\circ})  &-\nabla_{z}g(z^{\circ})(\lambda - \lambda^{\circ} + \lambda^{\circ}) &&+ \nabla_{z}\phi(z^{\circ})\\
\nabla_{z}^{2}\mathcal{L}(z^{\circ},\lambda^{\circ})(z-z^{\circ})  &-\nabla_{z}g(z^{\circ})\lambda &&+ \nabla_{z}\phi(z^{\circ})
\end{align*}$$
We therefore see that we can rewrite the Taylor approximation as 
$$\mathcal{K}(z,\lambda)\approx\begin{bmatrix}\nabla_{z}^{2}\mathcal{L}(z^{\circ},\lambda^{\circ}) & -\nabla_{z}g(z^{\circ}) \\  \nabla_{z}g^{\top}(z^{\circ}) & 0 \end{bmatrix}
\cdot \begin{bmatrix}z - z^{\circ}  \\  \lambda \end{bmatrix}
+ \begin{bmatrix} \nabla_{z}\phi(z^{\circ}) \\  g(z^{\circ}) \end{bmatrix}$$
Now, using this approximation, we can write the KKT conditions as:
$$\begin{gather*}
\mathcal{K}(z,\lambda) = 0\\
\begin{bmatrix}\nabla_{z}^{2}\mathcal{L}(z^{\circ},\lambda^{\circ}) & -\nabla_{z}g(z^{\circ}) \\  \nabla_{z}g^{\top}(z^{\circ}) & 0 \end{bmatrix}
\cdot \begin{bmatrix}z - z^{\circ}  \\  \lambda \end{bmatrix}
+ \begin{bmatrix} \nabla_{z}\phi(z^{\circ}) \\  g(z^{\circ}) \end{bmatrix} = 0\\
\begin{bmatrix}\nabla_{z}^{2}\mathcal{L}(z^{\circ},\lambda^{\circ}) & -\nabla_{z}g(z^{\circ}) \\  \nabla_{z}g^{\top}(z^{\circ}) & 0 \end{bmatrix}
\cdot \begin{bmatrix}z - z^{\circ}  \\  \lambda \end{bmatrix}
= -\begin{bmatrix} \nabla_{z}\phi(z^{\circ}) \\  g(z^{\circ}) \end{bmatrix}
\end{gather*}$$
In order to make the matrix nice and symmetric, we again rewrite:
$$\begin{bmatrix}\nabla_{z}^{2}\mathcal{L}(z^{\circ},\lambda^{\circ}) & -\nabla_{z}g(z^{\circ}) \\  -\nabla_{z}g^{\top}(z^{\circ}) & 0 \end{bmatrix}
\cdot \begin{bmatrix}\Delta z  \\  \lambda \end{bmatrix}
= \begin{bmatrix} -\nabla_{z}\phi(z^{\circ}) \\  g(z^{\circ}) \end{bmatrix}$$
We also used $\Delta z \triangleq z - z^{\circ}$. This is the KKT system.