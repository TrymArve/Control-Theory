#Unfinished 
Based on [[Gros ~ LMPC]], [[Gros ~ NMPC]], and [[Gros ~ SQP for NMPC]].


We see that, by [[Lemma - (QP for NMPC) vs. (LMPC)]], we have that the first iteration of the [[Gros ~ SQP for NMPC|SQP-like algorithm for NMPC]], it equal to the step taken in LPMC, if one uses the reference as the initial guess for the SQP step.
- *(given the same step size $\alpha$)*
That is: $$u^{\text{NMPC}}_{i} = u^{\text{LMPC}}_{i}$$ whenever $$\begin{align*}
u^{\text{NMPC}}_{i} & = \tilde{u}^{i}_{0}\\
u^{\text{LMPC}}_{i} & = u^{ref,i}_{0} + \Delta u^ {i}_{0}\\[0.5cm]
\text{where:}\\
\Delta u^ {i}_{0} &\leftarrow \text{QP}_\text{LMPC}^{i}(\hat{x}_{i},x^{ref,i},u^{ref,i})\\
\tilde{u}^{i}_{0} & \leftarrow \text{SQP}^{i}_{\text{NMPC}}(\hat{x}_{i},\tilde{x}^{i,g_{0}},\tilde{u}^{i,g_{0}},x^{ref,i},u^{ref,i},k_{max})\\[0.5cm]
\text{with:}\\
\tilde{x}^{i,g_{0}} &= x^{ref,i}\\
\tilde{u}^{i,g_{0}} &= u^{ref,i}\\
k_{max} &= 1
\end{align*}$$


