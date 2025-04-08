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
\end{bmatrix*}}_{\mathcal{K}(z,\lambda)}
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
		- See [[Interior Point Methods]] and [[SQP Method]], [[Newton-type Methods]]
	- [[Parameter Sensitivities]]


**Derivation:**
Consider:
$$\min_{z\in\mathbb{R}^{n_z}} ~\phi(z)\quad s.t. \quad g(z) = 0$$
where $g(z)$ has consumed the active inequality constraints.
The Lagrangian is:
$$\mathcal{L}(z,\lambda) \triangleq \phi(z) - \lambda^{\top}g(z)$$

The KKT vector is defined as the Lagrangian Jacobian: ![[KKT-Vector#^KKT-vector]]which, when required to be equal to zero, is identical to the [[KKT Conditions (First-Order Necessary Conditions)|KKT conditions]].

The KKT system the linear system of equations you get when you apply [[Newton Method]]/[[Newton-type Methods]] to solve for $\kappa(s) = 0$.

A Newton step is found by solving the following system:
$$\begin{align*}
\nabla_{s}\kappa(s_{k})\Delta s + \kappa(s_{k}) &= 0 \\[0.5em]
\nabla^{2}_{s} \mathcal{L}(s_{k}) \Delta s & =  -\nabla_{s} \mathcal{L}(s_{k})\\[0.5em]
\nabla_{s}\left(\begin{bmatrix}
\nabla_{z} \mathcal{L}(s) \\[0.5em]
 - g(z)
\end{bmatrix}\right)\Bigg|_{s_{k}} \Delta s & = -\begin{bmatrix}
\nabla_{z} \phi(z_{k}) - \nabla_{z}g^{\top}(z_{k})\lambda_{k} \\
 - g(z_{k})
\end{bmatrix}\\
\end{align*}
$$

By writing out the Hessian matrix, we get:
$$\begin{align*}
\nabla_{s}\left(\begin{bmatrix}
\nabla_{z} \mathcal{L}(s) \\[0.5em]
 - g(z)
\end{bmatrix}\right) &= \left(\frac{\partial}{\partial s}
\begin{bmatrix}
\nabla_{z} \mathcal{L}(s) \\[0.5em]
 - g(z)
\end{bmatrix}\right)^{\top} \\
&= 
\begin{bmatrix}
\nabla^{2}_{z} \mathcal{L}(s)  &  \nabla_{\lambda}(\nabla_{z} \mathcal{L}(s))  \\
-\nabla_{z} g(z)  &  \nabla_{\lambda}g(z)
\end{bmatrix}^{\top} \\[0.5em]
&= \begin{bmatrix}\nabla^{2}_{z} \mathcal{L}(s)  &  -\nabla_{z} g(z)  \\
\nabla_{\lambda}(\nabla_{z} \mathcal{L}(s))  &  \nabla_{\lambda}g(z)
 \end{bmatrix}\\[0.5em]
&= \begin{bmatrix}\nabla^{2}_{z} \mathcal{L}(s)  &  -\nabla_{z} g(z)  \\
-\nabla_{z} g(s)  &  0
 \end{bmatrix}
\end{align*}$$
thus the linear system can be written:

$$\begin{align*}
\begin{bmatrix}
\nabla^{2}_{z} \mathcal{L}(s_{k})&  -\nabla_{z} g(z_{k}) \\
 - \nabla_{z} g(z_{k}) & 0
\end{bmatrix} \begin{bmatrix} \Delta z \\ \Delta \lambda \end{bmatrix} & = \begin{bmatrix}
-\nabla_{z} \phi(z_{k}) + \nabla_{z}g^{\top}(z_{k})\lambda_{k} \\
g(z_{k})
\end{bmatrix}\\[0.5em]
\end{align*}$$
We can further simplify the top equation in the following way:
$$\begin{align*}
\nabla^{2}_{z} \mathcal{L}(s_{k}) \Delta z  -\nabla_{z} g(z_{k})& \Delta \lambda & & = -\nabla_{z} \phi(z_{k}) + \nabla_{z}g^{\top}(z_{k})\lambda_{k} \\
\nabla^{2}_{z} \mathcal{L}(s_{k}) \Delta z  -\nabla_{z} g(z_{k})& \Delta \lambda - \nabla_{z}g^{\top}(z_{k})\lambda_{k} & &= -\nabla_{z} \phi(z_{k}) \\
\nabla^{2}_{z} \mathcal{L}(s_{k}) \Delta z  -\nabla_{z} g(z_{k}) &(\Delta \lambda + \lambda_{k}) & &= -\nabla_{z} \phi(z_{k}) \\
\nabla^{2}_{z} \mathcal{L}(s_{k}) \Delta z  -\nabla_{z} g(z_{k}) & \lambda_{k+1} & &= -\nabla_{z} \phi(z_{k}) 
\end{align*}$$

and thus rewrite the linear system to be:
$$\underbrace{\begin{bmatrix}
\nabla^{2}_{z} \mathcal{L}(s_{k})&  -\nabla_{z} g(z_{k}) \\
 - \nabla_{z} g(z_{k}) & 0
\end{bmatrix}}_{\mathcal{K}(s_{k})} \begin{bmatrix} \Delta z \\ \lambda_{k+1} \end{bmatrix} = \underbrace{\begin{bmatrix}
-\nabla_{z} \phi(z_{k}) \\
g(z_{k})
\end{bmatrix}}_{\kappa(s_{k})}$$
which we call the KKT system.