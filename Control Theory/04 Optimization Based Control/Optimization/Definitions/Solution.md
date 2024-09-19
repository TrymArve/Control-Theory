---
tags:
  - Optimization
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---

Consider ![[NLP formulation#^NLP]]
If:
- $z^{*} \in \mathbb{F}$
- $\phi(z^{*})\leq \phi(z') \quad \forall z' \in \tilde{\mathbb{N}}(z^{*}) \cap \mathbb{F}$
	where
	- $\tilde{\mathbb{N}}(z)$ is a neighborhood of $z$
	- $\mathbb{F}$ is the [[Feasible Set]] of (NLP)

Then:
- $z^*$ is a ***solution*** of (NLP)

**Remarks:**
- a solution is also referred to as a ***"Local solution"***, to distinguish the concept from a **global solution**.


# Strict Solution
Consider ![[NLP formulation#^NLP]]
If:
- $z^{*} \in \mathbb{F}$
- $\phi(z^{*}) < \phi(z') \quad \forall z' \in \tilde{\mathbb{N}}(z^{*}) \cap \mathbb{F}$

Then:
- $z^*$ is a ***strict solution*** of (NLP)

**Remarks:**
- the difference from a "solution", is that the point must yield a **strictly smaller** objective value than the other feasible points in its neighborhood.
- also called a "strict *local* solution"


# Global Solution
Consider ![[NLP formulation#^NLP]]
If:
- $z^{*} \in \mathbb{F}$
- $\phi(z^{*}) \leq \phi(z') \quad \forall z' \in \mathbb{F}$

Then:
- $z^*$ is a ***global solution*** of (NLP)

**Remarks:**
- No feasible point yields a smaller objective value than $z^{*}$
- A global solution is a local solution
- A global solution is not necessarily a strict local solution



# Unique Solution
Consider ![[NLP formulation#^NLP]]
If:
- $z^{*} \in \mathbb{F}$
- $\phi(z^{*}) < \phi(z') \quad \forall z' \in \mathbb{F}\setminus z^{*}$

Then:
- $z^*$ is a ***unique solution*** of (NLP)

**Remarks:**
- All other feasible points yield a strictly larger objective value
- There is only one or zero unique solutions
- A unique solution is a global solution
- A unique solution is a strict solution
- A unique solution is a, and is the only, global solution


