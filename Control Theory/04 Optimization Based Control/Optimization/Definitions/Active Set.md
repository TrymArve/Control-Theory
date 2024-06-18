---
tags: 
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
Consider ![[NLP formulation#^NLP]]
**Equality:**
The **active set***, $\mathbb{A}_{eq}(z)$ for equality constraints at a point $z\in \mathbb{R}^{n_{z}}$ is the set of all indices for which $g_{i}$ is an [[Active Constraint]]. That is $$\mathbb{A}_{eq}(z) \triangleq \{i\in \mathbb{N}_{1,n_{eq}} | ~ g_{i}(z)=0\}$$
**Remarks:**
- We have:   $z\in \mathbb{F} \implies \mathbb{A}_{eq}=\mathbb{N}_{1,n_{eq}}$
	- it follows that:   $\mathbb{A}_{eq}\centernot=\mathbb{N}_{1,n_{eq}} \implies z\centernot\in \mathbb{F}$


**Inequality:**
The **active set***, $\mathbb{A}_{in}(z)$ for inequality constraints at a point $z\in \mathbb{R}^{n_{z}}$ is the set of all indices for which $h_{i}$ is an [[Active Constraint]]. That is $$\mathbb{A}_{in}(z) \triangleq \{i\in \mathbb{N}_{1,n_{in}} | ~ h_{i}(z)=0\}$$

**Alternatively:**
When only specifying *"active set"*, one usually refers to both equality and inequality constraints at the same time. When defining the constraints as: $$\begin{align*}
c_{i}(z) = 0~\forall i\in \mathbb{N}_{1,n_{eq}} \\
c_{i}(z) \geq 0~\forall i\in \mathbb{N}_{1,n_{in}}
\end{align*}$$we say that the ***active set*** at point $z$ is:
$$\mathbb{A}(z) \triangleq \{i\in \mathbb{N}_{1,n_{eq}+n_{in}} | ~ c_{i}(z)=0\}$$

