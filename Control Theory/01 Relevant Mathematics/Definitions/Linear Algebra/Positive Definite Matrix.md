---
tags:
  - Unfinished
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
**Obs! ⚠ Caution ⚠**
The notion of "[[Definiteness|positive definiteness]]" applies to functions, and the notion of a *positive definite matrix* is only meant to reflect that the equivalent [[Quadratic Form|quadratic form]] is positive definite. Following convention, this notion therefore only regards **square, symmetric** matrices


**Definition:**
A *positive definite matrix* is a matrix $M\in \mathbb{R}^{n\times n}$ such that
- $x^{\top}Mx > 0 \quad \forall x\in \mathbb{R}^{n}\setminus\{0\}$
- ($M = M^{\top}$ *(symmetric)* is sometimes required by convention)


**Remarks:**
- It is common to use the following notation to indicate that a matrix is positive definite: $M \succ 0$
- The requirement that $M$ is symmetric is purely convention, and sometimes one might see that a non-symmetric matrix is referred to as positive definite.
	- Where the only requirement is: $x^{\top}Mx > 0 \quad \forall x\in \mathbb{R}^{n}\setminus\{0\}$


**Equivalent statements:**
The following statements are all sufficient conditions for positive definiteness of $M$
$$\begin{align*}
&(1): \quad x^{\top}Mx > 0 \quad \forall x\in \mathbb{R}^{n}\setminus\{0\}\\[0.5cm]
&(2): \quad \exists P,B\in \mathbb{R}^{n\times n}: ~~ (P^{\top}MP=B ~~\wedge~~B \text{~is diagonal with positive elements})\\[0.5cm]
&(3): \quad \exists B: ~~ (M = B^{\top}B ~~\wedge~~ B \text{~is invertible})\\[0.5cm]
&(4): \quad M = M^{\top} ~~ \wedge~~ \lambda_{i}>0 ~\forall i
\end{align*}$$
(where $\lambda_i$ are the eigen values of $M$)

