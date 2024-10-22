---
tags:
  - Optimization/NMPC
  - Optimization/SQP
Note Author:
  - Trym A. Gabrielsen
Theory Author:
  - Sébastien Gros
Reviewed By:
---

An [[General SQP Method|SQP]]-type strategy for solving the NMPC problem.
Notation: [[Optimization#Dynamic Optimization / MPC|here]]

# SQP for NMPC
NMPC Control requires that, at time $t_{i}$, we compute $$\text{NLP}_{\text{NMPC}}^{i}(\hat{x}_{i},x^{ref,i},u^{ref,i})$$
To this end, we use an algorithm to approximate the solution:
$$\text{SQP}^{i}_{\text{NMPC}}(\hat{x}_{i},\tilde{x}^{i,g_{0}},\tilde{u}^{i,g_{0}},x^{ref,i},u^{ref,i},k_{max}) \approx \text{NLP}_{\text{NMPC}}^{i}(\hat{x}_{i},x^{ref,i},u^{ref,i})$$

The algorithm is defined as: ![[Gros ~~ SQP-NMPC Algorithm#$ text{SQP} {i}_{ text{NMPC}}( hat{x}_{i}, tilde{x} {i,g_{0}}, tilde{u} {i,g_{0}},x {ref,i},u {ref,i},k_{max}) triangleq$]]


# Idea

## Initial Guess
1) First we simply guess a solution; $(\tilde{x}^{i,g_{0}},\tilde{u}^{i,g_{0}})$
2) This guess $(k=0)$ is wrong, and we must find a set of adjustments:
	- $(\Delta x^{i},\Delta u^{i})_{k} = (\tilde{x}^{i,g_{k}},\tilde{u}^{i,g_{k}})-(\tilde{x}^{i,g_{k+1}},\tilde{u}^{i,g_{k+1}})$
	to obtain the next guess $(k+1=1)$
## Newton Step
3) To find the appropriate adjustments to the $k^{\text{th}}$ guess, we approximate $\text{NLP}^{i}_{\text{NMPC}}(\cdot)$ by a QP, and solve for the adjustments that minimizes it:  ![[Gros ~~ QP-NMPC Formulation#^QP]]with correction terms ![[Gros ~~ QP-NMPC Correction Terms#^Correction-Terms]] and linearizations ![[Gros ~~ QP-NMPC Linearizations#^Linearizations]] and $H^{i}_{j} \approx \nabla^{2}\mathcal{L}^{i}_{j}$ is some approximation of the Hessian of the Lagrangian of the original NLP problem
	-  ("Gauss-Newton Hessian approximation" $\rightarrow H^{i}_{j} = W^{i}_{j}$ is often a decent approximation)
4) We then define: $$(\Delta x^{i},\Delta u^{i})_{k} \triangleq \text{QP}_{\text{NMPC}}^{i}(\hat{x}_{i},\tilde{x}^{g_{k}},\tilde{u}^{g_{k}},x^{ref,i},u^{ref,i})$$
- **Interpretation:**
	- These adjustments adjusts the guess in such a way that the new guess minimizes a [[Gros ~~ QP-LMPC Formulation|QP]] approximation of the original [[Gros ~~ NMPC Formulation|NLP]]
	- The new guess likely also approximates the solution to the NLP better than the previous guess
		- this is not necessarily the case, and one usually chooses somewhere in between the two guesses *(step length)* as the actual new guess.
	- One may understand that the QP is a meaningful approximation of the NLP by noticing that the KKT conditions are either the same, or good approximations of each other.
## Take Step
5) Use a [[Merit Function]] to find a step length; $\alpha$, that ensures progress/descent
	- or some other way of ensuring that progress
6) Take step $$(\tilde{x}^{i,g_{k+1}},\tilde{u}^{i,g_{k+1}}) = (\tilde{x}^{i,g_{k}},\tilde{u}^{i,g_{k}}) + \alpha(\Delta x^{i},\Delta u^{i})_{k}$$
## Repeat
7) Repeat:
	- Find Newton Step
		- QP approximation about current guess
		- Solve QP
	- Take Step
## Terminate
8) Stop iterating when:
	- either; some convergence criteria is satisfied
	- or; after a certain number of iterations
9) The solution to the NLP *(the state and input prediction)* is then
	- $(\tilde{x}^{i,g_{k}},\tilde{u}^{i,g_{k}}) \rightarrow (\tilde{x}^{i*},\tilde{u}^{i*})$


