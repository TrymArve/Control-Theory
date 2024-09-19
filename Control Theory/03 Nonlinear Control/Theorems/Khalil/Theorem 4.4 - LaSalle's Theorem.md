---
tags:
  - Theorem
  - NonlinearSystems/Theorem
Note Author:
  - Trym A. Gabrielsen
Theory Author:
  - Hassan K. Kahlil
Reviewed By:
---
Consider ![[Consider - NTI#^system]]
Let:
- $\mathbb{\Omega} \subseteq \mathbb{D}$
	- be a compact set
	- be positively invariant w.r.t. $\Sigma_{\circ}$
- $V:\mathbb{D}\mapsto \mathbb{R} ~~\text{s.t.}$
	- $V$ continuous on $\mathbb{\Omega}$
	- $\dot{V}(x) \leq 0 \quad \forall x\in \mathbb{\Omega}$
- $\mathbb{E} \triangleq \{ x\in \mathbb{\Omega}~|~ \dot{V}(x) = 0\}$
- $\mathbb{M}\subseteq \mathbb{E}$
	- be the largest positively invariant set in $\mathbb{E}$

Then:
- $x^{\circ}(0)\in \mathbb{\Omega} \implies x^{\circ}(t) \rightarrow \mathbb{M} ~~\text{as}~~ t \rightarrow\infty$




##### Proof
*(page 128 in Khalil)*

Let $x^{\circ}(t)$ be the solution of $\Sigma_{\circ}$, with $x^{\circ}(t_{\circ}) = x_{\circ} \in \mathbb{\Omega}$.
Since 
$$(1)\quad \dot{V}(x) \leq 0 \quad \forall x\in \mathbb{\Omega}$$
and that $\mathbb{\Omega}$ is positively invariant
$$(2)\quad x^{\circ}(t) \in \mathbb{\Omega} \quad \forall t\geq t_{\circ}$$
we have that $V(x^{\circ}(t))$ is a decreasing function of time.
Since $V$ is [[Continuous|continuous]] at each point in $\mathbb{\Omega}$, we have that 
$$(3)\quad  V(x) > \infty \quad \forall x \in \mathbb{\Omega}$$
Combining $(1)$ and $(3)$, we see that $V$ has a limit as $t \rightarrow\infty$
$$t \rightarrow \infty \implies V(x^{\circ}(t)) \rightarrow V^*$$
Also, since $\mathbb{\Omega}$ is positively invariant and [[Closed (set)]], the [[Positive Limit Set|positive limit set]], $\mathbb{L}^{+}(x_{\circ})$ must be contained in $\mathbb{\Omega}$ :
$$\mathbb{L}^{+}(x_{\circ}) \subseteq \mathbb{\Omega}$$
Let $x^{lim} \in \mathbb{L}^{+}$ be a state that $x^{\circ}(t_{n})$ approaches as $n \rightarrow\infty$
$$n \rightarrow \infty \implies x^{\circ}(t_{n}) \rightarrow x^{lim}$$
where $t_{n}\in \bar{t} = \{t_{0},t_{1},t_{2},\cdots\}$ such that $n \rightarrow\infty \implies t_{n} \rightarrow \infty$
Then
$$V(x^{lim}) = \lim\limits_{n \rightarrow\infty} V(x^{\circ}(t_{n})) = V^{*}$$
Meaning that 
$$V(x) = V^{*} \quad \forall x\in \mathbb{L}^{+}$$
Since, by [[Lemma 4.1 - Positive Limit Set|lemma 4.1]], the positive limit set $\mathbb{L}^{+}$ is [[Invariant Set|invariant]], we have that 
$$(4) \quad \dot{V}(x) = 0 \quad\forall x\in \mathbb{L}^{+}$$
which gives
$$\mathbb{L}^{+}\subseteq \mathbb{M} \subseteq \mathbb{E} \subseteq \mathbb{\Omega}$$
(Note that invariance of $\mathbb{L}^{+}$ alone is not sufficient to say that it is a subset of $\mathbb{M}$, since there might be invariant subsets of $\mathbb{\Omega}$ that have $\dot{V}(x) < 0$ for some $x$ in the subset. Whereas, $\mathbb{M}$ requires that $\dot{V}(x) = 0$, since it is a subset of $\mathbb{E}$. Therefore, we needed to show eq. $(4)$ to conclude that $\mathbb{L}^{+} \subseteq \mathbb{M}$.)

We also have that $x^{\circ}(t)$ is [[Boundedness|bounded]], since $\mathbb{\Omega}$ is required to be [[Invariant Set|positively invariant]]. Therefore, by [[Lemma 4.1 - Positive Limit Set|lemma 4.1]], we also get that 
$$t \rightarrow\infty \implies x^{\circ}(t) \rightarrow \mathbb{L}^{+}\subset \mathbb{M} \quad _\blacksquare$$
