#Theory/Definition/ISS 

- [Input-to-state stability - Wikipedia](https://en.wikipedia.org/wiki/Input-to-state_stability)
	- **Input-to-state stability (ISS) is a stability notion widely used to study stability of nonlinear with external inputs. Roughly speaking, a control system is ISS if it is globally asymptotically stable in the absence of external inputs and if its trajectories are bounded by a function of the size of the input for all sufficiently large times. The importance of ISS is due to the fact that the concept has bridged the gap between and, widely used within the control systems community.

	- ISS unified the Lyapunov and input-output stability theories and revolutionized our view on stabilization of nonlinear systems, design of robust nonlinear observers, stability of nonlinear interconnected control systems, nonlinear detectability theory, and supervisory adaptive control. This made ISS the dominating stability paradigm in nonlinear control theory, with such diverse applications as robotics, mechatronics, systems biology, electrical and aerospace engineering, to name a few.

	- The notion of ISS was introduced for systems described by ordinary differential equations by Eduardo Sontag in 1989.

	- Since that the concept was successfully used for many other classes of control systems including systems governed by partial differential equations, retarded systems, hybrid systems, etc.

Consider: ![[Consider - Controlled NTI#^system]]
$$(1) \qquad \dot{\boldsymbol{x}} = \boldsymbol{f}(\boldsymbol{x}, \boldsymbol{u}), \quad \boldsymbol{x}(t) \in \mathbb{R}^n , \quad \boldsymbol{u}(t) \in \mathbb{R}^m$$
where:
- $\boldsymbol{u}$ is a Lebesgue measurable essentially bounded external input
- $\boldsymbol{f}$ is a Lipschitz continuous function w.r.t. the first argument uniformly w.r.t. the second one. 
*This ensures that there exists a unique absolutely continuous solution of the system.*

**Definition ISS**
System $\Sigma_\circ$ is called **input-to-state stable (ISS)** if there exist function $\gamma \in \mathcal{K}$ and $\beta \in \mathcal{KL}$ so that for all initial values $\boldsymbol{x}_0$, all admissible inputs $u$ and all times $t\geq0$ the following inequality holds
$$ |x(t)| \leq \beta(|x_0|,t) + \gamma(||u||_\infty). $$
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
$$ \max\{||x_0||,||u||_\infty\} \leq \delta \quad \implies \quad ||x^0(t,u(t))|| \leq \epsilon \quad \forall t\geq t_0$$
### Wikipedia (LISS):
A system is called **Locally ISS*** iff:
- $\exists~\rho>0$
- $\exists~\gamma\in\mathcal{K}$
- $\exists~\beta\in\mathcal{KL}$
such that
- $\forall~x_0 \leq \rho$
- $\forall~u:||u||_\infty \leq \rho$
- $\forall~t \geq t_0$
we have that
$$ ||x(t)|| \leq \beta(||x_0||,t) + \gamma(||u||_\infty)$$
**Note:** This is essentially just that the ISS property hold in some region around the origin and for small input values.

# Properties

## Implications
Clearly, if the system is ISS, the it is also 0-GAS, and also BIBO stable if the state is considered the output of the system:

- ISS $\implies$ [[0-GAS]]
- ISS $\implies$ [[BIBO Stability|BIBO stable]] (if the state is considered the output: $y = x$)
- 0-GAS $\implies$ Local ISS



