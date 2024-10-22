---
tags:
  - Unfinished
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
**Definition:**
The *null space*; $\mathbb{N}_{ull}$, of a [[Linear Map (linear transformation, vector space homomorphism)|linear map]], $l:\mathbb{D}\mapsto \mathbb{O}$, is defined as
$$\mathbb{N}_{ull} \triangleq \{u\in \mathbb{D} ~|~ l(u)=e\}$$
where $e$ is the additive ($+$) vector identity of the domain-[[05 -Vector Space|vector space]].


**Practical definition (for engineers)**
The *null space* of a matrix $A$ the set of vectors that are mapped to zero:
$$\mathbb{N}_{ull} \triangleq \{x ~|~ Ax = 0\}$$


**Remarks:**
- If the domain vector set is $\mathbb{D} = \mathbb{R}^{m}$ or $\mathbb{D} = \mathbb{C}^{m}$, then the additive vector identity is $e = 0\in \mathbb{R}^{m}$
- Let's define: $\mathbb{A} \triangleq \mathbb{D}\setminus \mathbb{N}_{ull}$
- The null space is the [[Function|preimage]] of $0$
	- that is; $l^{-1}(0)\in \mathbb{N}_{ull}$
- The image of $\mathbb{D}$, that is; $im[\mathbb{D}]$, under $l$ is of the same dimensionality as the complement of the nullspace, $\mathbb{A}$. 
	- That is: $im[\mathbb{D}] = \{y ~|~ y=Ax ~\forall x \in \mathbb{A}\}$


**Properties:**
1) We have
$$l(u_{1}) = l(u_{2}) ~~\Longleftrightarrow~~ l(u_{1}-u_{2})=0$$

2) We have
$$\begin{align*}
v \in \mathbb{N}_{ull}  &\implies v \centernot\in \mathbb{A} \\\\
u \in \mathbb{A}  &\implies u \centernot\in \mathbb{N}_{ull}
\end{align*}$$
3) Property 2) naturally gives
$$\dim(\mathbb{A}) + \dim(\mathbb{N}_{ull}) = \dim(\mathbb{D})$$
	 which coupled with
$$\dim(\mathbb{A}) = \dim(im[\mathbb{D}])$$
	gives
$$\dim(\mathbb{N}_{ull}) + \dim(im[\mathbb{D}]) = \dim(\mathbb{D})$$
	- *(known as the rank-nullity theorem)*
**Intuition:** 
The *rank* of matrix (linear map) $A$ is the same as the dimensionality of the output space, e.i. the image of the domain; $im[\mathbb{D}]$:
$$Rank(A) = \dim(im[\mathbb{D}])$$
Also, the *nullity* of A is the dimensionality of its nullspace: $\dim(\mathbb{N}_{ull})$
$$Nullity(A) = \dim(\mathbb{N}_{ull})$$
Thus we have
$$Rank(A) + Nullity(A) = \dim(\mathbb{D})$$
