**Also known as:** *'Karush–Kuhn–Tucker' conditions

Consider ![[NLP formulation#^NLP]]
and ![[Lagrangian#^f38d6e]]
For a given solution $z^{*}$, and lagrangian multipliers $\lambda^{*}$, the KKT conditions are:
$$\begin{align*}
\text{(KKT-1):} \qquad && \nabla_{z}\mathcal{L}(z^*,\lambda^*)&=0\\
\text{(KKT-2):} \qquad && g(z^*)&=0\\
\text{(KKT-3):} \qquad && h(z^*)&\geq0\\
\text{(KKT-4):} \qquad && \hat{\lambda}^*&\geq0\\
\text{(KKT-5):} \qquad && \bar{\lambda}^*_{i}g_{i}(z^*) &=0 \quad \forall i \in \mathbb{Z}_{1,n_{eq}}\\
\text{(KKT-6):} \qquad && \hat{\lambda}^*_{i}h_{i}(z^*) &=0 \quad \forall i \in \mathbb{Z}_{1,n_{in}}
\end{align*}$$
