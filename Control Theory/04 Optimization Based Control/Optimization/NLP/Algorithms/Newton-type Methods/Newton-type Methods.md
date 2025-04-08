---
tags: []
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By: 
Relevant Papers:
---
The "[[Newton Method]]" is a numerical procedure for finding roots of a nonlinear function. The ideal is to linearize the function, i.e. constructing a first order Taylor approximation, and solving for the root of the linearization:
$$\frac{\partial f}{\partial x}\bigg|_{x_{k}} (x_{k+1} - x_{k}) + f(x_{k}) = 0$$
$$\implies x_{k+1} = x_{k}-\frac{\partial f}{\partial x}\bigg|_{x_{k}}^{-1}f(x_{k})$$
Under some conditions:
$$k\rightarrow \infty \implies f(x_{k}) \rightarrow 0$$
An important condition for the procedure to give converging iterates is that the initial guess, $x_{0}$, is sufficiently close to a root.


## Newton-type Methods for NLPs
Newton's method can also be employed to solve NLPs. The idea is that we can search for KKT points by simply using Newton's method to find roots of the [[KKT Conditions (First-Order Necessary Conditions)|KKT vector]], which is the list of KKT conditions for an equality constrained NLP. 
Newton's method applied to the KKT vector results in the [[KKT system]], which is used in a plethora of applications involving NLP solvers, solution tracking algorithms, and similar. 
