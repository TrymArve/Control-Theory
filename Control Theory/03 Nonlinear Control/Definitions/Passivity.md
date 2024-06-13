#NonlinearSystems/Definition

Reference:
*"Nonlinear Systems"*- by Hassan K. Khalil, third edition - Pearson New International Edition p.236.

Consider: ![[Consider - Controlled NTI#^system]]
System $\Sigma_\circ$ is said to be **passive** iff
- $\exists~ V:\mathbb{R}^{n_x}\mapsto \mathbb{R}$ s.t.    *('storage function')*
	- $V\in\mathcal{C}^1$ 
	- $V$ is positive semi-definite
	such that
	$$ u^\top y \geq \dot{V} = \frac{\partial V}{\partial x}f(x,u)$$

Moreover, it is said to be
- **lossless** iff:
	- $u^\top y = \dot{V}$
- **input-feedforward passive** iff:
	- $u^\top y \geq \dot{V} + u^\top \phi(u) \quad \bigg(\implies u^\top (y -\phi(u)) \geq \dot{V} \bigg)$ 
	- for some function $\phi(u) \in \mathbb{R}^{n_u}$
- **input strictly passive** iff:
	- it is input-feedforward passive with $\phi(u)$ [[Definiteness#Half-Definiteness (Trym's definition)|half-definite]]
- **output-feedback passive** iff: 
	- $u^\top y \geq \dot{V} + y^\top \rho(y) \quad \bigg(\implies y^\top (u -\rho(y)) \geq \dot{V} \bigg)$ 
	- for some function $\rho(y) \in \mathbb{R}^{n_y}$
- **output strictly passive** iff:
	- it is output-feedback passive with $\rho(y)$ [[Definiteness#Half-Definiteness (Trym's definition)|half-definite]] 
- **strictly passive** iff:
	- $u^\top y \geq \dot{V} + \psi(x) \quad \bigg(\implies y^\top u - \psi(x) \geq \dot{V} \bigg)$
	- for some [[Definiteness#Positive definiteness|positive definite]] function $\psi(x)\in\mathbb{R}$ 


# Intuition
- The storage function looks like
$$ \varepsilon (t) = \varepsilon_\circ + \int_{t_\circ}^{t}u(\tau)^\top y(\tau) ~d\tau + \cdots$$
with draining/reviving terms
- $-\int_{t_\circ}^{t} u(\tau)^\top \phi(u) ~d\tau$  for input-feedforward passivity
- $-\int_{t_\circ}^{t} y(\tau)^\top \rho(y) ~d\tau$  for output-feedback passivity
we notice that
- for normal passivity, the storage function is a property of the system that only changes values when applying input *'against'* or *'with'* the output.
	- $u(\tau)^\top y(\tau) < 0$ and $u(\tau)^\top y(\tau) > 0$ respectively
- therefore, to make this value (storage function) equal to zero, we just have to make sure to work *'against'* the output more than we work *'with'* it.
- to ensure this, we can make a state-feedback controller $u = -k(y)$ such that $k$ is [[Definiteness#Half-Definiteness (Trym's definition)|half-definite]], since with then always work *against* the output, and subsequently always drain the storage function.
- if the system then has the property that $\varepsilon(t)\rightarrow0 \implies x\rightarrow0$, then we see that the system has become [[Attractivity|attractive]].
- This is the principle availed in [[Theorem 4 - Passivity-Based Control for Asymptotic Stability]]

- we see that if the system is input-feedforward or output-feedback passive
	- the controller must make sure to drain the storage faster than the feedforward/feedback terms
	- if the only the input-feedforward term is present, then the storage will never change as long as the input is zero
	- if only the output-feedback term is present, then the storage will not change when the output is zero
- In the strict case
	- the controller only needs to not revive the storage more than the draining terms drain


# Mostly passive (Trym's definition)
The system is 
- **mostly input passive** iff:
	- it is input-feedforward passive with $\int_{t_\circ}^{\infty} u(\tau)^\top\phi(u(\tau))~d\tau \leq 0$ 
- **mostly output passive** iff:
	- it is output-feedback passive with $\int_{t_\circ}^{\infty} y(\tau)^\top\rho(y(\tau))~d\tau \leq 0$ 