#Theory/Definition 

Consider: ![[Consider - Controlled NTI#^system]]
where:
- $\boldsymbol{u}$ is a Lebesgue measurable essentially bounded external input
- $\boldsymbol{f}$ is a Lipschitz continuous function w.r.t. the first argument uniformly w.r.t. the second one. 
	- *(This ensures that there exists a unique absolutely continuous solution of the system.)*

**Definition ISS**
System $\Sigma_\circ$ is called **input-to-state stable (ISS)** if there exist function $\gamma \in \mathcal{K}$ and $\beta \in \mathcal{KL}$ so that for all initial values $x_\circ$, all admissible inputs $u$ and all times $t\geq0$ the following inequality holds
$$ ||x(t)|| \leq \beta(||x_\circ||,t) + \gamma(||u||_{\mathcal{L}_\infty}). $$
- $\gamma$ is referred to as the "gain".



## Local ISS   (aka: *"Malkin's total stability"*)
#Theory/Definition/Local-ISS
### Slides by Antonio Loria
The origin for $\dot{x} = f(t,x,0)$ is said to be ***Locally ISS** (totally stable)*  if
- For the system $\dot{x} = f(t,x,u)$,
	- small bounded inputs $u(t,x)$, and
	- small initial conditions $x_0$
	yield small state trajectories for all $t\geq t_0$.
That is;
- $\forall~\epsilon>0 \quad \exists~\delta>0 :$
$$ \max\{||x_\circ||,||u||_{\mathcal{L}_\infty}\} \leq \delta \quad \implies \quad ||x^0(t,u(t))|| \leq \epsilon \quad \forall t\geq t_0$$
### Wikipedia (LISS):
A system is called **Locally ISS*** iff:
- $\exists~\rho>0$
- $\exists~\gamma\in\mathcal{K}$
- $\exists~\beta\in\mathcal{KL}$
such that
- $\forall~x_0 \leq \rho$
- $\forall~u(t):||u(t)||_{\mathcal{L}_\infty} \leq \rho$
- $\forall~t \geq t_0$
we have that
$$ ||x(t)|| \leq \beta(||x_0||,t) + \gamma(||u||_{\mathcal{L}_\infty})$$
**Note:** This is essentially just that the ISS property hold in some region around the origin and for small input values.



