---
tags: []
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By: 
Relevant Papers:
---
Consider:
![[ideal NMPC#^idealNMPC]]
with Lagrangian:
![[Lagrangian (NMPC)#^Simple-Lagrangian]]
*(defined as therein)*

---
We define
$$z^{k} \triangleq \begin{bmatrix} z^{k}_{0}  \\ z^{k}_{1}  \\ \vdots  \\ z^{k}_{N-1}  \\ \tilde x^{k}_{N} \end{bmatrix},
\quad z^{k}_{j} = \begin{bmatrix}\tilde x^{k}_{j}  \\  \tilde u^{k}_{j} \end{bmatrix}~\forall j\in \mathbb{Z}_{0,N-1},
\quad \bar \lambda = \begin{bmatrix} \bar \lambda_{-1}  \\ \bar \lambda_{0}  \\ \vdots  \\ \bar \lambda_{N} \end{bmatrix},
\quad \hat \lambda = \begin{bmatrix} \hat \lambda_{0}  \\ \hat \lambda_{1}  \\ \vdots  \\ \hat \lambda_{N} \end{bmatrix}
$$

^def-z-lam

where the solution to $\text{NLP}^{k}_{\text{NMPC}}$ is:
$$
s^{*}(\hat x_{k}) = \begin{bmatrix} z^{k,*}(\hat x_{k})  \\  \bar \lambda^{*}(\hat x_{k})  \\ \hat \lambda^{*}(\hat x_{k}) \end{bmatrix}
\in \mathbb{R}^{2n_{x}(N+1)+N(n_{u}+n_{h})+\bar n_{\mathcal{T}} + \hat n_{\mathcal{T}}}
$$

^solution-to-NLP



**Sensitivity of Solution $s^{*}$ on Initial Condition $\hat x_{k}$:**
$$\begin{bmatrix*}
-\nabla_{z^{k}}g^{\top}(z^{k,*}) &  0 & 0\\
\nabla_{z^{k}}^{2}\mathcal{L}(z^{k,*},\lambda^{*}) & -\nabla_{z^{k}}g(z^{k,*}) & -\nabla_{z^{k}}h_{\mathbb{A}}(z^{k,*}) \\
-\nabla_{z^{k}}h_{\mathbb{A}}^{\top}(z^{k,*}) & 0 & 0
\end{bmatrix*}
\frac{d s^{*}(\hat x_{k})}{d \hat x_{k}} 
= 
-\begin{bmatrix*} ~~I_{n_{x}\times n_{x}}~~  \\ 0 \\ \vdots  \\ 0
\end{bmatrix*}
\in \mathbb{R}^{2n_{x}(N+1)+N(n_{u}+n_{h})+\bar n_{\mathcal{T}} + \hat n_{\mathcal{T}}}
$$
^sensitivity-on-initial-condition

---
# Derivation
From [[Parameter Sensitivities]], we get
$$
\frac{d s^{*}(\hat x_{k})}{d \hat x_{k}} = -\begin{bmatrix*}
\nabla_{z^{k}}^{2}\mathcal{L}(z^{k,*},\lambda^{*}) & -\nabla_{z^{k}}g(z^{k,*}) & -\nabla_{z^{k}}h_{\mathbb{A}}(z^{k,*}) \\
-\nabla_{z^{k}}g^{\top}(z^{k,*}) &  0 & 0\\
-\nabla_{z^{k}}h_{\mathbb{A}}^{\top}(z^{k,*}) & 0 & 0
\end{bmatrix*}^{-1}
\begin{bmatrix*}
\nabla^{2}_{z^{k},\hat x_{k}}\,\mathcal{L}(z^{k,*},\bar \lambda^{*},\hat \lambda^{*}) \\
-\nabla_{\hat x_{k}}\,g^{\top}(z^{k,*}) \\
-\nabla_{\hat x_{k}}\,h_{\mathbb{A}}^{\top}(z^{k,*})
\end{bmatrix*}
$$
Where we have that 
$$\nabla_{\hat x_{k}}\,g^{\top}(z^{k,*}) = \frac{\partial}{\partial \hat x_{k}}\begin{bmatrix}
\tilde x^{k}_{0} - \hat x_{k} \\[0.5em]
\tilde x^{k}_{1} - f_{d}(t_{k},\tilde x^{k}_{0}, \tilde u^{k}_{0}) \\[0.5em]
\vdots \\[0.5em]
\tilde x^{k}_{j+1} - f_{d}(t_{k+j},\tilde x^{k}_{j}, \tilde u^{k}_{j}) \\[0.5em]
\vdots\\[0.5em]
\tilde x^{k}_{N} - f_{d}(t_{k+N-1},\tilde x^{k}_{N-1}, \tilde u^{k}_{N-1}) \\[0.5em]
\bar{\mathcal{T}}(\tilde x^{k}_{N})
\end{bmatrix}
=
-\begin{bmatrix} ~~I_{n_{x}\times n_{x}}~~  \\ 0 \\ 0  \\ \vdots  \\ 0 \end{bmatrix}\in \mathbb{R}^{(n_{x}\cdot(N+1)+\bar n_{\mathcal{T}} )\times n_{x}}
$$
and (assuming all inequalities are active):
$$\nabla_{\hat x_{k}}\,h^{\top}_{h}(z^{k,*}) = \frac{\partial}{\partial \hat x_{k}}\begin{bmatrix}
h(t_{k},\tilde x^{k}_{0},\tilde u^{k}_{0}) \\
\vdots \\
h(t_{k+j},\tilde x^{k}_{j},\tilde u^{k}_{j}) \\
\vdots  \\
h(t_{k+N-1},\tilde x^{k}_{N-1},\tilde u^{k}_{N-1}) \\[0.3em]
\hat{\mathcal{T}}(\tilde x^{k}_{N})
\end{bmatrix}
=
\begin{bmatrix} ~~0~~  \\ 0 \\ 0  \\ \vdots  \\ 0 \end{bmatrix} \in \mathbb{R}^{(n_{h}N+\hat n_{\mathcal{T}})\times n_{x}}
$$
The [[Jacobian of Lagrangian (NMPC)|Lagrangian]] term is:
$$\frac{\partial}{\partial \hat x_{k}} 
\nabla_{z^{k}} \mathcal{L} = 
\frac{\partial}{\partial \hat x_{k}} \underbrace{\begin{bmatrix} 
\nabla_{\tilde x^{k}_{0}}f_{d,0}\bar \lambda_{0} - \bar \lambda_{-1}\\ 
  \nabla_{\tilde u^{k}_{0}}f_{d,0} \bar \lambda_{0}\\ 
\vdots\\
 \nabla_{\tilde x^{k}_{j}} f_{d,j}\bar \lambda_{j} - \bar \lambda_{j-1}\\ 
  \nabla_{\tilde u^{k}_{j}} f_{d,j} \bar \lambda_{j}  \\ 
\vdots\\
\nabla_{\tilde x^{k}_{N-1}}  f_{d,N-1} \bar \lambda_{N-1} - \bar \lambda_{N-2}\\ 
   \nabla_{\tilde u^{k}_{N-1}}  f_{d,N-1}  \bar \lambda_{N-1}\\ 
  -  \nabla_{\tilde x^{k}_{N}}\bar{\mathcal{T}}(\tilde x^{k}_{N})\bar \lambda_{N} - \bar \lambda_{N-1}
\end{bmatrix}}_{\text{dynamic terms}}
+\frac{\partial}{\partial \hat x_{k}} \underbrace{\begin{bmatrix} 
\nabla_{\tilde x^{k}_{0}} L_{0} \\
\nabla_{\tilde u^{k}_{0}} L_{0} \\  
\vdots\\
\nabla_{\tilde x^{k}_{j}} L_{j} \\ 
\nabla_{\tilde u^{k}_{j}} L_{j} \\ 
\vdots\\
\nabla_{\tilde x^{k}_{N-1}} L_{N-1} \\
\nabla_{\tilde u^{k}_{N-1}} L_{N-1} \\  
\nabla_{\tilde x^{k}_{N}} T(\tilde x^{k}_{N}) 
\end{bmatrix}}_{\text{objective terms}}
+\frac{\partial}{\partial \hat x_{k}} \underbrace{\begin{bmatrix} 
-\nabla_{\tilde x^{k}_{0}}  h_{0}\hat \lambda_{0} \\
-\nabla_{\tilde u^{k}_{0}}  h_{0}\hat \lambda_{0} \\
\vdots\\
-\nabla_{\tilde x^{k}_{j}}  h_{j} \hat \lambda_{j}\\ 
-\nabla_{\tilde u^{k}_{j}}  h_{j}\hat \lambda_{j} \\ 
\vdots\\
- \nabla_{\tilde x^{k}_{N-1}} h_{N-1}\hat \lambda_{N-1} \\ 
- \nabla_{\tilde u^{k}_{N-1}} h_{N-1}\hat \lambda_{N-1} \\ 
-\nabla_{\tilde x^{k}_{N}} \hat{\mathcal{T}}(\tilde x^{k}_{N}) \hat \lambda_{N} 
\end{bmatrix}}_{\text{feasibility terms}}
=\begin{bmatrix}0  \\  0  \\ \vdots \\ 0\end{bmatrix}+\begin{bmatrix}0  \\  0  \\ \vdots \\ 0\end{bmatrix}+\begin{bmatrix}0  \\  0  \\ \vdots \\ 0\end{bmatrix} = \begin{bmatrix}0  \\  0  \\ \vdots \\ 0\end{bmatrix}$$
Therefore the sensitivity can be found as the solution to
$$\begin{bmatrix*}
\nabla_{z^{k}}^{2}\mathcal{L}(z^{k,*},\lambda^{*}) & -\nabla_{z^{k}}g(z^{k,*}) & -\nabla_{z^{k}}h_{\mathbb{A}}(z^{k,*}) \\
-\nabla_{z^{k}}g^{\top}(z^{k,*}) &  0 & 0\\
-\nabla_{z^{k}}h_{\mathbb{A}}^{\top}(z^{k,*}) & 0 & 0
\end{bmatrix*}
\frac{d s^{*}(\hat x_{k})}{d \hat x_{k}} 
= 
-\begin{bmatrix*}
\begin{bmatrix} ~~0~~ \\ \vdots  \\ 0\end{bmatrix} \in \mathbb{R}^{(n_{x}(N+1)+n_{u}N)\times n_{x}} \\
\begin{bmatrix} ~~I_{n_{x}\times n_{x}}~~  \\ 0 \\ \vdots  \\ 0 \end{bmatrix} \in \mathbb{R}^{(n_{x}(N+1)+\bar n_{\mathcal{T}})\times n_{x}} \\
\begin{bmatrix} ~~0~~ \\ \vdots  \\ 0 \end{bmatrix} \in \mathbb{R}^{(n_{h}N+\hat n_{\mathcal{T}})\times n_{x}}
\end{bmatrix*}$$
Which can be rewritten as
$$\begin{bmatrix*}
-\nabla_{z^{k}}g^{\top}(z^{k,*}) &  0 & 0\\
\nabla_{z^{k}}^{2}\mathcal{L}(z^{k,*},\lambda^{*}) & -\nabla_{z^{k}}g(z^{k,*}) & -\nabla_{z^{k}}h_{\mathbb{A}}(z^{k,*}) \\
-\nabla_{z^{k}}h_{\mathbb{A}}^{\top}(z^{k,*}) & 0 & 0
\end{bmatrix*}
\frac{d s^{*}(\hat x_{k})}{d \hat x_{k}} 
= 
-\begin{bmatrix*} ~~I_{n_{x}\times n_{x}}~~  \\ 0 \\ \vdots  \\ 0
\end{bmatrix*}
\in \mathbb{R}^{(2n_{x}(N+1)+N(n_{u}+n_{h})+\bar n_{\mathcal{T}} + \hat n_{\mathcal{T}})\times n_{x}}
$$
