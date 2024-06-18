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
To get the $j^{\text{th}}$ element of the $i^{\text{th}}$ state horizon, we use $$x^{i}_{j} = x^{i-1}_{j+1}$$ such that the complete horizon becomes: $$\begin{align*}
x^{i} &=\{x^{i}_{0},x^{i}_{1},x^{i}_{2},\dots,x^{i}_{H_{i}}\}\\[0.1cm]
&=\{x^{i-1}_{1},x^{i-1}_{2},x^{i-1}_{3},\dots ,x^{i-1}_{H_{i-1}}; ~~x^{i}_{>H_{i-1}} \} \\[0.1cm]
&= \{x^{i-1}_{1,\dots,H_{i}}~,~~x^{i}_{>H_{i-1}}\}
\end{align*}$$, where the last $(H_{i}-H_{i-1})$ elements must be chosen by other means. Of course, if the current horizon is shorter that the previous; $(H_{i}-H_{i-1}) < 0$, then there are no additional elements to generate.
visually, we get: $$\{x_{0},x_{1},
\rlap{ \overbrace{ \phantom{x_{2},x_{3},x_{4},x_{5},x_{6},x_{7}} }^{x^{2}} }
x_{2},\underbrace{ x_{3},x_{4},x_{5},x_{6},x_{7},
x_{8} }_{x^{3}},x_{9},x_{10},x_{11},x_{N=12}\}$$
