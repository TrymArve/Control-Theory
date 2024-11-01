---
tags: []
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By: 
Relevant Papers:
---
Consider the Implicit Function
$$R(z,p) = 0$$
where
- $R$ is $\mathcal{C}^{1}$
- $\nabla_{z}R(z,p)$ is full rank

Then:
- $\exists \xi(p) \mapsto z \quad$ that is
	- well defined 
	- $\mathcal{C}^{1}$
- such that
	- $R(\xi(p),p) \equiv 0$

according to the [[Implicit Function Theorem]].
For simplicity, we write $p \mapsto z^{*}(p)$, instead of $\xi$.

**Sensitivity:**
Since $R(z^{*}(p),p) \equiv 0$, we have that
$$\frac{dR}{dp} = \frac{\partial R}{\partial p} + \frac{\partial R}{\partial z}\frac{dz^{*}}{dp}\equiv 0$$

The sensitivity of $z^{*}$ w.r.t. $p$ at a given point $p_{0}$ is  therefore:
$$\frac{dz^{*}}{dp}\Bigg|_{p_{0}} = -\frac{\partial R}{\partial z}\Bigg|_{(z^{*}(p_{0}),p_{0})}^{-1}\cdot\frac{\partial R}{\partial p}\Bigg|_{(z^{*}(p_{0}),p_{0})}$$

**Remarks:**
- Note that since we require that $\nabla_{z}R(z,p)$ is full rank, we also have that $\frac{\partial R}{\partial z}\big|_{(z^{*}(p_{0}),p_{0})}^{-1}$ exists.
