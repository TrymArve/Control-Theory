---
tags: []
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By: 
Relevant Papers:
---
**Warning:**
- This is NOT a derivative in the [[Derivative (Total)|traditional]] sense !


Consider a function 
$$f:\mathbb{D}_{1}\times \mathbb{D}_{2}\mapsto \mathbb{O}$$
Define another function;
$$r(x) \triangleq f(x,y_{0})$$
where $y_{0} \in \mathbb{D}_{2}$ is a constant in the domain of the function.

**Definition:**
$$\frac{\partial f}{\partial x}\Bigg|_x \triangleq \lim_{\Delta x \rightarrow 0} \frac{r(x + \Delta x) - r(x)}{\Delta x}$$

**Remarks:**
- The partial derivative is closer to the concept of antiderivative, then to an actual derivative.
- The partial derivative differentiates the function as if all other arguments are kept constant.
- Usually, partial derivatives only appear on the context of computing total derivatives.