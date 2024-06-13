---
tags:
  - NonlinearSystems/Lemma
  - Optimization/NMPC
  - Optimization/LMPC
---
---
If:
 - Gauss-Newton Hessian approximation is used in [[Gros ~ SQP for NMPC|SQP for NMPC]]
	 - that is: $H^{i}_{j} = W^{i}_{j}$

Then:
$$\text{QP}^{i}_{\text{LPMC}}(\hat{x}_{i},x^{ref,i},u^{ref,i}) = \text{QP}^{i}_{\text{NPMC}}(\hat{x}_{i},x^{ref,i},u^{ref,i},x^{ref,i},u^{ref,i})$$

---

**Remarks:**
- The QPs are based on [[Gros ~ LMPC]] and [[Gros ~ SQP for NMPC]]
- $\text{QP}^{i}_{\text{NPMC}}$ amounts to one iteration of [[Gros ~~ SQP-NMPC Algorithm#$ text{SQP}_{ text{NMPC}}( hat{x}_{i}, tilde{x} {i,g_{0}}, tilde{u} {i,g_{0}},x {ref,i},u {ref,i},k_{max}) triangleq$|SQP for NMPC]]
- This comparison lets us [[LPMC vs NMPC - Bridging the Gap with RTI|"bridge the gap"]] between Linear and Nonlinear MPC with #Unfinished "insert RTI reference"

**Interpretation:**
- The adjustment ($\Delta u^{i}_{0}$) to the control reference ($u^{ref,i}_{0}$) by [[Gros ~ LMPC|Linear MPC]] is the same as:
- The adjustment ($\Delta u^{i}_{0}$) that the [[Gros ~~ QP-NMPC Formulation|QP approximation]] of [[Gros ~~ NMPC Formulation|NMPC problem]] makes to your guess, if you guess that the reference is the solution.


# Comparison:
![[QP-LMPC Formulation#^QP]]

![[Gros ~~ QP-NMPC Formulation#^QP]]
**QP-LMPC Linearizations:**
![[QP-LMPC Linearizations#^Linearizations]]
**QP-NMPC Linearizations:**
![[Gros ~~ QP-NMPC Linearizations#^Linearizations]]


