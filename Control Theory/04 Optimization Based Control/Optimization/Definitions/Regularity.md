---
tags:
  - Unfinished
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By: 
Relevant Papers:
---
**Definition:**
An optimization problem ([[NLP formulation|NLP]]) is said to be *regular* iff it satisfies at least one of the following conditions:
- [[LICQ - Linear Independence Constraint Qualification]]
- ... #Unfinished 




**Remarks:**
- Regularity (not LICQ) is necessary to guarantee that the [[KKT Conditions (First-Order Necessary Conditions)|KKT conditions]] hold
- Many solvers assume that regularity holds, and the solution it returns is not guaranteed to be optimal if the problem is not regular.
- Also, a solver may sometimes not converge is the problem is not regular.