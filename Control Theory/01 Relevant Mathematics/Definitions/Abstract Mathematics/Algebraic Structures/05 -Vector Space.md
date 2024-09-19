---
tags: []
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
**Definition:**
A *vector space* is an ordered hextuple; $(\mathbb{F},\oplus,\circ,\mathbb{V},+,\cdot)$, consisting of;
- a [[Set|set]] $\mathbb{F}\centernot=\emptyset$
- [[Binary Operation|binary operations]] $\oplus$ and $\circ$ on the set $\mathbb{F}$
- a set $\mathbb{V}\centernot=\emptyset$
- a binary operation $+$ on the set $\mathbb{V}$
- and a [[Function|binary function]]; $$\cdot:\mathbb{F}\times \mathbb{V}\mapsto \mathbb{V}$$

such that
- $(\mathbb{F},\oplus,\circ)$ forms a [[04 -Field|field]]
- $(\mathbb{V},+)$ forms a [[02 Commutative Group (Abelian Group)|commutative group]]
- **multiplicative compatibility:**$$a\circ (b\cdot v) = (a\circ b)\cdot v \quad \forall a,b\in \mathbb{F},v\in \mathbb{V}$$
- the multiplicative identity of $(\mathbb{F},\circ)$, say $e$, is also an identity for the binary function, $\cdot$, in the sense that $$e\cdot v = v \quad \forall v\in \mathbb{V}$$
- Distributivity of vector-scalar multiplication ($\cdot$) with respect to vector addition ($+$); $$a\cdot(v+u) = (a\cdot v) + (a\cdot u) \quad \forall a\in \mathbb{F},v,u\in \mathbb{V}$$
- Distributivity of vector-scalar multiplication with respect to field addition ($\oplus$); $$(a \oplus b) \cdot v = (a\cdot v) \oplus (b\cdot v) \quad \forall a,b\in \mathbb{F},v\in \mathbb{V}$$


**Remarks:**
- There is no multiplicative binary operation on the set of vectors $\mathbb{V}$, which one might think of a vector multiplication, or the cross product.
- An example of a vector space is: $(\mathbb{R},+_s,\cdot_s,\mathbb{R}^n,+_v,\cdot_v)$
	- where
		- $(\mathbb{R},+_s,\cdot_s)$ is the standard field of reals, under scalar addition and multiplication
		- $(\mathbb{R}^n,+_v)$ is an abelian group of the $n^{th}$ power of the reals, and vector addition
		- and $\cdot_v$ is vector-scalar multiplication
	- (notice that scalar and vector addition, $+_s$ and $+_v$, are both typically denoted $+$, since the use is clear from context)
	- (also, the use of either multiplication symbol is usually omitted, since the distinction is also clear from context)
	- (Lastly, the use of a symbol $\cdot$, is often to mean the "inner product", which is a from of vector multiplication, which is not a part of a vector space, but extends the vector space to an [[06 - Inner Product Space|inner product space]])
