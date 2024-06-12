If:
 - Gauss-Newton Hessian approximation is used in [[SQP for NMPC by Gros|SQP for NMPC]]
	 - that is: $H^{i}_{j} = W^{i}_{j}$
Then:
$$\text{QP}^{i}_{\text{LPMC}}(\hat{x}_{i},x^{ref,i},u^{ref,i}) = \text{QP}^{i}_{\text{NPMC}}(\hat{x}_{i},x^{ref,i},u^{ref,i},x^{ref,i},u^{ref,i})$$

**Remarks:**
- The QPs are based on [[LMPC - By Gros]] and [[SQP for NMPC by Gros]]
- $\text{QP}^{i}_{\text{NPMC}}$ amounts to one iteration of [[SQP-NMPC Algorithm by Gros#$ text{SQP}_{ text{NMPC}}( hat{x}_{i}, tilde{x} {i,g_{0}}, tilde{u} {i,g_{0}},x {ref,i},u {ref,i},k_{max}) triangleq$|SQP for NMPC]]



