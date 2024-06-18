---
tags:
  - NonlinearSystems/Lemma
Note Author:
  - Trym A. Gabrielsen
Theory Author:
  - Antonio Loría
Reviewed By:
---
Consider: ![[Consider - NTV#^system]]
If:
- $\exists~r,c,p>0:$
	- $(1): \quad \max(||x(t)||_{\mathcal{L}_\infty}, ||x(t)||_{\mathcal{L}_p}) \leq c||x_\circ||\quad \forall~(x_\circ,t_\circ)\in\mathbb{B}_r\times\mathbb{R}_+$
then:
- the origin is 
	- uniformly exponentially stable (UES)
	- where 
		- $||x(t)||\leq k||x_\circ||e^{-\gamma(t-t_\circ)}\quad \forall t\geq t_\circ , x_\circ \in \mathbb{B}_r$
	- with
		- $k=ce^{\frac{1}{p}}$  
		- $\gamma = \frac{1}{pc^p}$

Moreover, if 
- (1) holds for all $x_\circ \in \mathbb{R}^{n_x}$
then
- the origin is uniformly globally exponentially stable (UGES)
