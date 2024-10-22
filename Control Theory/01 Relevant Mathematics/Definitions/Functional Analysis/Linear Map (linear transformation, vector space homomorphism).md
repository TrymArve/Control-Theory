---
tags:
  - Unfinished
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
**Definition:**
A *linear map*, $l$, is a [[Function|function]] 
$$l:\mathbb{D} \mapsto \mathbb{O}$$

where $\mathbb{D}$ and $\mathbb{O}$ are the vector sets of [[05 -Vector Space|vector spaces]]:
$$\begin{align}
&\mathcal{V}_{1} = (\mathbb{F},\oplus,\circ,\mathbb{D},+,\cdot)\\
&\mathcal{V}_{2} = (\mathbb{F},\oplus,\circ,\mathbb{O},\tilde{+},\tilde{\cdot})
\end{align}$$

with the same [[04 -Field|field]], $(\mathbb{F},\oplus,\circ)$, such that
- $\forall (u,v) \in \mathbb{D}^{2},~c\in \mathbb{F}$
	- **(Additivity)**
$$l(u+ v) = l(u) ~\tilde{+}~ l(v)$$

	- **(Homogeneity)**
$$l(c\cdot u) = c ~\tilde{\cdot}~ l(u)$$



**Remarks:**
- As a consequence of the conditions for a linear map, we get:
$$l(c_{1}\cdot u_{1} + c_{2}\cdot u_{2} +\cdots+ c_{n}\cdot u_{n}) = c_{1}~\tilde{\cdot}~l(u_{1}) ~\tilde{+}~ c_{2}~\tilde{\cdot}~l(u_{2}) ~\tilde{+}~\cdots~\tilde{+}~ c_{n}~\tilde{\cdot}~l(u_{n})$$

	or 
$${\huge l} \left(\sum\limits_{i=1}^{n} c_{i}\cdot u_{i} \right) = \sum\limits_{i=1}^{n} c_{i} ~\tilde{\cdot}~  l(u_{i})$$

- The notion of a linear map is also defined for the more general case of [[modules]] over a [[03 -Ring|ring]] rather than a field.
- If $l$ is a [[Bijective|bijection]], then it is a [[linear isomorphism]]
- If $\mathbb{D}=\mathbb{O}$, then $l$ is a [[linear endomorphism]]
- If $\mathbb{D}$ and $\mathbb{O}$ are finite-dimensional, and one defines a basis for each, then the linear map $l:\mathbb{D}\mapsto \mathbb{O}$ can be represented by a matrix:
$$v = l(u) = Au$$

	- note that if $A\in \mathbb{R}^{n\times m}$, then $\mathbb{D} = \mathbb{R}^{m}$ and $\mathbb{O} = \mathbb{R}^{n}$

