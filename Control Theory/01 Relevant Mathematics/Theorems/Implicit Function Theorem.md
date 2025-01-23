---
tags:
  - Theorem
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By: 
Relevant Papers:
---
Let $z$ be implicitly defined by a function $R: \mathbb{R}^{n_{z}}\times \mathbb{R}^{n_{p}} \mapsto \mathbb{R}^{n_{r}}$ as follows:
$$R(z,p) = 0$$
where
- $R$ is $\mathcal{C}^{1}$
- $p \in \mathbb{R}^{n_{p}}$ is some parameter

Then:
- $\forall (z_{0},p_{0}) ~~:~~ \nabla_{z} R(z_{0},p_{0})$ is full rank
	- $\exists \xi:\mathbb{R}^{n_{p}} \mapsto \mathbb{R}^{n_{z}} \quad \wedge \quad \exists r > 0 \quad \text{s.t.}$
		- $\xi$ is $\mathcal{C}^{1}$
		- ($\xi(p_{0}) = z_{0}$ ?)
		- $R(\xi(p),p) = 0 \quad \forall p\in \{p\in \mathbb{R}^{n_{p}}~|~||p-p_{0}||<r\}$

**Remarks:**
- The theorem can be taken to mean that if $R$ is, locally, smooth about $p_{0}$, then, locally, there exists a $\mathcal{C}^{1}$ function $z = \xi(p)$.
	- That is; $z$ can (locally) be described by an explicit function of $p$.
