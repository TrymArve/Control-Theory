---
tags: []
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By: 
Relevant Papers:
---

Consider ![[NLP formulation#^NLP]]
and ![[Lagrangian#^Lagrangian]]
The KKT conditions are: ![[KKT Conditions (First-Order Necessary Conditions)#^KKT-conditions]]

For equality constrained NLPs, we can alternatively write the KKT conditions are the Jacobian of the Lagrangian w.r.t. the primal-dual vector, $s \triangleq \begin{bmatrix}z \\ \lambda \end{bmatrix}$, which we call the *KKT-vector* (when transposed):
$$\kappa(s) = \nabla_{s} \mathcal{L} (z,\lambda) = \frac{\partial \mathcal{L}(z,\lambda)}{\partial s}^{\top} = \begin{bmatrix}
\nabla_{z} \phi(z) - \nabla_{z}g^{\top}(z)\lambda \\
 - g(z)
\end{bmatrix}$$

^KKT-vector

**Remarks**
- The KKT vector is only applicable to equality constrained NLPs, although, active inequalities can be assumed to be equality constraints in the search for a KKT point.
	- This is useful in some cases.
- We can see that the KKT conditions are in fact recovered by the KKT vector:

$$\kappa(s) = \nabla_{s} \mathcal{L}(s) 
= \begin{bmatrix} 
\nabla_{z} \mathcal{L} \\
\nabla_{\lambda} \mathcal{L}\end{bmatrix}
= \begin{bmatrix}
\nabla_{z} \phi(z) - \nabla_{z}(\lambda^{\top}g(z)) \\
\nabla_{\lambda} \phi(z) - \nabla_{\lambda}(\lambda^{\top}g(z))
\end{bmatrix}
= \begin{bmatrix}
\nabla_{z} \phi(z) - \nabla_{z}g^{\top}(z)\lambda \\
 - g(z)
\end{bmatrix}$$

 - When this vector is equal to zero, the KKT conditions are met. (not inequalities)