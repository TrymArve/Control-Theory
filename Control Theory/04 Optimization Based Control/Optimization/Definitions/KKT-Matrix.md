---
tags:
  - Definition
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
Consider 
![[NLP formulation#^NLP]]
and the ![[Lagrangian#^Lagrangian]]
**Definition:**
For $\text{(NLP)}$, the *KKT matrix* is defined as:
$$K(z,\lambda) \triangleq \frac{\partial^{2} \mathcal{L}(z,\lambda)}{\partial s^{2}}$$
where $s$ is the primal-dual vector.


**Note**
The KKT matrix takes the form:
$$K(z,\lambda) = \begin{bmatrix*}
\nabla_{z}^{2}\mathcal{L}(z,\lambda) & -\nabla_{z}g(z) & -\nabla_{z}h_{\mathbb{A}}(z) \\
-\nabla_{z}g^{\top}(z) &  0 & 0\\
-\nabla_{z}h_{\mathbb{A}}^{\top}(z) & 0 & 0
\end{bmatrix*}$$

^KKT-Matrix

when the primal-dual vector $s$ is created by stacking the primal and the dual variables:
$$s = \begin{bmatrix}z \\ \lambda\end{bmatrix}$$
 

**Remarks:**
- $h_{\mathbb{A}}$ is vector composed of the elements of $h$ that are [[Active Constraint|active]] at $z$, i.e.
$$h_{\mathbb{A}}(z) \triangleq \begin{bmatrix}h_{i_{1}}(z) \\ h_{i_{2}}(z) \\ \vdots  \\ h_{i_{j}}(z) \end{bmatrix}$$
where 
$$\{i_{1},i_{2},\dots,i_{j}\} = \mathbb{A}_{in}$$
- Note that depending on where the [[Lagrangian]] is defined using addition or subtraction of the constraint-terms, the KKT matrix may take different signs in front of the constraint gradients appearing in the matrix.
- Also, the sign of the transposed gradients is adjusted to make the matrix symmetric. Therefore, the sign of the corresponding vector of the KKT system: $K\cdot w = v$ must be adjusted accordingly.
- Note that the [[Rank of KKT matrix|KKT matrix has full rank]] if LICQ and SOSC hold.
- 