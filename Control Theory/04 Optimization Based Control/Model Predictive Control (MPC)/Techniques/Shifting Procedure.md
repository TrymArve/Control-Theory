---
tags: 
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
Consider some state horizon: $$x^{i} = \{x^{i}_{0},x^{i}_{1},x^{i}_{2},\dots,x^{i}_{H_{i}}\}=\{x_{i},x_{i+1},x_{i+2},\dots,x_{i+H_{i}}\}$$
Which is an excerpt of some operating interval:
$$\{x_{0},x_{1},x_{2},\underbrace{x_{3},x_{4},x_{5},x_{6},x_{7}}_{x^ {i=3}},x_{8},x_{9},x_{N=10}\}$$
The ***Shifting Procedure*** consists of generating the next horizon, by simply re-using the previous horizon values, but shifted by one. 
To get the $j^{\text{th}}$ element of the $i^{\text{th}}$ state horizon, we use $$x^{i}_{j} = x^{i-1}_{j+1}$$ such that the following state horizon becomes: $$\begin{align*}
x^{i} &=\{x^{i}_{0},x^{i}_{1},x^{i}_{2},\dots,x^{i}_{H_{i}}\}\\[0.1cm]
&=\{x^{i-1}_{1},x^{i-1}_{2},x^{i-1}_{3},\dots ,x^{i-1}_{H_{i-1}}; ~~x^{i}_{H_{i-1} ,\cdots, H_{i}} \} \\[0.1cm]
&= \{x^{i-1}_{1,\dots,H_{i}}~,~~x^{i}_{>H_{i-1}}\}
\end{align*}$$, where the last $(1+H_{i}-H_{i-1})$ elements must be chosen by other means. Of course, if the current horizon is shorter than the previous; $(1+H_{i}-H_{i-1}) \leq 0$, then there are no additional elements to generate.
visually, we get: $$\{x_{0},x_{1},
\rlap{ \overbrace{ \phantom{x_{2},x_{3},x_{4},x_{5},x_{6},x_{7}} }^{x^{2}} }
x_{2},\underbrace{ x_{3},x_{4},x_{5},x_{6},x_{7},
x_{8} }_{x^{3}},x_{9},x_{10},x_{11},x_{N=12}\}$$

**Generating New terms:**
Typical strategies for generating the new horizon elements include:
- **Copy last element of previous horizon:**
$$x^{i}_{j} = x^{i-1}_{H_{i-1}} \quad \forall j\in \mathbb{Z}_{H_{i-1},H_{i}}$$
	- This method is fast ! 
	- No computation required
	- It is often advantageous to simply copy the previous last element, if the increase in speed makes up for the minor lack in accuracy.
	- For example, if the horizon is long, the poor copy-guess is adjusted many times before reaching the start of the horizon, where disturbance rejection is most prominent.
- **Predict the next state using dynamics:**
	- A reasonable guess is to, instead copy the states, one may copy the control last control action from the previous horizon, and simulate the new states:
$$x^{i}_{j} = f_{d}(x^{i}_{j-1},u^{i-1}_{end}) \quad \forall j\in \mathbb{Z}_{H_{i-1},H_{i}}$$
	- This method usually generates a more accurate state prediction, but requires some computation time. 
	- I is usually a good idea if the horizon is short, and one expects large disturbances.
- **Use the state reference:**
	- If one expects that the horizon is long enough that the states approach the reference by the end of the horizon, then a good guess is to simply use the reference as the appended variables:
$$x^{i}_{j} = x^{ref,i}_{j} \quad \forall j\in \mathbb{Z}_{H_{i-1},H_{i}}$$
	- This needs no computation time, and provides a guess that is feasible with respect to the dynamics, AND is likely close to the optimal prediction.

