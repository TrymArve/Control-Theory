---
tags: 
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
**Also known as:** *'Karush–Kuhn–Tucker'* conditions

Consider ![[NLP formulation#^NLP]]
and ![[Lagrangian#^f38d6e]]
**Definition:**
For a given solution $z^{*}$, and Lagrangian multipliers $\lambda^{*}$, the *KKT conditions* are:
$$\begin{align*}
\text{(KKT-1):} \qquad && \nabla_{z}\mathcal{L}(z^*,\lambda^*)&=0\\
\text{(KKT-2):} \qquad && g(z^*)&=0\\
\text{(KKT-3):} \qquad && h(z^*)&\geq0\\
\text{(KKT-4):} \qquad && \hat{\lambda}^*&\geq0\\
%% \text{(KKT-5):} \qquad && \bar{\lambda}^*_{i}g_{i}(z^*) &=0 \quad \forall i \in \mathbb{Z}_{1,n_{eq}}\\ %%
\text{(KKT-5):} \qquad && \hat{\lambda}^*_{i}h_{i}(z^*) &=0 \quad \forall i \in \mathbb{Z}_{1,n_{in}}
\end{align*}$$

**Remarks:**
- The KKT conditions are guaranteed to hold in a local optimum if the problem is [[Regularity|regular]]
- 