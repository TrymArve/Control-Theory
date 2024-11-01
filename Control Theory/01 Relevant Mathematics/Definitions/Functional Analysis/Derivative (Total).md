---
tags: 
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By: 
Relevant Papers:
---
Consider a function 
$$f:\mathbb{D}_{1}\times \mathbb{D}_{2}\mapsto \mathbb{O}$$
**Definition:**
$$\frac{df}{dx}\Bigg|_x \triangleq \lim_{\Delta x \rightarrow 0} \frac{f(x + \Delta x,y) - f(x,y)}{\Delta x}$$


**Remarks:**
- The number of input arguments is not constrained to two, and can be any number.
- The derivative can defined in the same way for each argument.
- The limit operation must be well defined on the function at $x$, in order for the derivative to be defined.
- By using limit-functions that approach from a specified direction, one can define "directional derivatives".

**Intuition:**
If the function $f$ is a map
$$(x,y) \mapsto z$$
then, the *(total) derivative* of $f$ w.r.t. its first argument ($x$) is then interpreted as the rate of change of the output ($z$) relative to the rate of change of the input ($x$).
