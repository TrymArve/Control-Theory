Based on [[Gros ~ SQP for NMPC]]


---
# $\text{SQP}^{i}_{\text{NMPC}}(\hat{x}_{i},\tilde{x}^{i,g_{0}},\tilde{u}^{i,g_{0}},x^{ref,i},u^{ref,i},k_{max}) \triangleq$

1) $\text{Set:~}k = 0$ *(current iteration)*
2) $\text{While:~} (\text{Not Converged ~~AND~}\quad k < k_{max})$ 
	1) $\text{Evaluate:}$
		- $r^{i}_{j},\quad h^{i}_{j}$
		- $A^{i}_{j},\quad B^{i}_{j}$
		- $C^{i}_{j},\quad D^{i}_{j}$
	2) $\text{Construct and Solve:}$
		- $(\Delta x^{i}, \Delta u^{i})_{k} = \text{QP}^{i}_{\text{NMPC}}(\hat{x}_{i},\tilde{x}^{i,g_{0}},\tilde{u}^{i,g_{0}},x^{ref,i},u^{ref,i})$
	3) $\text{Compute step-size:}$
		- $\alpha\in\langle0,1]$
		- $\text{such that there is 'progress'/descent}$
			- *([[Merit Function]])*
	4) $\text{Update...}$
		- $\text{...Guess:}\quad (\tilde{x}^{i,g_{k+1}},\tilde{u}^{i,g_{k+1}}) = (\tilde{x}^{i,g_{k}},\tilde{u}^{i,g_{k}}) + \alpha(\Delta x^{i}, \Delta u^{i})_{k}$
		- $\text{...Iteration Index:}\quad k \leftarrow k+1$
3) $\text{Return:} ~~ (\tilde{x}^{i,g_{k}},\tilde{u}^{i,g_{k}})$

---


