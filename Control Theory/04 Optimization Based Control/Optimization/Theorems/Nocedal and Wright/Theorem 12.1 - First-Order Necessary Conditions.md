%% #NonlinearSystems/Theorem%%
Consider ![[NLP formulation#^NLP]]
If:
- $z^*$ is a local solution of (NLP)
- $g\in \mathcal{C}^{1}$
- $h\in \mathcal{C}^{1}$
- [[LICQ - Linear Independence Constraint Qualification|LICQ]] holds at $z^*$

Then:
- there exists a $\lambda^{*}$ such that the [[KKT Conditions]] are satisfied at $(z^{*},\lambda^{*})$



**Remarks:**
- This theorem says that the KKT conditions necessarily hold at all solutions (given LICQ and differentiability). Therefore the KKT conditions are "necessary conditions" for optimality
- Many NLP-solvers are simply algorithm for solving a set of equations; the [[KKT Conditions]], numerically. Points that satisfy the KKT conditions are good candidates for solutions.
	- Note that a point that does not satisfy the KKT conditions is NOT a solution.


