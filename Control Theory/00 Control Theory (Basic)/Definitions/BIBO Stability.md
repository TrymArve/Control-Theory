#Theory/Definition/BIBO

# Definition
A controlled system (system with input $u$) is BIBO stable iff
- for every bounded input, The output is bounded.

## Summary
$\dot{x} = f(x,u)$ is BIBO stable iff
$$ ||u(t)||_{\mathcal{L}_\infty} \leq \overline{u} \implies ||x^0(t)|| \leq b \quad \forall t\geq t_0$$
