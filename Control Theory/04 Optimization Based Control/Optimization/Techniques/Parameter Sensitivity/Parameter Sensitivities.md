---
tags: []
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By: 
Relevant Papers:
---
Consider the KKT conditions:
![[KKT Conditions (First-Order Necessary Conditions)#^KKT-conditions]]
**Assumption:**
- There are no weakly active constraints at point $(z^{*},\lambda^{*})$


 If only regarding the **strictly active** set $\mathbb{A}$, the KKT conditions define an implicit function 
$$R(z^{*},\lambda^{*},p) \triangleq \begin{bmatrix}\nabla_{z}\mathcal{L}(z^{*},\lambda^{*})\\
-g(z^{*})\\
-h_{\mathbb{A}}(z^{*})\end{bmatrix} \equiv 0$$
*(We negate(negative) the constraint function to make a neat correspondence to the KKT matrix)*
Thus, by the [[Implicit Function Theorem]], the map 
$$p \mapsto (z^{*},\lambda^{*})$$ exists and is differentiable. We can therefore find the [[Derivative of Implicit Function|derivative of the implicit function]], as:
$$\begin{align*}
\frac{dz^{*}}{dp}\Bigg|_{p_{0}} &= -\frac{\partial R}{\partial z}\Bigg|_{(z^{*},\lambda^{*},p)}^{-1}\cdot\frac{\partial R}{\partial p}\Bigg|_{(z^{*},\lambda^{*},p)}\\[0.5em]
\frac{d\lambda^{*}}{dp}\Bigg|_{p_{0}} &= -\frac{\partial R}{\partial \lambda}\Bigg|_{(z^{*},\lambda^{*},p)}^{-1}\cdot\frac{\partial R}{\partial p}\Bigg|_{(z^{*},\lambda^{*},p)}
\end{align*}$$

We then notice that the sensitivity of $R$ w.r.t. $z$ is simply the [[KKT-Matrix]]:
$$-\frac{\partial R}{\partial (z,\lambda)}\Bigg|_{(z^{*},\lambda^{*},p)} = -\begin{bmatrix*}
\nabla_{z}^{2}\mathcal{L}(z^{*},\lambda^{*}) & -\nabla_{z}g(z^{*}) & -\nabla_{z}h_{\mathbb{A}}(z^{*}) \\
-\nabla_{z}g^{\top}(z^{*}) &  0 & 0\\
-\nabla_{z}h_{\mathbb{A}}^{\top}(z^{*}) & 0 & 0
\end{bmatrix*}$$
where
$$-\frac{\partial R}{\partial z}\Bigg|_{(z^{*},\lambda^{*},p)} = -\begin{bmatrix*}
\nabla_{z}^{2}\mathcal{L}(z^{*},\lambda^{*})\\
-\nabla_{z}g^{\top}(z^{*})\\
-\nabla_{z}h_{\mathbb{A}}^{\top}(z^{*})
\end{bmatrix*},\qquad 
-\frac{\partial R}{\partial \lambda}\Bigg|_{(z^{*},\lambda^{*},p)} = -\begin{bmatrix*}
-\nabla_{z}g(z^{*}) & -\nabla_{z}h_{\mathbb{A}}(z^{*}) \\
0 & 0\\
0 & 0
\end{bmatrix*}$$
We also have that
$$\frac{\partial R}{\partial p}\Bigg|_{(z^{*},\lambda^{*},p)} = \begin{bmatrix*}
\nabla_{z,p}\,\mathcal{L}(z^{*},\lambda^{*}) \\
-\nabla_{p}\,g^{\top}(z^{*}) \\
-\nabla_{p}\,h_{\mathbb{A}}^{\top}(z^{*})
\end{bmatrix*}$$
Thus, the complete sensitivity can be computed as:
$$\frac{d}{dp}\begin{bmatrix}z^{*} \\ \bar \lambda^{*} \\ \hat \lambda^{*}\end{bmatrix} = -\begin{bmatrix*}
\nabla_{z}^{2}\mathcal{L}(z^{*},\lambda^{*}) & -\nabla_{z}g(z^{*}) & -\nabla_{z}h_{\mathbb{A}}(z^{*}) \\
-\nabla_{z}g^{\top}(z^{*}) &  0 & 0\\
-\nabla_{z}h_{\mathbb{A}}^{\top}(z^{*}) & 0 & 0
\end{bmatrix*}^{-1}
\begin{bmatrix*}
\nabla_{z,p}\,\mathcal{L}(z^{*},\lambda^{*}) \\
-\nabla_{p}\,g^{\top}(z^{*}) \\
-\nabla_{p}\,h_{\mathbb{A}}^{\top}(z^{*})
\end{bmatrix*}
$$

**Remarks:**
- Notice that the KKT matrix is also computed for performing [[Newton Step|Newton steps]].
- **OBS:** The parametric sensitivity is not valid if
	- an inequality constraint is weakly active !
		- *(all must be strongly active or completely inactive)*
	- the point $(z^{*},\lambda^{*})$ is not a KKT point
		- *(because only KKT points satisfy the implicit function: $R\equiv 0$, which is needed to compute the derivative in the way done above)*
- If the parameter enters affinely and in the equality constraints only; that is $g(z,p) = \gamma(z) + \alpha p$, then we have 

$$\frac{\partial R}{\partial p}\Bigg|_{(z^{*},\lambda^{*},p)} = \begin{bmatrix*}
0 \\
- \alpha \\
0
\end{bmatrix*} $$
