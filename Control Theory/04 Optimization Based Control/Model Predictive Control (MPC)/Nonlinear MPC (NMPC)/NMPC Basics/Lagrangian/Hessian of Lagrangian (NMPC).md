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
In which case, the Jacobian is:
![[Jacobian of Lagrangian (NMPC)#^Jacobian-of-Lagrangian]]

---

Then the **Hessian** is:
$$\nabla^{2}_{z^{k}} \mathcal{L} 
=\begin{bmatrix} 
\nabla^{2}_{z^{k}_{0}}\mathcal{L}_{0}  \\ 
& \tiny\ddots  \\ 
&& \nabla^{2}_{z^{k}_{N-1}}\mathcal{L}_{N-1} \\ 
&&& \nabla^{2}_{\tilde x^{k}_{N}} \mathcal{T}
\end{bmatrix}
$$

^Hessian

with
$$\begin{align*}
\mathcal{L}_{j} &\triangleq L_{j} + f_{d,j}^{\top} \, \bar \lambda_{j} - h_{j}^{\top} \, \hat \lambda_{j} \\
\mathcal{T} &\triangleq T(\tilde x^{k}_{N}) - \bar{\mathcal{T}}^{\top}\small (\tilde x^{k}_{N}) \normalsize \, \bar \lambda_{N} - \hat{\mathcal{T}}^{\top}\small (\tilde x^{k}_{N}) \normalsize\, \hat \lambda_{N}
\end{align*}$$




# Sub-Hessians:
$$\begin{align*}
\nabla^{2}_{z^{k}_{j}}\mathcal{L}_{j} &\triangleq f_{j}^{\nabla} + \nabla^{2}_{z^{k}_{j}}~ L_{j} - h^{\nabla}_{j} \quad \forall j\in \mathbb{Z}_{0,N-1}\\[0.5em]
\nabla^{2}_{\tilde x^{k}_{N}} \mathcal{T} & \triangleq \nabla^{2}_{\tilde x^{k}_{N}} T(\tilde x^{k}_{N}) - \bar{\mathcal{T}}^{\nabla} - \hat{\mathcal{T}}^{\nabla}
\end{align*}$$
$$
\begin{align*}
f^{\nabla}_{j} &\triangleq \sum\limits_{i=1}^{n_{x}} \Big(\nabla^{2}_{z^{k}_{j}} f_{i,d,j}~  \bar \lambda_{i,j} \Big)\\
\bar{\mathcal{T}}^{\nabla} &\triangleq \sum\limits_{i=1}^{\bar n_{\mathcal{T}}}~\Big(\nabla^{2}_{\tilde x^{k}_{N}} \bar{\mathcal{T}}_{i}(\tilde x^{k}_{N})~ \bar\lambda_{i,N} \Big) \\
h^{\nabla}_{j} &\triangleq \sum\limits_{i=1}^{n_{h}} \Big(\nabla^{2}_{z^{k}_{j}} h_{i,j}~  \bar \lambda_{i,j} \Big)\\
\hat{\mathcal{T}}^{\nabla} &\triangleq \sum\limits_{i=1}^{\hat n_{\mathcal{T}}}~\Big(\nabla^{2}_{\tilde x^{k}_{N}} \hat{\mathcal{T}}_{i}(\tilde x^{k}_{N})~ \hat\lambda_{i,N} \Big)
\end{align*}
$$
where
$$
\begin{gather}
\begin{pmatrix}f_{d,j} = \begin{bmatrix}f_{1,d,j} \\ f_{2,d,j} \\ \vdots \\ f_{n_{x},d,j} \end{bmatrix}, \quad \bar \lambda_{j} = \begin{bmatrix}\bar \lambda_{1,j} \\ \bar \lambda_{2,j} \\ \vdots \\ \bar \lambda_{n_{x},j} \end{bmatrix} \quad \in \mathbb{R}^{n_{x}}, \qquad h_{j} = \begin{bmatrix}h_{1,j}  \\ h_{2,j}  \\ \vdots  \\ h_{n_{h},j}\end{bmatrix}, \quad \hat \lambda_{j} = \begin{bmatrix}\hat \lambda_{1,j} \\ \hat \lambda_{2,j} \\ \vdots \\ \hat \lambda_{n_{h},j} \end{bmatrix} \quad \in \mathbb{R}^{n_{h}}\end{pmatrix} \qquad \forall j\in \mathbb{Z}_{0,N-1} \\[1em]
%
\bar{\mathcal{T}} = \begin{bmatrix}\bar{\mathcal{T}}_{1} \\ \bar{\mathcal{T}}_{2} \\ \vdots \\\bar{\mathcal{T}}_{\bar n_{\mathcal{T}}}\end{bmatrix},
\quad \bar \lambda_{N} = \begin{bmatrix}\bar \lambda_{1,N} \\ \bar \lambda_{2,N} \\ \vdots \\ \bar \lambda_{\bar n_{\mathcal{T}},N} \end{bmatrix}
\quad \in \mathbb{R}^{\bar n_{\mathcal{T}}},
\qquad \hat{\mathcal{T}} = \begin{bmatrix}\hat{\mathcal{T}}_{1} \\ \hat{\mathcal{T}}_{2} \\ \vdots \\ \hat{\mathcal{T}}_{\hat n_{\mathcal{T}}}\end{bmatrix},
\quad \hat \lambda_{N} = \begin{bmatrix}\hat \lambda_{1,N} \\ \hat \lambda_{2,N} \\ \vdots \\ \hat \lambda_{\hat n_{\mathcal{T}},N} \end{bmatrix}
\quad \in \mathbb{R}^{\bar n_{\mathcal{T}}}
\end{gather}
$$
^f-h-lambda-as-subvectors


# Derivation:
We wish to find the Hessian of the Lagrangian w.r.t. the decision variables $z^{k} = \{z^{k}_{0}, \dots, z^{k}_{N}\},\quad z^{k}_{j} = [\tilde x^{k\top}_{j}, \tilde u^{k\top}_{j}]^{\top}$ *(w/ caveat on $j\in\{0,N\}$)* of an NMPC problem:
$$\nabla^{2}_{z^{k}} \mathcal{L} = \sum\limits_{j=-1}^{N-1} \nabla^{2}_{z^{k}} \mathcal{L}_{j}(s^{k}_{j},s^{k}_{j+1}) 
+ \nabla^{2}_{z^{k}}\mathcal{L}_{N}(s^{k}_{N})$$
By, again, using the [[Jacobian of Lagrangian (NMPC)#^separability-of-Lagrangian|separability]] of the Lagrangian, which allowed us to write the Jacobian in a [[Jacobian of Lagrangian (NMPC)#^Jacobian-of-Lagrangian|simplified way,]] we get that the Hessian is:

$$\nabla^{2}_{z^{k}} \mathcal{L} (\hat x_{k},\tilde x^{k},\tilde u^{k}) = \nabla^{2}_{z^{k}} \mathcal{L}^{d} (\cdot) + \nabla^{2}_{z^{k}} \mathcal{L}^{o} (\cdot) + \nabla^{2}_{z^{k}} \mathcal{L}^{f} (\cdot)$$
where *(note that the transpose of the new nabla operation of omitted for convenience)*:
## Dynamic Term
$$
\nabla^{2}_{z^{k}} \mathcal{L}^{d} = \nabla_{z^{k}} \begin{bmatrix} 
\nabla_{\tilde x^{k}_{0}}f_{d,0}\bar \lambda_{0} - \bar \lambda_{-1}\\ 
  \nabla_{\tilde u^{k}_{0}}f_{d,0} \bar \lambda_{0}\\ 
\vdots\\
 \nabla_{\tilde x^{k}_{j}} f_{d,j}\bar \lambda_{j} - \bar \lambda_{j-1}\\ 
  \nabla_{\tilde u^{k}_{j}} f_{d,j} \bar \lambda_{j}  \\ 
\vdots\\
\nabla_{\tilde x^{k}_{N-1}}  f_{d,N-1} \bar \lambda_{N-1} - \bar \lambda_{N-2}\\ 
   \nabla_{\tilde u^{k}_{N-1}}  f_{d,N-1}  \bar \lambda_{N-1}\\ 
  -  \nabla_{\tilde x^{k}_{N}}\bar{\mathcal{T}}(\tilde x^{k}_{N})\bar \lambda_{N} - \bar \lambda_{N-1}
\end{bmatrix}
 = 
\nabla_{z^{k}} \begin{bmatrix} 
\nabla_{\tilde x^{k}_{0}}f_{d,0}\bar \lambda_{0}\\ 
  \nabla_{\tilde u^{k}_{0}}f_{d,0} \bar \lambda_{0}\\ 
\vdots\\
 \nabla_{\tilde x^{k}_{j}} f_{d,j}\bar \lambda_{j}\\ 
  \nabla_{\tilde u^{k}_{j}} f_{d,j} \bar \lambda_{j}  \\ 
\vdots\\
\nabla_{\tilde x^{k}_{N-1}}  f_{d,N-1} \bar \lambda_{N-1}\\ 
   \nabla_{\tilde u^{k}_{N-1}}  f_{d,N-1}  \bar \lambda_{N-1}\\ 
  -  \nabla_{\tilde x^{k}_{N}}\bar{\mathcal{T}}(\tilde x^{k}_{N})\bar \lambda_{N}
\end{bmatrix}
$$
$$= \begin{bmatrix} 
\nabla_{z^{k}_{0}} (\nabla_{\tilde x^{k}_{0}}f_{d,0}) \bar \lambda_{0} & & \\ 
  \nabla_{z^{k}_{0}} (\nabla_{\tilde u^{k}_{0}}f_{d,0})\bar \lambda_{0} & & \\ 
& \tiny \ddots & \\
& &  \nabla_{z^{k}_{j}} (\nabla_{\tilde x^{k}_{j}} f_{d,j})\bar \lambda_{j}\\ 
   & & \nabla_{z^{k}_{j}} (\nabla_{\tilde u^{k}_{j}} f_{d,j})\bar \lambda_{j}  \\ 
& & & \tiny \ddots\\
& & & &  \nabla_{z^{k}_{N-1}} (\nabla_{\tilde x^{k}_{N-1}}  f_{d,N-1})\bar \lambda_{N-1}\\ 
   & & & & \nabla_{z^{k}_{N-1}} (\nabla_{\tilde u^{k}_{N-1}}  f_{d,N-1})\bar \lambda_{N-1}  \\ 
  & & & & & -\nabla_{z^{k}_{N}} (\nabla_{\tilde x^{k}_{N}}\bar{\mathcal{T}}(\tilde x^{k}_{N})) \bar \lambda_{N}
\end{bmatrix}$$

$$= \begin{bmatrix} 
\begin{bmatrix} \nabla_{\tilde x^{k}_{0}} (\nabla_{\tilde x^{k}_{0}}f_{d,0}\bar \lambda_{0}) & \nabla_{\tilde u^{k}_{0}} (\nabla_{\tilde x^{k}_{0}}f_{d,0}\bar \lambda_{0})\end{bmatrix} & & \\ 
  \begin{bmatrix}\nabla_{\tilde x^{k}_{0}} (\nabla_{\tilde u^{k}_{0}}f_{d,0}\bar \lambda_{0}) & \nabla_{\tilde u^{k}_{0}} (\nabla_{\tilde u^{k}_{0}}f_{d,0}\bar \lambda_{0})\end{bmatrix} & & \\ 
& \tiny \ddots & \\
& &  \begin{bmatrix}\nabla_{\tilde x^{k}_{j}} (\nabla_{\tilde x^{k}_{j}} f_{d,j}\bar \lambda_{j}) & \nabla_{\tilde u^{k}_{j}} (\nabla_{\tilde x^{k}_{j}} f_{d,j}\bar \lambda_{j})\end{bmatrix}\\ 
   & &  \begin{bmatrix}\nabla_{\tilde x^{k}_{j}} (\nabla_{\tilde u^{k}_{j}} f_{d,j}\bar \lambda_{j} ) & \nabla_{\tilde u^{k}_{j}} (\nabla_{\tilde u^{k}_{j}} f_{d,j}\bar \lambda_{j} )\end{bmatrix} \\ 
& & & \tiny \ddots\\
& & & &  \begin{bmatrix}\nabla_{\tilde x^{k}_{N-1}} (\nabla_{\tilde x^{k}_{N-1}}  f_{d,N-1}\bar \lambda_{N-1}) & \nabla_{\tilde u^{k}_{N-1}} (\nabla_{\tilde x^{k}_{N-1}}  f_{d,N-1}\bar \lambda_{N-1})\end{bmatrix}\\ 
   & & & & \begin{bmatrix}\nabla_{\tilde x^{k}_{N-1}} (\nabla_{\tilde u^{k}_{N-1}}  f_{d,N-1}\bar \lambda_{N-1} )  & \nabla_{\tilde u^{k}_{N-1}} (\nabla_{\tilde u^{k}_{N-1}}  f_{d,N-1}\bar \lambda_{N-1} ) \end{bmatrix} \\ 
  & & & & & - \nabla_{\tilde x^{k}_{N}} (\nabla_{\tilde x^{k}_{N}}\bar{\mathcal{T}}(\tilde x^{k}_{N})\bar \lambda_{N})
\end{bmatrix}$$
In order to proceed, we now rewrite the Jacobian as the sum of gradients:
$$
\begin{gather}
\nabla_{\tilde x^{k}_{j}} ~ f_{d,j} \cdot \bar \lambda_{j} = \sum\limits_{i=1}^{n_{x}} ~ \nabla_{\tilde x^{k}_{j}} f_{i,d,j} \cdot \bar\lambda_{i,j}
\\[0.5em]
\nabla_{\tilde u^{k}_{j}} ~ f_{d,j} \cdot \bar \lambda_{j} = \sum\limits_{i=1}^{n_{x}} ~ \nabla_{\tilde u^{k}_{j}} f_{i,d,j} \cdot \bar\lambda_{i,j}
\\[0.5em]
\nabla_{\tilde x^{k}_{N}} ~ \bar{\mathcal{T}}(\tilde x^{k}_{N}) \cdot \bar \lambda_{N} = \sum\limits_{i=1}^{\bar n_{\mathcal{T}}} ~ \nabla_{\tilde x^{k}_{N}} \bar{\mathcal{T}}_{i}(\tilde x^{k}_{N}) \cdot \bar\lambda_{i,N}
\end{gather}
$$
where
$$
f_{d,j} = \begin{bmatrix}f_{1,d,j} \\ f_{2,d,j} \\ \vdots \\ f_{n_{x},d,j} \end{bmatrix}, \quad \bar \lambda_{j} = \begin{bmatrix}\bar \lambda_{1,j} \\ \bar \lambda_{2,j} \\ \vdots \\ \bar \lambda_{n_{x},j} \end{bmatrix}, \quad \forall j\in \mathbb{Z}_{0,N-1}, \qquad \bar{\mathcal{T}} = \begin{bmatrix}\bar{\mathcal{T}}_{1} \\ \bar{\mathcal{T}}_{2} \\ \vdots \\\bar{\mathcal{T}}_{\bar n_{\mathcal{T}}}\end{bmatrix}, \quad \bar \lambda_{N} = \begin{bmatrix}\bar \lambda_{1,N} \\ \bar \lambda_{2,N} \\ \vdots \\ \bar \lambda_{\bar n_{\mathcal{T}},N} \end{bmatrix}
$$
We can then write the sub-Hessians as
$$
\begin{gather}
\nabla_{\tilde x^{k}_{j}} (\nabla_{\tilde x^{k}_{j}} ~ f_{d,j} \cdot \bar \lambda_{j}) = \nabla_{\tilde x^{k}_{j}}\begin{pmatrix}\sum\limits_{i=1}^{n_{x}} ~ \nabla_{\tilde x^{k}_{j}} f_{i,d,j} \cdot \bar\lambda_{i,j}\end{pmatrix}= \sum\limits_{i=1}^{n_{x}} ~ \nabla_{\tilde x^{k}_{j}}\begin{pmatrix}\nabla_{\tilde x^{k}_{j}} f_{i,d,j} \cdot \bar\lambda_{i,j}\end{pmatrix} = \sum\limits_{i=1}^{n_{x}} ~ \nabla_{\tilde x^{k}_{j}}\begin{pmatrix}\nabla_{\tilde x^{k}_{j}} f_{i,d,j}\end{pmatrix} \cdot \bar\lambda_{i,j} = \sum\limits_{i=1}^{n_{x}} ~ \nabla^{2}_{\tilde x^{k}_{j}} f_{i,d,j}\cdot \bar\lambda_{i,j}
\\[1em]
\nabla_{\tilde u^{k}_{j}} (\nabla_{\tilde u^{k}_{j}} ~ f_{d,j} \cdot \bar \lambda_{j}) = \nabla_{\tilde u^{k}_{j}}\begin{pmatrix}\sum\limits_{i=1}^{n_{x}} ~ \nabla_{\tilde u^{k}_{j}} f_{i,d,j} \cdot \bar\lambda_{i,j}\end{pmatrix}= \sum\limits_{i=1}^{n_{x}} ~ \nabla_{\tilde u^{k}_{j}}\begin{pmatrix}\nabla_{\tilde u^{k}_{j}} f_{i,d,j} \cdot \bar\lambda_{i,j}\end{pmatrix} = \sum\limits_{i=1}^{n_{x}} ~ \nabla_{\tilde u^{k}_{j}}\begin{pmatrix}\nabla_{\tilde u^{k}_{j}} f_{i,d,j}\end{pmatrix} \cdot \bar\lambda_{i,j} = \sum\limits_{i=1}^{n_{x}} ~ \nabla^{2}_{\tilde u^{k}_{j}} f_{i,d,j}\cdot \bar\lambda_{i,j}
\\[1em]
\nabla_{\tilde x^{k}_{j}} (\nabla_{\tilde u^{k}_{j}} ~ f_{d,j} \cdot \bar \lambda_{j}) = \nabla_{\tilde x^{k}_{j}}\begin{pmatrix}\sum\limits_{i=1}^{n_{x}} ~ \nabla_{\tilde u^{k}_{j}} f_{i,d,j} \cdot \bar\lambda_{i,j}\end{pmatrix}= \sum\limits_{i=1}^{n_{x}} ~ \nabla_{\tilde x^{k}_{j}}\begin{pmatrix}\nabla_{\tilde u^{k}_{j}} f_{i,d,j} \cdot \bar\lambda_{i,j}\end{pmatrix} = \sum\limits_{i=1}^{n_{x}} ~ \nabla_{\tilde x^{k}_{j}}\begin{pmatrix}\nabla_{\tilde u^{k}_{j}} f_{i,d,j}\end{pmatrix} \cdot \bar\lambda_{i,j} = \sum\limits_{i=1}^{n_{x}} ~ \nabla^{2}_{\tilde x^{k}_{j},\,\tilde u^{k}_{j}} ~f_{i,d,j}\cdot \bar\lambda_{i,j}
\\[1em]
\nabla_{\tilde u^{k}_{j}} (\nabla_{\tilde x^{k}_{j}} ~ f_{d,j} \cdot \bar \lambda_{j}) = \nabla_{\tilde u^{k}_{j}}\begin{pmatrix}\sum\limits_{i=1}^{n_{x}} ~ \nabla_{\tilde x^{k}_{j}} f_{i,d,j} \cdot \bar\lambda_{i,j}\end{pmatrix}= \sum\limits_{i=1}^{n_{x}} ~ \nabla_{\tilde u^{k}_{j}}\begin{pmatrix}\nabla_{\tilde x^{k}_{j}} f_{i,d,j} \cdot \bar\lambda_{i,j}\end{pmatrix} = \sum\limits_{i=1}^{n_{x}} ~ \nabla_{\tilde u^{k}_{j}}\begin{pmatrix}\nabla_{\tilde x^{k}_{j}} f_{i,d,j}\end{pmatrix} \cdot \bar\lambda_{i,j} = \sum\limits_{i=1}^{n_{x}} ~ \nabla^{2}_{\tilde x^{k}_{j},\,\tilde u^{k}_{j}} ~f_{i,d,j}\cdot \bar\lambda_{i,j}
\\[1em]
\nabla_{\tilde x^{k}_{N}} \Big(\nabla_{\tilde x^{k}_{N}} ~ \bar{\mathcal{T}}(\tilde x^{k}_{N}) \cdot \bar \lambda_{N}\Big) = \nabla_{\tilde x^{k}_{N}}\begin{pmatrix}\sum\limits_{i=1}^{\bar n_{\mathcal{T}}} ~ \nabla_{\tilde x^{k}_{N}} \bar{\mathcal{T}}_{i}(\tilde x^{k}_{N}) \cdot \bar\lambda_{i,N}\end{pmatrix} = \sum\limits_{i=1}^{\bar n_{\mathcal{T}}}~\nabla_{\tilde x^{k}_{N}}\begin{pmatrix}\nabla_{\tilde x^{k}_{N}} \bar{\mathcal{T}}_{i}(\tilde x^{k}_{N}) \cdot \bar\lambda_{i,N}\end{pmatrix} = \sum\limits_{i=1}^{\bar n_{\mathcal{T}}}~\nabla^{2}_{\tilde x^{k}_{N}} \bar{\mathcal{T}}_{i}(\tilde x^{k}_{N}) \cdot \bar\lambda_{i,N}
\end{gather}$$
And the Hessian can therefore be written as:

$$= \begin{bmatrix} 
\sum\limits_{i=1}^{n_{x}}
\begin{bmatrix}  \nabla^{2}_{\tilde x^{k}_{0}}f_{i,d,0} & \nabla^{2}_{\tilde x^{k}_{0},\,\tilde u^{k}_{0}}\, f_{i,d,0} \\[0.5em] \nabla^{2}_{\tilde x^{k}_{0},\,\tilde u^{k}_{0}}\,f_{i,d,0} & \nabla^{2}_{\tilde u^{k}_{0}}f_{i,d,0}\end{bmatrix}\bar \lambda_{i,0} & & \\
& \tiny \ddots & \\
& &  \sum\limits_{i=1}^{n_{x}}
\begin{bmatrix}  \nabla^{2}_{\tilde x^{k}_{j}}f_{i,d,j} & \nabla^{2}_{\tilde x^{k}_{j},\,\tilde u^{k}_{j}}\, f_{i,d,j} \\[0.5em] \nabla^{2}_{\tilde x^{k}_{j},\,\tilde u^{k}_{j}}\,f_{i,d,j} & \nabla^{2}_{\tilde u^{k}_{j}}f_{i,d,j}\end{bmatrix}\bar \lambda_{i,j} & & \\
& & & \tiny \ddots\\
& & & & \sum\limits_{i=1}^{n_{x}}
\begin{bmatrix}  \nabla^{2}_{\tilde x^{k}_{N-1}}f_{i,d,N-1} & \nabla^{2}_{\tilde x^{k}_{N-1},\,\tilde u^{k}_{N-1}}\, f_{i,d,N-1} \\[0.5em] \nabla^{2}_{\tilde x^{k}_{N-1},\,\tilde u^{k}_{N-1}}\,f_{i,d,N-1} & \nabla^{2}_{\tilde u^{k}_{N-1}}f_{i,d,N-1}\end{bmatrix}\bar \lambda_{i,N-1}\\[0.8em]
  & & & & & -  \sum\limits_{i=1}^{\bar n_{\mathcal{T}}}~\nabla^{2}_{\tilde x^{k}_{N}} \bar{\mathcal{T}}_{i}(\tilde x^{k}_{N})~ \bar\lambda_{i,N}
\end{bmatrix}$$
Conveniently we can go back to using $z^{k}_{j} = \begin{bmatrix}\tilde x^{k\top}_{0},\, & \tilde u^{k\top}_{0}\end{bmatrix} \forall j\in \mathbb{Z}_{0,N-1}$ and $z^{k}_{N} = \tilde x^{k}_{N}$, to get:
$$= \begin{bmatrix} 
\sum\limits_{i=1}^{n_{x}}
\nabla^{2}_{z^{k}_{0}} f_{i,d,0}~ \bar \lambda_{i,0} & & \\
& \tiny \ddots & \\
& &  \sum\limits_{i=1}^{n_{x}}
\nabla^{2}_{z^{k}_{j}} f_{i,d,j}~  \bar \lambda_{i,j} & & \\
& & & \tiny \ddots\\
& & & & \sum\limits_{i=1}^{n_{x}}
\nabla^{2}_{z^{k}_{N-1}} f_{i,d,N-1}~\bar \lambda_{i,N-1}\\[0.8em]
  & & & & & -  \sum\limits_{i=1}^{\bar n_{\mathcal{T}}}~\nabla^{2}_{\tilde x^{k}_{N}} \bar{\mathcal{T}}_{i}(\tilde x^{k}_{N})~ \bar\lambda_{i,N}
\end{bmatrix}$$
By then defining
$$
\begin{align*}
f^{\nabla}_{j} &\triangleq \sum\limits_{i=1}^{n_{x}} \Big(\nabla^{2}_{z^{k}_{j}} f_{i,d,j}~  \bar \lambda_{i,j} \Big) = \nabla^{2}_{z^{k}_{j}} (f_{d,j}^{\top} \,\bar \lambda_{j})\\
\bar{\mathcal{T}}^{\nabla} &\triangleq \sum\limits_{i=1}^{\bar n_{\mathcal{T}}}~\Big(\nabla^{2}_{\tilde x^{k}_{N}} \bar{\mathcal{T}}_{i}(\tilde x^{k}_{N})~ \bar\lambda_{i,N} \Big) = \nabla^{2}_{z^{k}_{j}} (\bar{\mathcal{T}}^{\top}\small(\tilde x^{k}_{N}) \normalsize \,\bar \lambda_{N}) 
\end{align*}
$$
to get a simpler notation:
$$=\begin{bmatrix} 
f^{\nabla}_{0}  \\ 
& \tiny\ddots  \\ 
&& f^{\nabla}_{N-1} \\ 
&&& -\bar{\mathcal{T}}^{\nabla}
\end{bmatrix}$$


## Objective Term
$$
\nabla^{2}_{z^{k}} \mathcal{L}^{o} = \nabla_{z^{k}}
\begin{bmatrix} 
\nabla_{z^{k}_{0}} L_{0} \\ 
\vdots\\
\nabla_{z^{k}_{j}} L_{j} \\ 
\vdots\\
\nabla_{z^{k}_{N-1}} L_{N-1} \\ 
\nabla_{\tilde x^{k}_{N}} T(\tilde x^{k}_{N}) 
\end{bmatrix}
$$
$$
=
\begin{bmatrix} 
\nabla^{2}_{z^{k}_{0}} L_{0} \\ 
& \tiny\ddots\\
&&\nabla^{2}_{z^{k}_{N-1}} L_{N-1} \\[0.5em]
&&&\nabla^{2}_{\tilde x^{k}_{N}} T(\tilde x^{k}_{N}) 
\end{bmatrix}
$$

## Feasibility Term
We have
$$
\nabla^{2}_{z^{k}} \mathcal{L}^{d} = \nabla_{z^{k}} \begin{bmatrix} 
-\nabla_{\tilde x^{k}_{0}}  h_{0}\hat \lambda_{0} \\
-\nabla_{\tilde u^{k}_{0}}  h_{0}\hat \lambda_{0} \\
\vdots\\
-\nabla_{\tilde x^{k}_{j}}  h_{j} \hat \lambda_{j}\\ 
-\nabla_{\tilde u^{k}_{j}}  h_{j}\hat \lambda_{j} \\ 
\vdots\\
- \nabla_{\tilde x^{k}_{N-1}} h_{N-1}\hat \lambda_{N-1} \\ 
- \nabla_{\tilde u^{k}_{N-1}} h_{N-1}\hat \lambda_{N-1} \\ 
-\nabla_{\tilde x^{k}_{N}} \hat{\mathcal{T}}(\tilde x^{k}_{N}) \hat \lambda_{N} 
\end{bmatrix}
 = 
- \nabla_{z^{k}} \begin{bmatrix} 
\nabla_{\tilde x^{k}_{0}}  h_{0}\hat \lambda_{0} \\
\nabla_{\tilde u^{k}_{0}}  h_{0}\hat \lambda_{0} \\
\vdots\\
\nabla_{\tilde x^{k}_{j}}  h_{j} \hat \lambda_{j}\\ 
\nabla_{\tilde u^{k}_{j}}  h_{j}\hat \lambda_{j} \\ 
\vdots\\
 \nabla_{\tilde x^{k}_{N-1}} h_{N-1}\hat \lambda_{N-1} \\ 
 \nabla_{\tilde u^{k}_{N-1}} h_{N-1}\hat \lambda_{N-1} \\ 
\nabla_{\tilde x^{k}_{N}} \hat{\mathcal{T}}(\tilde x^{k}_{N}) \hat \lambda_{N} 
\end{bmatrix}
$$
and notice that the structure is exactly the same as for the dynamic term, thus we can simply copy the result, with $f_{d,j} \rightarrow h_{j}$ , $\bar \lambda \rightarrow\hat \lambda$, and $\bar{\mathcal{T}} \rightarrow \hat{\mathcal{T}}$, to get:
$$= ~~-\begin{bmatrix} 
h^{\nabla}_{0}  \\ 
& \tiny\ddots  \\ 
&& h^{\nabla}_{N-1} \\ 
&&& \hat{\mathcal{T}}^{\nabla}
\end{bmatrix}$$
Where
$$
\begin{align*}
h^{\nabla}_{j} &\triangleq \sum\limits_{i=1}^{n_{h}} \Big(\nabla^{2}_{z^{k}_{j}} h_{i,j}~  \hat \lambda_{i,j} \Big) = \nabla^{2}_{z^{k}_{j}} (h_{j}^{\top} \,\hat \lambda_{j})\\
\hat{\mathcal{T}}^{\nabla} &\triangleq \sum\limits_{i=1}^{\hat n_{\mathcal{T}}}~\Big(\nabla^{2}_{\tilde x^{k}_{N}} \hat{\mathcal{T}}_{i}(\tilde x^{k}_{N})~ \hat\lambda_{i,N} \Big) = \nabla^{2}_{z^{k}_{j}} (\hat{\mathcal{T}}^{\top}\small(\tilde x^{k}_{N}) \normalsize \,\hat \lambda_{N}) 
\end{align*}
$$
and 
$$h_{j} = \begin{bmatrix}h_{1,j}  \\ h_{2,j}  \\ \vdots  \\ h_{n_{h},j}\end{bmatrix} \in \mathbb{R}^{n_{h}}$$
## combine
Thus we can write:
$$
\nabla^{2}_{z^{k}} \mathcal{L}
=
\begin{bmatrix} 
f^{\nabla}_{0}  \\ 
& \tiny\ddots  \\ 
&& f^{\nabla}_{N-1} \\ 
&&& -\bar{\mathcal{T}}^{\nabla}
\end{bmatrix}
+\begin{bmatrix} 
\nabla^{2}_{z^{k}_{0}} L_{0} \\ 
& \tiny\ddots\\
&&\nabla^{2}_{z^{k}_{N-1}} L_{N-1} \\[0.5em]
&&&\nabla^{2}_{\tilde x^{k}_{N}} T(\tilde x^{k}_{N}) 
\end{bmatrix}
-\begin{bmatrix} 
h^{\nabla}_{0}  \\ 
& \tiny\ddots  \\ 
&& h^{\nabla}_{N-1} \\ 
&&& \hat{\mathcal{T}}^{\nabla}
\end{bmatrix}$$
Furthermore, we define
$$
\begin{align*}
\mathcal{L}_{j} &\triangleq L_{j} + f_{d,j}^{\top} \, \bar \lambda_{j} - h_{j}^{\top} \, \hat \lambda_{j} \\
\mathcal{T} &\triangleq T(\tilde x^{k}_{N}) - \bar{\mathcal{T}}^{\top}\tiny (\tilde x^{k}_{N}) \normalsize \, \bar \lambda_{N} - \hat{\mathcal{T}}^{\top}\tiny (\tilde x^{k}_{N}) \normalsize\, \hat \lambda_{N}
\end{align*}
$$
to get
$$\nabla^{2}_{z^{k}_{j}} \mathcal{L}_{j} \triangleq f_{j}^{\nabla} + \nabla^{2}_{z^{k}_{j}}~ L_{j} - h^{\nabla}_{j} \quad \forall j\in \mathbb{Z}_{0,N-1}$$
$$ \nabla^{2}_{\tilde x^{k}_{N}}\mathcal{T} \triangleq \nabla^{2}_{\tilde x^{k}_{N}} T(\tilde x^{k}_{N}) - \bar{\mathcal{T}}^{\nabla} - \hat{\mathcal{T}}^{\nabla}$$
So that, lastly, we can write
$$\nabla^{2}_{z^{k}} \mathcal{L}
=
\begin{bmatrix} 
\nabla^{2}_{z^{k}_{0}}\mathcal{L}_{0}  \\ 
& \tiny\ddots  \\ 
&& \nabla^{2}_{z^{k}_{N-1}}\mathcal{L}_{N-1} \\ 
&&& \nabla^{2}_{\tilde x^{k}_{N}} \mathcal{T}
\end{bmatrix}
$$
