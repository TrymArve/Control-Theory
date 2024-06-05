#Theory/Definition
Consider: ![[Consider - Controlled NTV#^system]]
The system $\dot{x} = f(t,x,u)$ satisfies the **Asymptotic Gain*** property iff
- $\exists~\gamma\in\mathcal{K}:$
	- $\forall x_0$ , $\forall u$
		- $\limsup_{t\rightarrow\infty} ||x^0(t)|| \leq \gamma(||u||_{\mathcal{L}_\infty})$ 


**Intuition**
As the time goes to infinity, the state $x(t)$ either goes to infinity, goes to some point, or keeps moving around, boundedly, forever . The magnitude therefore either goes to infinity, converges to some value, or keeps 'oscillating' up and down with a finite bound. 
The upper bound on this 'oscillation' should be zero in the absence of input, that is, the unactuated system will go to zero: GAS.
The system is allowed to not converge to zero when there is some input. The distance the solution may roam is dependent ($\mathcal{K}$) on the largest input value applied to the system across its evolution ($||u||_{\infty}$). 