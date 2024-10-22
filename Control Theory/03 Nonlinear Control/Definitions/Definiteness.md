---
tags:
  - NonlinearSystems/Definition
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---

Consider functions 
$$
\begin{align}
f:&~\mathbb{D}\subseteq\mathbb{R}^{n}\mapsto\mathbb{R} \\
F:&~\mathbb{M}\subseteq\mathbb{R}^{n}\mapsto\mathbb{R}^{n}
\end{align}
$$
# Positive definiteness
Function $f$ is **positive definite** in $\mathbb{D}$ iff
$$ 
\begin{align}
f(x) >& ~0 \quad \forall x\in\mathbb{D}\setminus\{0\} \\
f(x) =& ~0 \quad \forall x=0
\end{align}
$$
## Negative definiteness
Function $f$ is **negative definite** iff
- $p=-f$ is positive definite


# Positive semi-definiteness
Function $f$ is **positive semi-definite** iff
$$ 
\begin{align}
f(x) \geq& ~0 \quad \forall x\in\mathbb{D}\setminus\{0\} \\
f(x) =& ~0 \quad \forall x=0
\end{align}
$$
## Negative semi-definiteness
Function $f$ is **negative semi-definite** iff
- $p=-f$ is positive semi-definite

# Half-Definiteness 
Function $F$ is **half-definite** iff
- $\tilde{f}(x) = x^\top F(x)$
is positive definite

## Negative Half-Definiteness
Function $F$ is **negative half-definite** iff 
- $P=-F$ is half-definite

## Strict Half-Definiteness
Function $F$ is **strictly (negative) half-definite** iff:
- $F$ is (negative) half-definite
- and $F(0) = 0$

## semi-half-definiteness
Function $F$ is **(negative) semi-half-definite** iff
$$ \tilde{f}(x) = x^\top F(x)$$
is positive (negative) semi-definite.

