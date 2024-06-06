Consider ![[NLP formulation#^NLP]]
Given a Lagrangian multiplier for inequality constraints; $\mu$, and the [[Feasible Set]];  $\vec{\mathbb{F}}(z)$, the **critical cone** is defined as:
$$
\vec{\mathbb{C}}(z) \triangleq \left\{~~d\in \vec{\mathbb{F}}(z) ~~\bigg| \quad
\nabla h_{i}^{\top}(z)d = 0, \quad \forall i \in \mathbb{A}_{in}: \mu_{i}>0\right\}$$



Equivalently:
$$
\vec{\mathbb{C}}(z) = \left\{~~d\in \mathbb{R}^{n_{z}} ~~\left| \quad \begin{align*}
\nabla g_{i}^{\top}(z)d = 0, & \quad \forall i \in \mathbb{A}_{eq} \\
\nabla h_{i}^{\top}(z)d = 0, & \quad \forall i \in \mathbb{A}_{in}: \mu_{i}>0\\
\nabla h_{i}^{\top}(z)d \geq 0, & \quad \forall i \in \mathbb{A}_{in}: \mu_{i}=0
\end{align*}\right. \right\}$$
