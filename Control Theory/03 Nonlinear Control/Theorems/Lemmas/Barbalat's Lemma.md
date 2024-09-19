---
tags:
  - NonlinearSystems/Lemma
Note Author:
  - Trym A. Gabrielsen
Theory Author:
  - Hassan K. Kahlil
  - Dumitru Barbălat
Reviewed By:
---
Let
- $\phi:\mathbb{R}\mapsto\mathbb{R}$

be
- [[Uniform Continuity|uniformly continuous]] on $[0,\infty\rangle$.

If
- $\lim_{t\rightarrow\infty} \int_{0}^{t} \phi(\tau) ~d\tau$
	- exists
	- is finite

then
- $t\rightarrow\infty \implies \phi(t)\rightarrow0$


# Alternatively
Let
- $\dot{f}:\mathbb{R}\mapsto\mathbb{R}$

be
- uniformly continuous on $[0,\infty\rangle$.

If
- $\lim_{t\rightarrow\infty} f(t)$
	- exists
	- is finite

then
- $t\rightarrow\infty \implies \dot{f}(t)\rightarrow0$



# Remarks
- $\lim_{t\rightarrow\infty} f(t)$
	- exists
	- is finite

essentially says that $f(t)$ converges to a value
- note: $\dot{f}\rightarrow0 \centernot\implies f(t)\rightarrow a$
	- ex: $f(t) = \sin(\ln(t))$
- note: $f(t) \rightarrow a \centernot\implies \dot{f}(t) \rightarrow 0$
	- ex: $f(t) = e^{-t}\sin(e^{2t})$
	- However, if in addition, $\dot{f}$ is uniformly continuous, then the implication is true
	- $\dot{f}$ is uniformly continuous if $\ddot{f}$ is [[Uniform Boundedness|uniformly bounded]]:  from [[Uniform Continuity from uniformly bounded derivative]]
- One can think:
	- the only way for a function to converge to a value without its derivative going to zero, is if the function starts oscillating up and down increasingly fast, with decreasing amplitude (since its converging).
	- this means that the derivative will start oscillating also, but with increasing amplitude.
		- the amplitude goes to infinity as $t\rightarrow\infty$
	- Though this means that the derivative is not uniformly continuous, even though it is continuous.
	- By requiring that the derivative is uniformly continuous, the oscillations cannot approach infinite frequency.
	- Now there is now way for the function to converge without its derivative smoothing out to zero.
	