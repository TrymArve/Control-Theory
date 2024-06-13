#NonlinearSystems/Lemma 
Let:
- $\phi:\mathbb{R}_+\mapsto\mathbb{R}^{n}$
	- be continuously differentiable ($\phi \in \mathcal{C}^1$)
	- be such that
		- $\phi,\dot{\phi} \in \mathcal{L}_\infty^n$     *(see [[Norm#$ mathcal{L}_p m$-space ($ mathcal{L}_p$-space, but for vector functions)|Lpm-spaces]])*
		- $\phi \in \mathcal{L}_2^n$          *(see [[Norm#$ mathcal{L}_p m$-space ($ mathcal{L}_p$-space, but for vector functions)|Lpm-spaces]])*
then
- $\lim_{t\rightarrow\infty}\phi(t)=0$


**Note:**
- $\phi,\dot{\phi} \in \mathcal{L}_\infty^n$  implies that the signals are uniformly bounded
- $\phi \in \mathcal{L}_2^n$       implies that the function is integrable  (finite area under curve)
- This lemma says pretty much the same this as [[Barbalat's Lemma]]…, but extends it to vector functions 
	- (note sure if Barbalat's lemma is completely covered by this or not)
# Intuition
- We understand this as
	- if the vector function is has finite area, then we would expect the function value to go to zero at some point, since it seems like if it does not go to zero, then the area would always keep increasing.
	- it is however also necessary that the signal is bounded, and its rate of change is bounded.
- We see this issue in a sin-function that keeps increasing its frequency. 
	- you can imagine that the area under the curve is converges, since the oscillations increase.
	- This happens without the function converging to zero...
	- However, the derivative oscillates with increasing amplitude, thus it is not uniformly bounded.
- By covering this edge-case, where the area is finite without the function going to zero, because the function may oscillate increasingly;
	- we can ensure that the function converges.