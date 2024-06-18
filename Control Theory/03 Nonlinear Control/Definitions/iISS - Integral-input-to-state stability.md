---
tags:
  - NonlinearSystems/Definition
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
The system 
$$\dot{x} = f(x,v)$$
is said to be ***integral-input-to-state stable (iISS)*** iff:
- $\exists\, \omega \in \mathcal{K}_\infty, ~\beta\in\mathcal{KL}, ~\mu \in \mathcal{K} \, :$
	$$ \omega(|x(t)|) \leq \beta(|x(0)|,t) + \int_{0}^{t} \mu(|v(\tau)|) ~d\tau \quad\forall t\geq 0$$

**Remarks:**
- Taken from "Definition 23 (Angeli-Sontag)"  of lecture slides by Antonio Loria.
- $\mu$ is called the "gain".
## Intuition
- We notice that iISS is defined similarly to ISS, but the Globally Asymptotically Attractive set is not a function of the constant value of the input, but rather a function of the integral of the input. That is, it 'remembers' the history of the input, and the entire history of the input is contributing to the size of the attractive set.

