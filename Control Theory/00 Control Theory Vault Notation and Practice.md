# Notation
In this vault, we strive to be consistent in our notation in order to
- maintain readability;
	- it easier to read through the theory quickly when you can tell by the notation what is meant by the various symbols
	- it is easier to compare notes when they use the same notation;
		- when looking at a theorem that utilizes a term/concept, you might want to look quickly at the definition of that term/concept. In such a case, it is convenient that the notation is the same in the theorem and definition.
- streamline communication between coworkers;
	- it is convenient to use the same notation when
		- discussing theory with another person
		- collaborating on/writing in the same note


## Symbols
We would like to align everyone's use of symbols within this vault, so as to maintain notational consistency. Here is a list of symbols and their respective meaning, that we will strive to adhere to. That is, we always use the relevant symbol for the given meaning, rather than another symbol, and the symbol should never be used to mean something else.
### Sets:
For denoting sets, we always use the "Blackboard Bold" font, and a capital letter:
- That is: "\\mathbb{}"
- this is to remain consistent with the widely used set notations from number theory:
	- $\mathbb{N}$, $\mathbb{Z}$, $\mathbb{Q}$, $\mathbb{I}$, $\mathbb{R}$, $\mathbb{C}$
#### Basic Symbols (number theory)
- $\emptyset$ - The empty set
- $\mathbb{N}$ - Natural numbers: $\{0,1,2,3,\dots\}$ 
	- To specify whether or not zero is included, we define:
		- $\mathbb{N}_0 \triangleq \mathbb{N}$
		- $\mathbb{N}_1 \triangleq \mathbb{N}\setminus 0$
- $\mathbb{Z}$ - Integers: $\{\dots,-3,-2,-1,0,1,2,3,\dots\}$
- $\mathbb{Q}$ - Rationals: $x\in\mathbb{Q} \implies \exists a,b\in\mathbb{Z}:x=\frac{a}{b}$
- $\mathbb{I}$ - Irrationals: $x\in\mathbb{I} \implies \centernot\exists a,b\in\mathbb{Z}:x=\frac{a}{b}$
- $\mathbb{R}$ - Reals: $\mathbb{R} \triangleq \mathbb{Q}\cup\mathbb{I}$
- $\mathbb{C}$ - Complex Numbers

#### Other Set Symbols
- $\mathbb{E}$ - An example set, used as place holder for any set.
- $\mathbb{D}$ - Used to denote the domain of a function: $f:\mathbb{D}\mapsto\mathbb{E}$, when the domain is non-specified
	- Typically for ODEs: $\dot{x} = f(t,x,u)$
		- then
			- $f:\mathbb{R}_+\times\mathbb{D}\times\mathbb{E}\mapsto\mathbb{R}^{n_x}$
			- $\mathbb{D}\subseteq\mathbb{R}^{n_x}$ 
-  $\mathbb{B}_r$ - A ball of radius $r$
	- $\mathbb{B}_r \triangleq \{x\in\mathbb{R}^{n}\Big| ||x||_2 \leq r\}$
-  $\mathbb{B}_{<r}$ - A ball of radius $r$, not including $r$
	- $\mathbb{B}_{<r} \triangleq \{x\in\mathbb{R}^{n}\Big| ||x||_2 < r\}$ 
#### Non-strict Set Symbols
These are typical uses for set symbols, but non-strict. That is, we strive to use these symbols is in the various listed contexts, but the symbols can be used for several context.
- $\mathbb{S}$
	- "safe sets" - Safe control: [[Control Barrier Function]] etc.
- $\mathbb{A}$ 
	- "region of attraction" - [[Lyapunov Stability#Asymptotic Stability (AS)|Asymptotic Stability]]
- $\mathbb{P}$
	- "set of primes" - $\mathbb{P} = \{x\in \mathbb{N} | x\text{ is prime}\}$
	- "Positive orthant" - $\mathbb{P} = \mathbb{R}_{>0}^{n}$
		- $\mathbb{P}_0 = \mathbb{R}_{+}^{n}$
- $\mathbb{U}$ 
	- "admissible inputs" - the set of possible/acceptable inputs to a dynamical system

#### Other Set Notational Practices
- $\mathbb{E}^{n}$ 
	- A set *'raised to a power'* is used to denote an n-dimensional vector space, where each dimension amounts to the base set;
		- For example, if a vector $v$ belongs to $\mathbb{E}\times\mathbb{E}\times\mathbb{E}$, we instead write $v\in \mathbb{E}^3$
		- Typical example: $x\in\mathbb{R}^{n_x}$ 
			- $x$, in this example, is such that $\dim(x) = n_x$ , and that each element belongs to the reals $x_i\in\mathbb{R}$.
- $\mathbb{E}_{+}$ 
	- A subscript "+" indicates the subset of $\mathbb{E}$ containing only and all positive values
		- $\mathbb{E}_+ \triangleq \{x\in\mathbb{E}|x\geq0\}$
			- This includes 0
			- Example: $\mathbb{R}_+$ denotes the positive reals
- $\mathbb{E}_{>0}$ 
	- A subscript ">0" indicates the subset of $\mathbb{E}$ containing only and all positive values except from zero
		- $\mathbb{E}_+ \triangleq \{x\in\mathbb{E}|x>0\}$
			- This excludes 0
			- Example: $\mathbb{R}_{>0} = \mathbb{R}_+\setminus0$ denotes the positive reals except zero
- $\mathbb{E}_{a,b}$ 
	- Subscripting with two numbers $a$ and $b$ indicates the subset of $\mathbb{E}$ that contain only and all values between and including $a$ and $b$
		- $\mathbb{E}_{a,b} \triangleq \{x\in\mathbb{E}|a\leq x \leq b\}$
		- Ex: $\mathbb{Z}_{0,5} = \{0,1,2,3,4,5\}$
- $\mathbb{E}'$ 
	- A 'prime' indicates the complement of a set.
		- That is, in the context of a greater set $\mathbb{O} \supset \mathbb{E}$, the complement, $\mathbb{E}'$, is such that:
			- $\mathbb{E} \cup \mathbb{E}' = \mathbb{O}$
			- $\mathbb{E} \cap \mathbb{E}' = \emptyset$
- $\partial\mathbb{E}$
	- The boundary of the set $\mathbb{E}$ 
- $\text{int}~\mathbb{E}$ 
	- Denotes the interior of $\mathbb{E}$

#### Operators and Relations
- $\mathbb{E}\subset\mathbb{O}$ 
	- $\mathbb{E}$ is a **strict** subset of $\mathbb{O}$
		- note: $\mathbb{E}\subset\mathbb{O} \implies \mathbb{E} \not= \mathbb{O}$
- $\mathbb{E} \subseteq \mathbb{O}$
	- $\mathbb{E}$ is a non-strict subset of $\mathbb{O}$
		- Note: $\mathbb{E} \subseteq \mathbb{O} \implies \big(\mathbb{E}\subset\mathbb{O} \bigvee \mathbb{E}=\mathbb{O}\big)$




### Functions and Dynamical Systems
Here, we define use of symbols and operators in the context of functions/maps and dynamical system/ODEs.

#### Initial Value Problem (dynamical system/ODE)
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


#### Other Functions
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