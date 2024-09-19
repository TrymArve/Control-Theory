---
tags: []
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
An *inner product*; $$\langle\cdot,\cdot\rangle : \mathbb{V}\times \mathbb{V} \mapsto \mathbb{R}$$is a [[Function|binary function]] that satisfies
- **(positive definiteness)** $$\begin{gather}\langle x,y\rangle >0 \quad \forall (x,y \centernot=e)\in \mathbb{V} \\ \langle e,e\rangle = 0\end{gather}$$
	- where $e$ is the additive identity of the group $(\mathbb{V},+)$
		- (usually $e=0$)
- **(conjugate symmetry)** $$\langle x,y \rangle = \overline{\langle y,x\rangle}$$
- **(Linearity)** $$\langle (a\cdot x) + (b\cdot y),z \rangle = a\circ\langle x,z\rangle + b\circ\langle y,z\rangle \quad \forall x,y,z\in \mathbb{V},a,b \in \mathbb{R}$$
	- (for some appropriate notion of compatible vector-scalar multiplication ($\cdot$), and scalar multiplication ($\circ$))


**Remarks:**
- If, instead of positive definiteness, one only requires positive semi-definiteness, then this is the definition of a *"positive semi-definite Hermitian form"*
- The inner product does not satisfy the triangle inequality, and thus is not a [[Metric|metric]].
- The inner product may be used to define a *"norm"*: $$||x|| \triangleq \sqrt{\langle x,x\rangle}$$
- The norm may then be used to define a metric, which also satisfies the triangle inequality: $$\begin{align} d(x,y) &\triangleq ||x-y|| \\ &= \sqrt{\langle x-y ~,~x-y\rangle}\end{align}$$
	- (where $-$ denotes the vector additive ($+$) inverse)
