---
tags:
  - Unfinished
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By: 
Relevant Papers:
---
This page extends the sensitivity analysis in [[Sensitivity on Initial Condition]].

**Initial Value Sensitivity:**
![[Sensitivity on Initial Condition#^sensitivity-on-initial-condition]]

We have
![[Sensitivity on Initial Condition#^def-z-lam]]
![[Sensitivity on Initial Condition#^solution-to-NLP]]


To analyze further, we define the following notation:
$$
\begin{align*}
\psi^{x}_{j} &\leftarrow \frac{d}{d\hat x^{k}} \bigg(\tilde x^{k,*}_{j}(\hat x_{k}) \bigg) \quad \forall j\in \mathbb{Z}_{0,N}\\
\psi^{u}_{j} &\leftarrow \frac{d}{d\hat x^{k}} \bigg(\tilde u^{k,*}_{j}(\hat x_{k}) \bigg) \quad \forall j\in \mathbb{Z}_{0,N-1}\\
\xi^{g}_{j} &\leftarrow \frac{d}{d\hat x^{k}} \bigg(\bar \lambda^{*}_{j}(\hat x_{k}) \bigg) \quad \forall j\in \mathbb{Z}_{-1,N}\\
\xi^{h}_{j} &\leftarrow \frac{d}{d\hat x^{k}} \bigg(\hat \lambda^{*}_{j}(\hat x_{k}) \bigg) \quad \forall j\in \mathbb{Z}_{0,N}
\end{align*}
$$
Lets also define
$$\begin{align*}
\psi^{x} &\triangleq \{\psi^{x}_{0},\psi^{x}_{1},\dots,\psi^{x}_{N-1},\psi^{x}_{N}\}\\
\psi^{u} &\triangleq \{\psi^{u}_{0},\psi^{u}_{1},\dots,\psi^{u}_{N-1}\}
\end{align*}$$
we then have
$$
\frac{d s^{*}(\hat x_{k})}{d \hat x_{k}} 
= \begin{bmatrix}
\begin{bmatrix}\psi^{x}_{0}  \\  \psi^{u}_{0} \\ \vdots  \\ \psi^{x}_{N-1}  \\  \psi^{u}_{N-1} \\ \psi^{x}_{N}\end{bmatrix} \\ 
\begin{bmatrix}\xi^{g}_{-1} \\ \xi^{g}_{0}  \\ \vdots  \\ \xi^{g}_{N} \end{bmatrix} \\ 
\begin{bmatrix}\xi^{h}_{0}  \\ \vdots  \\ \xi^{h}_{N} \end{bmatrix}
\end{bmatrix}
$$
# Top Expression
The System 
![[Sensitivity on Initial Condition#^sensitivity-on-initial-condition]]
can be partially solved. 
The top line is:
$$
-\nabla_{z^{k}}g^{\top}(z^{k,*})
~\cdot~ 
\frac{dz^{k}(\hat x_{k})}{d\hat x^{k}}
= \begin{bmatrix}-\mathbb{1}_{n_{x}}  \\  0  \\ \vdots \\ 0\end{bmatrix}
$$
Which amounts to *(see [[Jacobian - Equality Constraints]])*
$$
\underbrace{\begin{bmatrix}
I &  &  & \\[0.5em]
-A^{k}_{0} &
-B^{k}_{0} & I &  &  & \\[0.5em]
& 
&-A^{k}_{1} &
-B^{k}_{1}
&I & &  \\[0.5em]
 &  & 
&&-A^{k}_{2} &
-B^{k}_{2}
& I &  \\[0.5em]
&&&&&& \tiny\ddots \\
&&&&&&& I\\
&&&&&&&-A^{k}_{N-1} &
-B^{k}_{N-1}
&I &\\[0.5em]
&&&&&&&&&\frac{\partial}{\partial \tilde x^{k}_{N}} ( \bar{\mathcal{T}}(\tilde x^{k}_{N}))
\end{bmatrix}}_{\text{dim} ~=~ (n_{x}N+\bar n_{\mathcal{T}}) \times (n_{x}(N+1)+n_{u}N)}
~\cdot~ 
\begin{bmatrix}
\psi^{x}_{0} \\
\psi^{u}_{0} \\
\psi^{x}_{1} \\
\psi^{u}_{1} \\
\vdots  \\
\psi^{x}_{N-1} \\
\psi^{u}_{N-1} \\
\psi^{x}_{N}
\end{bmatrix}
 = \begin{bmatrix} ~\mathbb{1}_{n_{x}}  \\  0  \\ \vdots \\ 0 \end{bmatrix}
$$
the first line of which gives:
$$\psi^{x}_{0} = \mathbb{1}_{n_{x}}$$
The following lines then give:
$$
\psi^{x}_{j+1} = A^{k}_{j} \cdot \psi^{x}_{j} + B^{k}_{j} \cdot \psi^{u}_{j} \qquad\forall j\in \mathbb{Z}_{0,N-1}
$$
which is a linear discrete dynamical system, defining a map;
$$(\psi^{x}_{0},\psi^{u}) \mapsto \psi^{x} $$
The final line is
$$\frac{\partial}{\partial \tilde x^{k}_{N}} ( \bar{\mathcal{T}}(\tilde x^{k}_{N})) \cdot\psi^{x}_{N} = \mathbb{0}_{\bar n_{\mathcal{T}}} $$
Wee see that if $\bar n_{\mathcal{T}} = n_{x}$, and $\frac{\partial}{\partial \tilde x^{k}_{N}} ( \bar{\mathcal{T}}(\tilde x^{k}_{N})) \in \mathbb{R}^{\bar n_{\mathcal{T}} \times n_{x}}$ is full rank, then $\psi^{x}_{N} = 0$.
In conclusion, we essentially have a [[Boundary Value Problem (BVP)|boundary value problem]]:
$$
\begin{align*}
\psi^{x}_{0} &= I_{n_{x}\times n_{x}} \\[1em]
\psi^{x}_{j+1} &= A^{k}_{j} \cdot \psi^{x}_{j} + B^{k}_{j} \cdot \psi^{u}_{j} \qquad\forall j\in \mathbb{Z}_{0,N-1}\\[1em]
\frac{\partial}{\partial \tilde x^{k}_{N}} ( &\bar{\mathcal{T}}(\tilde x^{k}_{N})) \cdot\psi^{x}_{N} = 0 ~~\in \mathbb{R}^{\bar n_{\mathcal{T}}}
\end{align*}
$$
Note that without the terminal constraint, this is the same as algorithmic differentiation / variational approach to sensitivity on initial condition. The control signal for this system is the rate of change to the control signals. We must choose these changes to the control trajectory such that the resulting changes to the state trajectory satisfies the remaining equations.
# Bottom Expression
**Note: This analysis is only for the constraints which are active !**
In addition to satisfying the above, the remaining lines of the sensitivity must be satisfied:
$$-\nabla_{z^{k}}h_{\mathbb{A}}^{\top}(z^{k,*}) \cdot \begin{bmatrix}\psi^{x}_{0}  \\  \psi^{u}_{0} \\ \vdots  \\ \psi^{x}_{N-1}  \\  \psi^{u}_{N-1} \\ \psi^{x}_{N}\end{bmatrix} = 0$$which amounts to
$$
-\begin{bmatrix}
C^{k}_{0} & D^{k}_{0}  \\[0.5em]
&& C^{k}_{1} & D^{k}_{1}   \\[0.5em]
&&&& \tiny\ddots \\
&&&&& C^{k}_{N-2} & D^{k}_{N-2}  \\[0.5em]
&&&&&&& C^{k}_{N-1} & D^{k}_{N-1} \\[0.5em]
&&&&&&&&&\frac{\partial}{\partial \tilde x^{k}_{N}} ( \hat{\mathcal{T}}(\tilde x^{k}_{N}))
\end{bmatrix}
\cdot
\begin{bmatrix}\psi^{x}_{0}  \\  \psi^{u}_{0} \\ \vdots  \\ \psi^{x}_{N-1}  \\  \psi^{u}_{N-1} \\ \psi^{x}_{N}\end{bmatrix} = 0
$$
Yielding
$$
\begin{gather}
C^{k}_{j} \psi^{x}_{j} + D^{k}_{j} \psi^{u}_{j} = 0 \quad \forall j\in \mathbb{Z}_{0,N-1} \\[1em]
\frac{\partial}{\partial \tilde x^{k}_{N}} ( \hat{\mathcal{T}}(\tilde x^{k}_{N})) \cdot \psi^{x}_{N} = 0  ~~\in \mathbb{R}^{\hat n_{\mathcal{T}}}
\end{gather}
$$
**Note:**
- The active inequality constraints may over-define the sensitivities, making the perturbed problem infeasible w.r.t. the active set. This likely implies that the new problem has a different active set.
	- The dynamic-expression above is of dimension: $\quad \dim(\nabla_{z^{k}} g^{\top}) = (n_{x}N+\bar n_{\mathcal{T}}) \times (n_{x}(N+1)+n_{u}N)$
	- and the active inequality system is: $\quad \dim(\nabla_{z^{k}}h^{\top}) = (n_{h}N+\hat n_{\mathcal{T}})\times(n_{x}(N+1)+n_{u}N)$
- Notice that this expression is essentially saying that the change of the optimal point must be perpendicular to the gradient of the constraint function.
	- That is, the change in the solution must be along the zero (active) line of the constraint-function.
	- This is the same as saying that the active set must also be satisfied at the new solution ! which is exactly what we want !
	- It becomes clear by realizing that we are taking the inner product of the two vectors:
$$\begin{bmatrix}C^{k}_{j} & D^{k}_{j}\end{bmatrix}\cdot \begin{bmatrix}\psi^{x}_{j}  \\ \psi^{u}_{j}\end{bmatrix} = 0 \quad \text{same as:} \quad \nabla_{z^{k}_{j}} h_{j}^{\top} \cdot \nabla_{\hat x_{k}} z^{k}_{j} = 0$$ 

# Middle Expression
The middle expression is:
$$\begin{bmatrix}\nabla_{z^{k}}^{2}\mathcal{L}(z^{k,*},\lambda^{*}) & -\nabla_{z^{k}}g(z^{k,*}) & -\nabla_{z^{k}}h_{\mathbb{A}}(z^{k,*}) \end{bmatrix} 
\cdot
\begin{bmatrix}
\begin{bmatrix}\psi^{x}_{0}  \\  \psi^{u}_{0} \\ \vdots  \\ \psi^{x}_{N-1}  \\  \psi^{u}_{N-1} \\ \psi^{x}_{N}\end{bmatrix} \\ 
\begin{bmatrix}\xi^{g}_{-1} \\ \xi^{g}_{0}  \\ \vdots  \\ \xi^{g}_{N} \end{bmatrix} \\ 
\begin{bmatrix}\xi^{h}_{0}  \\ \vdots  \\ \xi^{h}_{N} \end{bmatrix}
\end{bmatrix}
= 0
$$
where
![[Hessian of Lagrangian (NMPC)#^Hessian]]
$$-\nabla_{z^{k}}g(z^{k,*})
=
-\begin{bmatrix}
I & -A^{k\top}_{0}  &  & \\[0.5em]
&
-B^{k\top}_{0} &  &  & \\[0.5em]
& I & -A^{k\top}_{1} \\[0.5em]
&& -B^{k\top}_{1}  \\[0.5em]
&& I & -A^{k\top}_{2} \\[0.5em]
&&&-B^{k\top}_{2} \\[0.5em]
&&& I \\[0.5em]
&&&& \tiny\ddots \\
&&&&& -A^{k\top}_{N-1}  \\[0.5em]
&&&&& -B^{k\top}_{N-1}  \\[0.5em]
&&&&&  I & \nabla_{\tilde x^{k}_{N}}\bar{\mathcal{T}}(\tilde x^{k}_{N})
\end{bmatrix}$$
$$-\nabla_{z^{k}}h_{h}(z^{k,*}) = 
\begin{bmatrix}
-C^{k\top}_{0}  &  & \\[0.5em]
-D^{k\top}_{0} &  &  & \\[0.5em]
& -C^{k\top}_{1} \\[0.5em]
& -D^{k\top}_{1}  \\[0.5em]
&& -C^{k\top}_{2} \\[0.5em]
&& -D^{k\top}_{2} \\[0.5em]
&& \\[0.5em]
&&& \tiny\ddots \\
&&&& -C^{k\top}_{N-1}  \\[0.5em]
&&&& -D^{k\top}_{N-1}  \\[0.5em]
&&&&& \nabla_{\tilde x^{k}_{N}}\hat{\mathcal{T}}(\tilde x^{k}_{N})
\end{bmatrix}$$
Thus we have
$$\begin{bmatrix} 
\nabla^{2}_{z^{k}_{0}}\mathcal{L}_{0}  \\ 
& \tiny\ddots  \\ 
&& \nabla^{2}_{z^{k}_{N-1}}\mathcal{L}_{N-1} \\ 
&&& \nabla^{2}_{\tilde x^{k}_{N}} \mathcal{T}
\end{bmatrix}\cdot
\begin{bmatrix}\psi^{x}_{0}  \\  \psi^{u}_{0} \\ \vdots  \\ \psi^{x}_{N-1}  \\  \psi^{u}_{N-1} \\ \psi^{x}_{N}\end{bmatrix}
-
\begin{bmatrix}
I & -A^{k\top}_{0}  &  & \\[0.5em]
&
-B^{k\top}_{0} &  &  & \\[0.5em]
& I  \\[0.5em]
&& \tiny\ddots \\
&&& -A^{k\top}_{N-1}  \\[0.5em]
&&& -B^{k\top}_{N-1}  \\[0.5em]
&&&  I & \nabla_{\tilde x^{k}_{N}}\bar{\mathcal{T}}(\tilde x^{k}_{N})
\end{bmatrix}\cdot
\begin{bmatrix}\xi^{g}_{-1} \\ \xi^{g}_{0}  \\ \vdots  \\ \xi^{g}_{N} \end{bmatrix}
-
\begin{bmatrix}
C^{k\top}_{0}  &  & \\[0.5em]
D^{k\top}_{0} &  &  & \\[0.5em]
& \tiny\ddots \\
&& C^{k\top}_{N-1}  \\[0.5em]
&& D^{k\top}_{N-1}  \\[0.5em]
&&& -\nabla_{\tilde x^{k}_{N}}\hat{\mathcal{T}}(\tilde x^{k}_{N})
\end{bmatrix}\cdot
\begin{bmatrix}\xi^{h}_{0}  \\ \vdots  \\ \xi^{h}_{N} \end{bmatrix}
 = 0
$$
which amounts to 
$$
\begin{gather}
\nabla^{2}_{z^{k}_{j}}\mathcal{L}_{j}  \begin{bmatrix}\psi^{x}_{j} \\ \psi^{u}_{j}\end{bmatrix} - \begin{bmatrix}\xi^{g}_{j-1} - A^{k\top}_{j} \xi^{g}_{j}  \\ -B^{k\top}_{j}\xi^{g}_{j}\end{bmatrix} - \begin{bmatrix}C^{k\top}_{j}  \\  D^{k\top}_{j}\end{bmatrix}\xi^{h}_{j} = 0 \quad \forall j \in \mathbb{Z}_{0,N-1}
\\[1em]
\nabla^{2}_{\tilde x^{k}_{N}} \mathcal{T}\psi^{x}_{N} - \nabla_{\tilde x^{k}_{N}}\bar{\mathcal{T}}(\tilde x^{k}_{N})\xi^{g}_{N} - \nabla_{\tilde x^{k}_{N}}\hat{\mathcal{T}}(\tilde x^{k}_{N}) \xi^{h}_{N} = 0
\end{gather}
$$
Where only the sensitivities are unknown. We can rewrite the sub-Hessians as
$$\nabla^{2}_{z^{k}_{j}}\mathcal{L}_{j}  = \begin{bmatrix}\nabla^{2}_{\tilde x^{k}_{j}}\mathcal{L}_{j} & \nabla^{2}_{\tilde x^{k}_{j},\tilde u^{k}_{j}}\mathcal{L}_{j} \\  \nabla^{2}_{\tilde x^{k}_{j},\tilde u^{k}_{j}}\mathcal{L}_{j}^\top & \nabla^{2}_{\tilde u^{k}_{j}}\mathcal{L}_{j}\end{bmatrix}
\triangleq
\begin{bmatrix} Q_{j} & W_{j} \\  W_{j}^{\top} & R_{j} \end{bmatrix}$$
and separate the expressions, to get
$$
\begin{gather}
\begin{aligned}
\xi^{g}_{j-1} &= Q_{j}  \psi^{x}_{j} + W_{j} \psi^{u}_{j} + A^{k\top}_{j}\xi^{g}_{j} - C^{k\top}_{j} \xi^{h}_{j} \\[1em]
0 &=  W_{j}^{\top} \psi^{x}_{j} + R_{j} \psi^{u}_{j} + B^{k\top}_{j}\xi^{g}_{j} - D^{k\top}_{j} \xi^{h}_{j} \\
\end{aligned} \qquad \forall j \in \mathbb{Z}_{0,N-1} \\[1em]
0 = \nabla^{2}_{\tilde x^{k}_{N}} \mathcal{T} \psi^{x}_{N} - \nabla_{\tilde x^{k}_{N}}\bar{\mathcal{T}}(\tilde x^{k}_{N})\xi^{g}_{N} - \nabla_{\tilde x^{k}_{N}}\hat{\mathcal{T}}(\tilde x^{k}_{N}) \xi^{h}_{N}
\end{gather}
$$
This is also a discrete linear dynamical system, defined backwards in $j$. More precisely, this is a discrete [[Ordinary Differential Equation (ODE)|differential algebraic equation (DAE)]].

# Summary
$$
\begin{align*}
\psi^{x}_{0} &= I_{n_{x}\times n_{x}} \\[2em]
\psi^{x}_{j+1} &= A^{k}_{j} \cdot \psi^{x}_{j} + B^{k}_{j} \cdot \psi^{u}_{j} && \qquad\forall j\in \mathbb{Z}_{0,N-1}\\[1em]
\xi^{g}_{j-1} &= Q_{j}  \psi^{x}_{j} + W_{j} \psi^{u}_{j} + A^{k\top}_{j}\xi^{g}_{j} - C^{k\top}_{j} \xi^{h}_{j}  &&\qquad \forall j \in \mathbb{Z}_{0,N-1}\\[1em]
0 &=  W_{j}^{\top} \psi^{x}_{j} + R_{j} \psi^{u}_{j} + B^{k\top}_{j}\xi^{g}_{j} - D^{k\top}_{j} \xi^{h}_{j}  &&\qquad \forall j \in \mathbb{Z}_{0,N-1} \\[1em]
0&=C^{k}_{j} \psi^{x}_{j} + D^{k}_{j} \psi^{u}_{j} &&\qquad \forall j\in \mathbb{Z}_{0,N-1} \\[2em] 
%% \\\\
0 &= \frac{\partial}{\partial \tilde x^{k}_{N}}\begin{bmatrix}\bar{\mathcal{T}}(\tilde x^{k}_{N}) \\ \hat{\mathcal{T}}(\tilde x^{k}_{N})
\end{bmatrix} \cdot \psi^{x}_{N}\\[1em] 
0 & = \nabla^{2}_{\tilde x^{k}_{N}} \mathcal{T} \psi^{x}_{N} - \nabla_{\tilde x^{k}_{N}}\bar{\mathcal{T}}(\tilde x^{k}_{N})\xi^{g}_{N} - \nabla_{\tilde x^{k}_{N}}\hat{\mathcal{T}}(\tilde x^{k}_{N}) \xi^{h}_{N}
\end{align*}
$$