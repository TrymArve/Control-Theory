---
tags: []
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By: 
Relevant Papers:
---
Consider:
![[Basic NMPC-NLP]]

Also, consider:
$$\begin{align*}
\mathbb{X} &= \mathbb{R}^{n_{x}} \\
\mathbb{U} &= \mathbb{R}^{n_{u}} \\
\mathbb{X}_{T} & \triangleq \{ ~x\in \mathbb{R}^{n_{x}}~|~ \bar{\mathcal{T}}(\tilde x^{k}_{N}) = 0 \wedge \hat{\mathcal{T}}(\tilde x^{k}_{N})\geq 0~\} 
%%\mathbb{X}_{T} = \mathbb{R}^{n_{x}}
\end{align*}$$
for some sufficiently smooth implicit functions $\bar{\mathcal{T}} \in \mathbb{R}^{\bar n_{\mathcal{T}}}$ and $\hat{\mathcal{T}} \in \mathbb{R}^{\hat n_{\mathcal{T}}}$. The state and control stage-constraints can then be omitted, and the terminal constraint can be imposed by adding
$$\begin{align*}
\bar{\mathcal{T}}(\tilde x^{k}_{N}) = 0 \\
\hat{\mathcal{T}}(\tilde x^{k}_{N}) \geq 0
\end{align*}$$
to the NLP.

**Lagrangian for NMPC**
The [[Lagrangian]] is then
$$\begin{align*}
\mathcal{L}(\hat x_{k},\tilde x^{k},\tilde u^{k}) = & +\sum\limits_{j =0}^{N-1} L(\tilde{x}^{k}_{j},\tilde{u}^{k}_{j}) + T(\tilde{x}^{k}_{N}) 
& \text{(Objective)}\\
& - \sum\limits_{j=0}^{N-1} \bar \lambda_{j}^{\top} (\tilde x^{k}_{j+1} - f_{d}(t_{k+j},\tilde x^{k}_{j},\tilde u^{k}_{j})) & \text{(Dynamic Constraints)}\\
& - \sum\limits_{j=0}^{N-1} \hat \lambda_{j}^{\top} h(t_{k+j},\tilde x^{k}_{j},\tilde u^{k}_{j}) & \text{(Inequality Constraints)}\\
& - \bar \lambda_{-1}^{\top}(\tilde x^{k}_{0} - \hat x_{k}) & \text{(Initial Value Embedding)}\\
& - \bar \lambda_{N}^{\top}\bar{\mathcal{T}}(\tilde x^{k}_{N}) & \text{(Terminal Equality)}\\
& - \hat \lambda_{N}^{\top}\hat{\mathcal{T}}(\tilde x^{k}_{N}) & \text{(Terminal Inequality)}
\end{align*}$$
^Lagrangian

**Simplification 1:**
Using [[Dynamic Constraints]], [[Inequality Vector]], and [[Objective Terms]], we define:
$$\begin{align*}
\mathcal{L}(\hat x_{k},\tilde x^{k},\tilde u^{k})  
= \qquad & \sum\limits_{j =0}^{N} J_{j}
& \text{(Objective)}\\
 -& \sum\limits_{j=-1}^{N} \bar \lambda_{j}^{\top} g_{j} & \text{(Equality Constraints)}\\
 -& \sum\limits_{j=0}^{N} \hat \lambda_{j}^{\top} h_{j} & \text{(Inequality Constraints)}\\
\end{align*}$$
^Simple-Lagrangian

**Simplification 2:**
It can be rewritten as 
$$
\begin{align*}
\mathcal{L}(\hat x_{k},\tilde x^{k},\tilde u^{k}) =& ~~\sum\limits_{j =0}^{N-1} \bigg( L(\tilde{x}^{k}_{j},\tilde{u}^{k}_{j}) 
 - \bar \lambda_{j}^{\top} (\tilde x^{k}_{j+1} - f_{d}(t_{k+j},\tilde x^{k}_{j},\tilde u^{k}_{j}))
- \hat \lambda_{j}^{\top} h(t_{k+j},\tilde x^{k}_{j},\tilde u^{k}_{j}) \bigg)\\[0.5em]
&~~ + T(\tilde{x}^{k}_{N}) - \bar \lambda_{N}^{\top}\mathcal{T}(\tilde x^{k}_{N}) - \hat \lambda_{N}^{\top}\hat{\mathcal{T}}(\tilde x^{k}_{N})\\
&~~ - \bar \lambda_{-1}^{\top}(\tilde x^{k}_{0} - \hat x_{k})
\end{align*}
$$

By defining
![[Decision Variables#^definition-of-z]]

$$\begin{align*}
\mathcal{L}_{-1}(s^{k}_{-1},s^{k}_{0}) & \triangleq - \bar \lambda_{-1}^{\top}(\tilde x^{k}_{0} - \hat x_{k})\\[0.5em]
\mathcal{L}_{j}(s^{k}_{j},s^{k}_{j+1})  & \triangleq L(\tilde{x}^{k}_{j},\tilde{u}^{k}_{j}) 
 - \bar \lambda_{j}^{\top} (\tilde x^{k}_{j+1} - f_{d}(t_{k+j},\tilde x^{k}_{j},\tilde u^{k}_{j}))
- \hat \lambda_{j}^{\top} h(t_{k+j},\tilde x^{k}_{j},\tilde u^{k}_{j}) ~\forall j\in\mathbb{Z}_{0,N-1}\\[0.5em]
\mathcal{L}_{N}(s^{k}_{N}) & \triangleq T(\tilde{x}^{k}_{N}) - \bar \lambda_{N}^{\top}\mathcal{T}(\tilde x^{k}_{N}) - \hat \lambda_{N}^{\top}\hat{\mathcal{T}}(\tilde x^{k}_{N})
\end{align*}$$
we can simplify the Lagrangian to
$$\mathcal{L}(\hat x_{k},\tilde x^{k},\tilde u^{k}) = \sum\limits_{j=-1}^{N-1}\mathcal{L}_{j}(s^{k}_{j},s^{k}_{j+1}) + \mathcal{L}_{N}(s^{k}_{N})$$ ^Simplified-Lagrangian
