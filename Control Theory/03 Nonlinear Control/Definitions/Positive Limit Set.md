---
tags:
  - Definition
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
Consider
![[Consider - NTV#^system]]
and its solution
$$x^{\circ}(t), \quad x^{\circ}(t_{\circ}) = x_{\circ}$$
Consider a sequence of times:
- $\bar{t} = \{\bar{t}_{0},\bar{t}_{1},\bar{t}_{2},\cdots\}$
- such that $n \rightarrow \infty \implies t_{n} \rightarrow \infty$

**Definition:**
The *positive limit set* of $\Sigma_{\circ}$ for an initial condition $x_{\circ}$ is the set $\Lambda^{+}(x_{\circ})$ such that
$$\Lambda^{+}(x_{\circ}) \triangleq \Big\{~~x\in \mathbb{R}^{n_{x}} ~~|~~ \exists \bar{t}: n \rightarrow \infty \implies x^{\circ}(t_{n})\rightarrow x~~\Big\}$$

**Remarks:**
- Note that this definition allows the state to not actually converge to a limit in the traditional sense.
	- That is:  $t \rightarrow \infty \centernot\implies x^{\circ}(t) \rightarrow x^*$
- For example, the state may approach a periodic orbit; $$x^{orb}(t) = x^{orb}(t+T) \quad \forall t\geq0$$for some $T>0$.
	- In this case, a trajectory; $$x^{\circ}(t) \rightarrow x^{orb}(t)$$ may have a limit, by an appropriate choice of sequence $\bar{t}$ :
	- $\bar{t} = \{t_{\circ},~ t_{\circ} + T,~ t_{\circ} + 2T,~ \cdots\}$
	- Then on may have: $$ n \rightarrow \infty \implies x^{\circ}(\bar{t}_{n}) \rightarrow x^{orb}_{\circ} $$
	- In which case: $x^{orb}_{\circ} \in \Lambda^{+}(x_{\circ})$
