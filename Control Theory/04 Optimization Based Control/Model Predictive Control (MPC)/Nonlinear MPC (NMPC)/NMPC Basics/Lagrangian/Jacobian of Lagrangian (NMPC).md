---
tags: []
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By: 
Relevant Papers:
---
Consider:
![[Lagrangian (NMPC)#^Lagrangian]]
![[Lagrangian (NMPC)#^Simplified-Lagrangian]]
(with $z$ and $s$ defined therein)

---

**Jacobian:**
$$\nabla_{z^{k}} \mathcal{L} = 
\underbrace{\begin{bmatrix} 
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
+\underbrace{\begin{bmatrix} 
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
+\underbrace{\begin{bmatrix} 
-\nabla_{\tilde x^{k}_{0}}  h_{0}\hat \lambda_{0} \\
-\nabla_{\tilde u^{k}_{0}}  h_{0}\hat \lambda_{0} \\
\vdots\\
-\nabla_{\tilde x^{k}_{j}}  h_{j} \hat \lambda_{j}\\ 
-\nabla_{\tilde u^{k}_{j}}  h_{j}\hat \lambda_{j} \\ 
\vdots\\
- \nabla_{\tilde x^{k}_{N-1}} h_{N-1}\hat \lambda_{N-1} \\ 
- \nabla_{\tilde u^{k}_{N-1}} h_{N-1}\hat \lambda_{N-1} \\ 
-\nabla_{\tilde x^{k}_{N}} \hat{\mathcal{T}}(\tilde x^{k}_{N}) \hat \lambda_{N} 
\end{bmatrix}}_{\text{feasibility terms}}\in \mathbb{R}^{n_{x}\cdot(N+1)+n_{u}\cdot(N)}$$

^Jacobian-of-Lagrangian

where we adopt the notation:
$$\begin{align*}
\mathcal{L} & \leftarrow \mathcal{L}(\hat x_{k},\tilde x^{k},\tilde u^{k})\\
f_{d,j} & \leftarrow f_{d}(t_{k+j},\tilde x^{k}_{j},\tilde u^{k}_{j})\\
h_{j} & \leftarrow h(t_{k+j},\tilde x^{k}_{j},\tilde u^{k}_{j})\\
L_{j} & \leftarrow L(\tilde x^{k}_{j},\tilde u^{k}_{j})\\
\end{align*}$$

---
# Derivation
**Jacobian of Lagrangian: (w.r.t. decision variables)**
$$
\nabla_{z^{k}} \mathcal{L} (\hat x_{k},\tilde x^{k},\tilde u^{k}) = \sum\limits_{j=-1}^{N-1} \nabla_{z^{k}} \mathcal{L}_{j}(s^{k}_{j},s^{k}_{j+1}) 
+ \nabla_{z^{k}}\mathcal{L}_{N}(s^{k}_{N})
$$
where
$$z^{k} \triangleq \begin{bmatrix}z^{k}_{0} \\ z^{k}_{1} \\ \vdots \\ z^{k}_{N-1} \\ \tilde x^{k}_{N}\end{bmatrix},\quad \Bigg(
z^{k}_{j} \triangleq \begin{bmatrix}\tilde x^{k}_{j}\\ \tilde u^{k}_{j}\end{bmatrix} \Bigg)$$

**Simplify:**
we can write:
$$\nabla_{z^{k}} \mathcal{L} (\hat x_{k},\tilde x^{k},\tilde u^{k}) = \begin{bmatrix} 
\nabla_{z^{k}_{0}} \mathcal{L} (\hat x_{k},\tilde x^{k},\tilde u^{k}) \\ 
\nabla_{z^{k}_{1}} \mathcal{L} (\hat x_{k},\tilde x^{k},\tilde u^{k})\\
\vdots\\
\nabla_{z^{k}_{N-1}} \mathcal{L} (\hat x_{k},\tilde x^{k},\tilde u^{k}) \\ 
\nabla_{\tilde x^{k}_{N}} \mathcal{L} (\hat x_{k},\tilde x^{k},\tilde u^{k}) 
\end{bmatrix}
$$
and since
$$\begin{gather}
\Big(\nabla_{z^{k}_i} \mathcal{L}_{j}(s^{k}_{j},s^{k}_{j+1}) = 0 \quad \forall i\not\in \{j,j+1\} \Big) \quad \forall j\in\mathbb{Z}_{-1,N-1}
\\[0.5em]
\nabla_{z^{k}_i} \mathcal{L}_{N}(s^{k}_{N}) = 0 \quad \forall i\not=N
\end{gather}$$

^separability-of-Lagrangian

we get
$$\nabla_{z^{k}} \mathcal{L} (\hat x_{k},\tilde x^{k},\tilde u^{k}) = \begin{bmatrix} 
\nabla_{z^{k}_{0}} \mathcal{L}_{-1} (s^{k}_{-1},s^{k}_{0}) + \nabla_{z^{k}_{0}} \mathcal{L}_{0} (s^{k}_{0},s^{k}_{1}) \\ 
\nabla_{z^{k}_{1}} \mathcal{L}_{0} (s^{k}_{0},s^{k}_{1}) + \nabla_{z^{k}_{1}} \mathcal{L}_{1} (s^{k}_{1},s^{k}_{2}) \\
\vdots\\
\nabla_{z^{k}_{j}} \mathcal{L}_{j-1} (s^{k}_{j-1},s^{k}_{j}) + \nabla_{z^{k}_{j}} \mathcal{L}_{j} (s^{k}_{j},s^{k}_{j+1}) \\ 
\vdots\\
\nabla_{z^{k}_{N-1}} \mathcal{L}_{N-2} (s^{k}_{N-2},s^{k}_{N-1}) + \nabla_{z^{k}_{N-1}} \mathcal{L}_{N-1} (s^{k}_{N-1},s^{k}_{N}) \\ 
\nabla_{\tilde x^{k}_{N}} \mathcal{L}_{N-1} (s^{k}_{N-1},s^{k}_{N}) +
\nabla_{\tilde x^{k}_{N}} \mathcal{L}_{N} (s^{k}_{N}) 
\end{bmatrix}$$

We split the sub-Lagrangians $\mathcal{L}_{j}$ into the dynamic terms $\mathcal{L}^{d}$, objective/cost terms $\mathcal{L}^{o}$, and feasibility terms $\mathcal{L}^{f}$, and write the Jacobian in these three terms separately:
$$\nabla_{z^{k}} \mathcal{L} (\hat x_{k},\tilde x^{k},\tilde u^{k}) = \nabla_{z^{k}} \mathcal{L}^{d} (\cdot) + \nabla_{z^{k}} \mathcal{L}^{o} (\cdot) + \nabla_{z^{k}} \mathcal{L}^{f} (\cdot)$$
where the dynamic term is:
$$
\begin{align*}
\nabla_{z^{k}} \mathcal{L}^{d} (\cdot) &  = \begin{bmatrix} 
- \nabla_{z^{k}_{0}} (\tilde x^{k}_{0} - \cancel{\hat x_{k}})\bar \lambda_{-1} - \nabla_{z^{k}_{0}}  (\cancel{\tilde x^{k}_{1}} - f_{d}(t_{k},\tilde x^{k}_{0},\tilde u^{k}_{0}))\bar \lambda_{0} \\ 
-  \nabla_{z^{k}_{1}}  (\tilde x^{k}_{1} - \cancel{f_{d}(t_{k},\tilde x^{k}_{0},\tilde u^{k}_{0})})\bar \lambda_{0} -  \nabla_{z^{k}_{1}} (\cancel{\tilde x^{k}_{2}} - f_{d}(t_{k+1},\tilde x^{k}_{1},\tilde u^{k}_{1}))\bar \lambda_{1} \\
\vdots\\
-  \nabla_{z^{k}_{j}}  (\tilde x^{k}_{j} - \cancel{f_{d}(t_{k+j-1},\tilde x^{k}_{j-1},\tilde u^{k}_{j-1})})\bar \lambda_{j-1} -  \nabla_{z^{k}_{j}} (\cancel{\tilde x^{k}_{j+1}} - f_{d}(t_{k+j},\tilde x^{k}_{j},\tilde u^{k}_{j}))\bar \lambda_{j} \\ 
\vdots\\
- \nabla_{z^{k}_{N-1}}  (\tilde x^{k}_{N-1} - \cancel{f_{d}(t_{k+N-2},\tilde x^{k}_{N-2},\tilde u^{k}_{N-2})})\bar \lambda_{N-2}  -  \nabla_{z^{k}_{N-1}} (\cancel{\tilde x^{k}_{N}} - f_{d}(t_{k+N-1},\tilde x^{k}_{N-1},\tilde u^{k}_{N-1})) \bar \lambda_{N-1}\\ 
- \nabla_{\tilde x^{k}_{N}}  (\tilde x^{k}_{N} - \cancel{f_{d}(t_{k+N-1},\tilde x^{k}_{N-1},\tilde u^{k}_{N-1})})\bar \lambda_{N-1} 
  + \nabla_{\tilde x^{k}_{N}}(- \bar{\mathcal{T}}(\tilde x^{k}_{N}))\bar \lambda_{N}
\end{bmatrix}\\[2em] 
%% 
& = \begin{bmatrix} 
- \nabla_{z^{k}_{0}} \tilde x^{k}_{0}\bar \lambda_{-1} +\nabla_{z^{k}_{0}}f_{d}(t_{k},\tilde x^{k}_{0},\tilde u^{k}_{0}) \bar \lambda_{0}\\ 
-  \nabla_{z^{k}_{1}} \tilde x^{k}_{1}\bar \lambda_{0} + \nabla_{z^{k}_{1}} f_{d}(t_{k+1},\tilde x^{k}_{1},\tilde u^{k}_{1})  \bar \lambda_{1}\\
\vdots\\
-  \nabla_{z^{k}_{j}} \tilde x^{k}_{j}\bar \lambda_{j-1} +  \nabla_{z^{k}_{j}} f_{d}(t_{k+j},\tilde x^{k}_{j},\tilde u^{k}_{j})\bar \lambda_{j} \\ 
\vdots\\
-  \nabla_{z^{k}_{N-1}} \tilde x^{k}_{N-1}\bar \lambda_{N-2} +  \nabla_{z^{k}_{N-1}}  f_{d}(t_{k+N-1},\tilde x^{k}_{N-1},\tilde u^{k}_{N-1}) \bar \lambda_{N-1}\\ 
-  \nabla_{\tilde x^{k}_{N}} \tilde x^{k}_{N}\bar \lambda_{N-1}
  -  \nabla_{\tilde x^{k}_{N}}\bar{\mathcal{T}}(\tilde x^{k}_{N})\bar \lambda_{N}
\end{bmatrix}\\[0.5em]
%%
& \qquad \text{(writing out z into [u, x])}\\[0.5em]
%%
& = \begin{bmatrix} 
- \cancel{\nabla_{\tilde x^{k}_{0}} \tilde x^{k}_{0}}\bar \lambda_{-1} + \nabla_{\tilde x^{k}_{0}}f_{d}(t_{k},\tilde x^{k}_{0},\tilde u^{k}_{0})\bar \lambda_{0} \\ 
  - \cancel{\nabla_{\tilde u^{k}_{0}} \tilde x^{k}_{0}\bar \lambda_{-1}} + \nabla_{\tilde u^{k}_{0}}f_{d}(t_{k},\tilde x^{k}_{0},\tilde u^{k}_{0})\bar \lambda_{0} \\ 
\vdots\\
- \cancel{\nabla_{\tilde x^{k}_{j}} \tilde x^{k}_{j}}\bar \lambda_{j-1}  +  \nabla_{\tilde x^{k}_{j}} f_{d}(t_{k+j},\tilde x^{k}_{j},\tilde u^{k}_{j})\bar \lambda_{j} \\ 
  - \cancel{ \nabla_{\tilde u^{k}_{j}} \tilde x^{k}_{j}\bar \lambda_{j-1}} +  \nabla_{\tilde u^{k}_{j}} f_{d}(t_{k+j},\tilde x^{k}_{j},\tilde u^{k}_{j})\bar \lambda_{j} \\ 
\vdots\\
-  \cancel{\nabla_{\tilde x^{k}_{N-1}} \tilde x^{k}_{N-1}}\bar \lambda_{N-2} +  \nabla_{\tilde x^{k}_{N-1}}  f_{d}(t_{k+N-1},\tilde x^{k}_{N-1},\tilde u^{k}_{N-1})\bar \lambda_{N-1} \\ 
  - \cancel{ \nabla_{\tilde u^{k}_{N-1}} \tilde x^{k}_{N-1}\bar \lambda_{N-2}} +  \nabla_{\tilde u^{k}_{N-1}}  f_{d}(t_{k+N-1},\tilde x^{k}_{N-1},\tilde u^{k}_{N-1})\bar \lambda_{N-1} \\ 
- \cancel{\nabla_{\tilde x^{k}_{N}} \tilde x^{k}_{N}} \bar \lambda_{N-1}
  -  \nabla_{\tilde x^{k}_{N}}\bar{\mathcal{T}}(\tilde x^{k}_{N})\bar \lambda_{N}
\end{bmatrix}\\[1em]
%%
& = \begin{bmatrix} 
- \bar \lambda_{-1} + \nabla_{\tilde x^{k}_{0}}f_{d}(t_{k},\tilde x^{k}_{0},\tilde u^{k}_{0})\bar \lambda_{0} \\ 
  \nabla_{\tilde u^{k}_{0}}f_{d}(t_{k},\tilde x^{k}_{0},\tilde u^{k}_{0})\bar \lambda_{0} \\ 
\vdots\\
- \bar \lambda_{j-1} +  \nabla_{\tilde x^{k}_{j}} f_{d}(t_{k+j},\tilde x^{k}_{j},\tilde u^{k}_{j})\bar \lambda_{j} \\ 
   \nabla_{\tilde u^{k}_{j}} f_{d}(t_{k+j},\tilde x^{k}_{j},\tilde u^{k}_{j}) \bar \lambda_{j} \\ 
\vdots\\
- \bar \lambda_{N-2} +  \nabla_{\tilde x^{k}_{N-1}}  f_{d}(t_{k+N-1},\tilde x^{k}_{N-1},\tilde u^{k}_{N-1}) \bar \lambda_{N-1}\\ 
  \nabla_{\tilde u^{k}_{N-1}}  f_{d}(t_{k+N-1},\tilde x^{k}_{N-1},\tilde u^{k}_{N-1}) \bar \lambda_{N-1} \\ 
- \bar \lambda_{N-1}
  - \nabla_{\tilde x^{k}_{N}}\bar{\mathcal{T}}(\tilde x^{k}_{N})\bar \lambda_{N} 
\end{bmatrix}
\end{align*}
$$

and the objective term is
$$
\begin{align*}
\nabla_{z^{k}} \mathcal{L}^{o} (\cdot) &  
= \begin{bmatrix} 
\nabla_{z^{k}_{0}} L(\tilde x^{k}_{0},\tilde u^{k}_{0}) \\ 
\cancel{\nabla_{z^{k}_{1}} L(\tilde x^{k}_{0},\tilde u^{k}_{0})} + \nabla_{z^{k}_{1}} L(\tilde x^{k}_{1},\tilde u^{k}_{1}) \\
\vdots\\
\cancel{\nabla_{z^{k}_{j}} L(\tilde x^{k}_{j-1},\tilde u^{k}_{j-1}) }+ \nabla_{z^{k}_{j}} L(\tilde x^{k}_{j},\tilde u^{k}_{j}) \\ 
\vdots\\
\cancel{\nabla_{z^{k}_{N-1}} L(\tilde x^{k}_{N-2},\tilde u^{k}_{N-2})} + \nabla_{z^{k}_{N-1}} L(\tilde x^{k}_{N-1},\tilde u^{k}_{N-1}) \\ 
\cancel{\nabla_{\tilde x^{k}_{N}} L(\tilde x^{k}_{N-1},\tilde u^{k}_{N-1})} +
\nabla_{\tilde x^{k}_{N}} T(\tilde x^{k}_{N}) 
\end{bmatrix}\\[1em]
&= \begin{bmatrix} 
\nabla_{z^{k}_{0}} L(\tilde x^{k}_{0},\tilde u^{k}_{0}) \\ 
\vdots\\
\nabla_{z^{k}_{j}} L(\tilde x^{k}_{j},\tilde u^{k}_{j}) \\ 
\vdots\\
\nabla_{z^{k}_{N-1}} L(\tilde x^{k}_{N-1},\tilde u^{k}_{N-1}) \\ 
\nabla_{\tilde x^{k}_{N}} T(\tilde x^{k}_{N}) 
\end{bmatrix}\\[1em]
&= \begin{bmatrix} 
\nabla_{\tilde x^{k}_{0}} L(\tilde x^{k}_{0},\tilde u^{k}_{0}) \\
\nabla_{\tilde u^{k}_{0}} L(\tilde x^{k}_{0},\tilde u^{k}_{0}) \\  
\vdots\\
\nabla_{\tilde x^{k}_{j}} L(\tilde x^{k}_{j},\tilde u^{k}_{j}) \\ 
\nabla_{\tilde u^{k}_{j}} L(\tilde x^{k}_{j},\tilde u^{k}_{j}) \\ 
\vdots\\
\nabla_{\tilde x^{k}_{N-1}} L(\tilde x^{k}_{N-1},\tilde u^{k}_{N-1}) \\
\nabla_{\tilde u^{k}_{N-1}} L(\tilde x^{k}_{N-1},\tilde u^{k}_{N-1}) \\  
\nabla_{\tilde x^{k}_{N}} T(\tilde x^{k}_{N}) 
\end{bmatrix}
\end{align*}
$$
and, similarly, we get that the feasibility term is:
$$
\begin{align*}
\nabla_{z^{k}} \mathcal{L}^{f} (\cdot) & = \begin{bmatrix} 
-\nabla_{\tilde x^{k}_{0}}  h(t_{k},\tilde x^{k}_{0},\tilde u^{k}_{0})\hat \lambda_{0} \\
-\nabla_{\tilde u^{k}_{0}}  h(t_{k},\tilde x^{k}_{0},\tilde u^{k}_{0})\hat \lambda_{0} \\
\vdots\\
-\nabla_{\tilde x^{k}_{j}}  h(t_{k+j},\tilde x^{k}_{j},\tilde u^{k}_{j})\hat \lambda_{j} \\ 
-\nabla_{\tilde u^{k}_{j}}  h(t_{k+j},\tilde x^{k}_{j},\tilde u^{k}_{j})\hat \lambda_{j} \\ 
\vdots\\
- \nabla_{\tilde x^{k}_{N-1}} h(t_{k+N-1},\tilde x^{k}_{N-1},\tilde u^{k}_{N-1})\hat \lambda_{N-1} \\ 
- \nabla_{\tilde u^{k}_{N-1}} h(t_{k+N-1},\tilde x^{k}_{N-1},\tilde u^{k}_{N-1})\hat \lambda_{N-1} \\ 
- \nabla_{\tilde x^{k}_{N}} \hat{\mathcal{T}}(\tilde x^{k}_{N})\hat \lambda_{N} 
\end{bmatrix}
\end{align*}
$$
Denoting
$$\begin{align*}
f_{d,j} & \leftarrow f_{d}(t_{k+j},\tilde x^{k}_{j},\tilde u^{k}_{j})\\
h_{j} & \leftarrow h(t_{k+j},\tilde x^{k}_{j},\tilde u^{k}_{j})\\
L_{j} & \leftarrow L(\tilde x^{k}_{j},\tilde u^{k}_{j})\\
\end{align*}$$
we can write the Jacobian as
$$
\nabla_{z^{k}} \mathcal{L} = 
\underbrace{\begin{bmatrix} 
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
+\underbrace{\begin{bmatrix} 
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
+\underbrace{\begin{bmatrix} 
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
$$
