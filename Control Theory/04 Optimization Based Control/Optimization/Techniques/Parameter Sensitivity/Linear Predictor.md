---
tags: []
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By: 
Relevant Papers:
---
Consider the parametric NLP:
![[Parametric NLP#^PNLP]]
and its solution $(z^{*},\bar\lambda^{*},\hat\lambda^{*})$, for a given parameter $p_{0}$.

**Linear Predictor:**
If the parameter vector changes to $p_{1} = p_{0} + \Delta p$, the *Linear Predictor* predicts the following change in the solution:
$$\begin{bmatrix} \Delta z \\ \Delta \bar\lambda  \\ \Delta\hat\lambda \end{bmatrix}
= -\begin{bmatrix*}
\nabla_{z}^{2}\mathcal{L}(z^{*},\lambda^{*}) & -\nabla_{z}g(z^{*}) & -\nabla_{z}h_{\mathbb{A}}(z^{*}) \\
-\nabla_{z}g^{\top}(z^{*}) &  0 & 0\\
-\nabla_{z}h_{\mathbb{A}}^{\top}(z^{*}) & 0 & 0
\end{bmatrix*}^{-1}
\begin{bmatrix*}
\nabla_{z,p}\,\mathcal{L}(z^{*},\lambda^{*}) \\
-\nabla_{p}\,g^{\top}(z^{*}) \\
-\nabla_{p}\,h_{\mathbb{A}}^{\top}(z^{*})
\end{bmatrix*}\cdot\Delta p
$$
to find the approximate solution $(z^{+},\bar\lambda^{+},\hat\lambda^{+}) = (z^{*},\bar\lambda^{*},\hat\lambda^{*}) + \Delta (z,\bar\lambda,\hat\lambda)$.




**Remarks:**
- This resulting linear system has the same linear transformation as the [[KKT system]], i.e. the [[KKT-Matrix]]
- The inverse of the KKT matrix is computed several times during the [[Newton Method|Newton method]] on the KKT conditions.
- Can be used to adjust a solution of an optimal control problem upon receiving a state estimate different form the one that was predicted.
	- In this case, the current state is a parameter, and the NLP is solved for a predicted state value. Upon receiving an estimate of the true state value, the solution can be adjusted using the NLP's parameter sensitivity to the current state.
- ***Important:*** The the sensitivity of the solution w.r.t. the parameter vector is only valid a KKT point.



**Derivation:**
By using the [[Parameter Sensitivities|NLP parameter sensitivities]]:

$$\begin{bmatrix} z^{+} \\ \bar\lambda^{+}  \\ \hat\lambda^{+} \end{bmatrix}
= \left.\frac{d}{dp}\begin{bmatrix}z^{*}(p) \\ \bar \lambda^{*}(p) \\ \hat \lambda^{*}(p)\end{bmatrix}\right|_{(z^{*},\bar\lambda^{*},\hat\lambda^{*})} \cdot\Delta p ~~+~~ 
\begin{bmatrix} z^{*} \\ \bar\lambda^{*}  \\ \hat\lambda^{*} \end{bmatrix}
$$
where *(obs! see remarks)*
$$\left.\frac{d}{dp}\begin{bmatrix}z^{*}(p) \\ \bar \lambda^{*}(p) \\ \hat \lambda^{*}(p)\end{bmatrix}\right|_{(z^{*},\bar\lambda^{*},\hat\lambda^{*})} = -\begin{bmatrix*}
\nabla_{z}^{2}\mathcal{L}(z^{*},\lambda^{*}) & -\nabla_{z}g(z^{*}) & -\nabla_{z}h_{\mathbb{A}}(z^{*}) \\
-\nabla_{z}g^{\top}(z^{*}) &  0 & 0\\
-\nabla_{z}h_{\mathbb{A}}^{\top}(z^{*}) & 0 & 0
\end{bmatrix*}^{-1}
\begin{bmatrix*}
\nabla_{z,p}\,\mathcal{L}(z^{*},\lambda^{*}) \\
-\nabla_{p}\,g^{\top}(z^{*}) \\
-\nabla_{p}\,h_{\mathbb{A}}^{\top}(z^{*})
\end{bmatrix*}$$

**Alternatively, we can write:**
$$\begin{bmatrix} \Delta z \\ \Delta \bar\lambda  \\ \Delta\hat\lambda \end{bmatrix}
= \left.\frac{d}{dp}\begin{bmatrix}z^{*}(p) \\ \bar \lambda^{*}(p) \\ \hat \lambda^{*}(p)\end{bmatrix}\right|_{(z^{*},\bar\lambda^{*},\hat\lambda^{*})} \cdot\Delta p
$$

giving the final form:
$$\begin{bmatrix} \Delta z \\ \Delta \bar\lambda  \\ \Delta\hat\lambda \end{bmatrix}
= -\begin{bmatrix*}
\nabla_{z}^{2}\mathcal{L}(z^{*},\lambda^{*}) & -\nabla_{z}g(z^{*}) & -\nabla_{z}h_{\mathbb{A}}(z^{*}) \\
-\nabla_{z}g^{\top}(z^{*}) &  0 & 0\\
-\nabla_{z}h_{\mathbb{A}}^{\top}(z^{*}) & 0 & 0
\end{bmatrix*}^{-1}
\begin{bmatrix*}
\nabla_{z,p}\,\mathcal{L}(z^{*},\lambda^{*}) \\
-\nabla_{p}\,g^{\top}(z^{*}) \\
-\nabla_{p}\,h_{\mathbb{A}}^{\top}(z^{*})
\end{bmatrix*}\cdot\Delta p
$$
