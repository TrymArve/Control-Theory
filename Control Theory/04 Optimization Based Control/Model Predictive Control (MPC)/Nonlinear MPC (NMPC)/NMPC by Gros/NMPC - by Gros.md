%% #NonlinearMPC %%
**Reference:** Gros, S., Zanon, M., Quirynen, R., Bemporad, A. and Diehl, M., 2020. From linear to nonlinear MPC: bridging the gap via the real-time iteration. _International Journal of Control_, _93_(1), pp.62-80.
Notation: [[Optimization#Dynamic Optimization / MPC|here]]
OCP: ![[Optimal Control Problem#^OCP]]

**NMPC Controller**
The NMPC control input; $u^{\text{NMPC}}_{i}$, at time $t_{i}$ is defined as
$$u^{\text{NMPC}}_{i} = \tilde{u}^{i}_{0}$$
where $\tilde{u}^{i}_{0}$ is found by solving
$$\begin{gather*}
\text{NLP}_{\text{NMPC}}^{i}(\hat{x}_{i},x^{ref,i},u^{ref,i}) \triangleq \hspace{10cm} \\[0.5cm]
\arg \min_{\tilde{x}^{i},\tilde{u}^{i}} \quad \sum\limits_{j=0}^{H-1}\frac{1}{2}\begin{bmatrix}\tilde{x}^{i}_{j}-x^{ref,i}_{j} \\ \tilde{u}^{i}_{j}-u^{ref,i}_{j}\end{bmatrix}^{\top} W^{i}_{j} \begin{bmatrix}\tilde{x}^{i}_{j}-x^{ref,i}_{j} \\ \tilde{u}^{i}_{j}-u^{ref,i}_{j}\end{bmatrix}\\[0.3cm]
\begin{aligned}
\text{subject to:}&\\
\tilde{x}^{i}_{0} & = \hat{x}_{i}\\
\tilde{x}^{i}_{j+1} & = f_d(t_{j},\tilde{x}^{i}_{j},\tilde{u}^{i}_{j}) && \forall j \in \mathbb{N}_{0,N-1}\\
0 &\leq h(t_{j},\tilde{x}^{i}_{j},\tilde{u}^{i}_{j})  && \forall j \in \mathbb{N}_{0,N-1}
\end{aligned}
\end{gather*}$$
^NMPC-Gros

**Remarks:**
- Note that there are no terminal costs/constraints, but should be present in an implementation
- Note that the cost/objective function may be nonlinear
	- this is sometimes preferred
	- here, for simplicity, we regard a quadratic cost, but [[SQP for NMPC by Gros]] is possible for nonlinear costs as well



