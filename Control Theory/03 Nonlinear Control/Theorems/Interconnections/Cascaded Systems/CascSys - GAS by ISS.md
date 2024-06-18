---
tags:
  - NonlinearSystems/Theorem
Note Author:
  - Trym A. Gabrielsen
Theory Author:
  - Antonio Loría
Reviewed By:
---
Consider: ![[Consider - Cascade Interconnection (Time-Invariant)#^cascade-interconnected-system]]
- If:
	- $\Sigma_2$ is GAS         ($x_2 \rightarrow 0$ from anywhere)
	- $\Sigma_1$ is ISS           ($x_1 \rightarrow \mathbb{B}_{\alpha(x_2)}$  from anywhere)
	Then:
	- The cascaded system $\Sigma_2 + \Sigma_1$ is GAS      ($(x_1,x_2) \rightarrow (0,0)$ from anywhere)

**Remarks:**
- *This is somewhat obvious, since ISS implies 0-GAS and Boundedness, thus [[CascSys - GAS by 0-GAS|Theorem 12]] holds*


Consider that $\Sigma_2$ has an input $u_2$ ($\dot{x}_2 = f_2(x_2,u_2)$), then
- If:
	- $\Sigma_2$ is ISS           ($x_2 \rightarrow \mathbb{B}_{\alpha_2(u_2)}$  from anywhere)
	- $\Sigma_1$ is ISS           ($x_1 \rightarrow \mathbb{B}_{\alpha_1(x_2)}$  from anywhere)
- Then:
	- The cascaded system $\Sigma_2 + \Sigma_1$ is ISS from $u_2$ to $(x_1,x_2)$. 
		($(x_1,x_2) \rightarrow \mathbb{B}_{\alpha_3(u_2)} \times \mathbb{B}_{\alpha_2(u_2)}$ from anywhere)

*Note that the ISS property means that the system state must converge to $\mathbb{B}_{\alpha(u)}$ for each constant $u$.