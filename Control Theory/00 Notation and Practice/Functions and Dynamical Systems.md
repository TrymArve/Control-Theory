Here, we define use of symbols and operators in the context of functions/maps and dynamical system/ODEs.

# Initial Value Problem (dynamical system/ODE)
An initial value problem can be written as:
$$
\Sigma_i:\quad
\begin{align}
\dot{x} & = f(t,x,u(t)), \quad x^\circ(t_\circ) = x_\circ \\
y &= h(t,x,u(t))
\end{align}
$$
and we use the following consistent notation:
- $t$ - the progressor of the IVP. That is, the "time" like variable over which the system evolves/progresses.
	- $t\in[0,t_1\rangle\subseteq\mathbb{R}_+$
- $x$ - a point in the state space of a dynamical system of dimension $n_x$
	- $x\in\mathbb{D}\subseteq\mathbb{R}^{n_x}$
- $u$ - a parameter, of dimension $n_u$ , of the system, over which we have full authority. That is, we may choose the values of $u$ across time; $u(t)$, exactly.
	- $u\in\mathbb{U}\subseteq\mathbb{R}^{n_u}$
- $f(\cdot)$ - the dynamics of a dynamical system
	- $f:[0,t_1\rangle\times\mathbb{D}\times\mathbb{U} \mapsto \mathbb{R}^{n_x}$
	- potentially; we may write:
		- $\dot{x} = f(\cdot) + g(\cdot)$
		- $\dot{x} = f(\cdot) + g(\cdot)u$
		to separate parts of the dynamics
- $\Sigma$ - used to denote a dynamical system. 
	- Use a subscript, f.ex.; $\Sigma_i$, to denote a specific system.
- $t_\circ$ - the initial 'time' of the IVP.
	- $t_\circ \in [0,t_1\rangle$
- $x_\circ$ - the initial value/state of the IVP.
	- $x_\circ \in \mathbb{D}$
- $x^\circ(t)$ - the solution to the IVP $\Sigma_i$ defined above.
	- That is, the solution to an IVP with initial conditions $x^\circ(t_\circ) = x_\circ$
	- $x^\circ:[0,t_1\rangle \mapsto \mathbb{R}^{n_x}$
- $y$ - the output of a dynamical system, f.ex:
	- the variables that we care about / want to control
	- the values we are able to measure
	- $y \in \mathbb{R}^{n_y}$
- $h$ - the map from time, state and input to the system output
	- $h:[0,t_1\rangle\times\mathbb{D}\times\mathbb{U} \mapsto \mathbb{R}^{n_y}$


# Other Functions
- $\alpha,\gamma$
	- class $\mathcal{K}$ and $\mathcal{K}_\infty$ functions
	- we prioritize using $\alpha(\cdot)$ to denote class $\mathcal{K}$ and $\mathcal{K}_\infty$ functions
	- If necessary/convenient, we may also use $\gamma(\cdot)$
	- To indicate membership if class $\mathcal{K}$ or $\mathcal{K}_\infty$, we may write:
		- $\alpha \in \mathcal{K}$  or  $\alpha \in \mathcal{K}_\infty$
- $\beta$
	- class $\mathcal{KL}$ functions
	- we write: $\beta \in \mathcal{KL}$
	- note:
		- $\beta(r,\cdot) \in \mathcal{K}$   in $r$ 
		- $\beta(\cdot,t) \in \mathcal{L}$    in $t$
- $V$ - Lyapunov functions
	- and Lyapunov 'like' functions