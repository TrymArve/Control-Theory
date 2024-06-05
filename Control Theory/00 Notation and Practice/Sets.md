For denoting sets, we always use the "Blackboard Bold" font, and a capital letter:
- That is: "\\mathbb{}"
- this is to remain consistent with the widely used set notations from number theory:
	- $\mathbb{N}$, $\mathbb{Z}$, $\mathbb{Q}$, $\mathbb{I}$, $\mathbb{R}$, $\mathbb{C}$
# Basic Set Symbols (number/set theory)
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

# Other Set-Symbols
- $\mathbb{D}$ - Used to denote the domain of a function: $f:\mathbb{D}\mapsto\mathbb{E}$, when the domain is non-specified
	- Typically for ODEs: $\dot{x} = f(t,x,u)$
		- then
			- $f:\mathbb{R}_+\times\mathbb{D}\times\mathbb{E}\mapsto\mathbb{R}^{n_x}$
			- $\mathbb{D}\subseteq\mathbb{R}^{n_x}$ 
-  $\mathbb{B}_r$ - A ball of radius $r$
	- $\mathbb{B}_r \triangleq \{x\in\mathbb{R}^{n}\Big| ||x||_2 \leq r\}$
-  $\mathbb{B}_{<r}$ - A ball of radius $r$, not including $r$
	- $\mathbb{B}_{<r} \triangleq \{x\in\mathbb{R}^{n}\Big| ||x||_2 < r\}$ 
- $\tilde{\mathbb{N}}(z)$ is a neighborhood of $z$
## Non-strict Set Symbols
These are typical uses for set symbols, but non-strict. That is, we strive to use these symbols is in the various listed contexts, but the symbols can be used for several context.
- $\mathbb{E}$ 
	- An example set, used as place holder for any set.
	- "Expected Value" - operator (not a set)
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

# Other Set Notational Practices
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

## Operators and Relations
- $\mathbb{E}\subset\mathbb{O}$ 
	- $\mathbb{E}$ is a **strict** subset of $\mathbb{O}$
		- note: $\mathbb{E}\subset\mathbb{O} \implies \mathbb{E} \not= \mathbb{O}$
- $\mathbb{E} \subseteq \mathbb{O}$
	- $\mathbb{E}$ is a non-strict subset of $\mathbb{O}$
		- Note: $\mathbb{E} \subseteq \mathbb{O} \implies \big(\mathbb{E}\subset\mathbb{O} \bigvee \mathbb{E}=\mathbb{O}\big)$




