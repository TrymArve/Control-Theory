---
tags:
  - Definition
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
**Definition:**
A *sequence*, $a$, in a [[Metric Space|metric space]] $(\mathbb{S},d)$;
- $a=\{a_{0},a_{1},a_{2},\dots\} \subseteq \mathbb{S}$
 is called *Cauchy* *(or 'a Cauchy sequence')*, iff:
- $\forall r \in \mathbb{R}_{\geq0}$
	- $\exists n\in \mathbb{N}:$
		- $d(a_{i},a_{j}) < r \qquad \forall i,j > n$



**Intuition:**
A sequence 
- $a=\{a_{0},a_{1},a_{2},\dots\}$ 
where the largest difference between two elements in the $n^{th}$ *tail*:
- $tail(a,n) = \{a_{n},a_{n+1},a_{n+2},\dots\}$ 
becomes arbitrarily small for sufficiently large $n$.

- That is, the *'speard'* of the elements in a tail; $tail(a,n)$, goes to zero for larger n. 