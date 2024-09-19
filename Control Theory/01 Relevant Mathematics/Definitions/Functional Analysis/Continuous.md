---
tags:
  - Definition
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
Consider 
- [[Metric Space|metric spaces]] $\mathbb{D}$ and $\mathbb{O}$
	- with respective [[Metric|metrics]] $d(\cdot,\cdot)$ and $o(\cdot,\cdot)$
- a [[Function|function]] $f:\mathbb{D}\mapsto \mathbb{O}$

**Definition**
The function $f$ is <u><i>continuous at a point</i></u> in its domain; $x_{c} \in \mathbb{D}$, iff
- $f(x_{c}) \in \mathbb{O}$ 
- $o(y,f(x_{c})) < \infty \quad \forall y \in \mathbb{O}$
- $\forall \epsilon>0$
	- $\exists \delta>0:$
		- $\forall x\in \mathbb{D}$
			- $d(x,x_{c})<\delta \implies o(~f(x)~,~f(x_{c})~) < \epsilon$


**Remarks:**
- Note that the notion of continuity is defined for a *point*, not the function itself nor a subdomain.
- We often refer to a function being continuous on a subset of the domain, or simply on the entire domain. This means that the function is continuous at each point in that set.
- There are also notions of continuity of function that to not map between metric spaces.