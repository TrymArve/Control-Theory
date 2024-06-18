---
tags:
  - Optimization
  - Optimization/NMPC
  - Optimization/LMPC
Note Author:
  - Trym A. Gabrielsen
Reviewed By:
---

Full notation [[Optimization|here]]

On the planned operating interval; $$\text{Operating Time Interval:}\quad t\in[0,T]$$ of a process, we typically define a set of sampling times; $$\text{sample times:}\quad \tilde{t} \triangleq \{t_{0}=0,~t_{1},~t_{2},~t_{3},~\dots,~t_{n-1},~t_{N}=T\}$$and corresponding state and input variables, to represent the state and input values at the sampling times, f.ex:
$$\begin{align*}
\text{Reference:}& \quad
 \begin{cases}
x^{ref}= \{x^{ref}_{0},x^{ref}_{1},x^{ref}_{2},x^{ref}_{3},x^{ref}_{4},x^{ref}_{5},x^{ref}_{6},x^{ref}_{7},x^{ref}_{8},x^{ref}_{9},x^{ref}_{N=10}\}\\[0.1cm]
u^{ref}= \{u^{ref}_{0},u^{ref}_{1},u^{ref}_{2},u^{ref}_{3},u^{ref}_{4},u^{ref}_{5},u^{ref}_{6},u^{ref}_{7},u^{ref}_{8},u^{ref}_{9}\}
\end{cases}\\[0.5cm]
\text{Predicted:} &\quad
\begin{cases}
\tilde{x}= \{\tilde{x}_{0},\tilde{x}_{1},\tilde{x}_{2},\tilde{x}_{3},\tilde{x}_{4},\tilde{x}_{5},\tilde{x}_{6},\tilde{x}_{7},\tilde{x}_{8},\tilde{x}_{9},\tilde{x}_{N=10}\}\\[0.1cm]
\tilde{u}= \{\tilde{u}_{0},\tilde{u}_{1},\tilde{u}_{2},\tilde{u}_{3},\tilde{u}_{4},\tilde{u}_{5},\tilde{u}_{6},\tilde{u}_{7},\tilde{u}_{8},\tilde{u}_{9}\}
\end{cases}
\end{align*}$$
Upon controlling the system with MPC, we only consider an excerpt of this interval, called the ***"horizon"***, which is a connected subset of the sampling times. At time $t_{i}$, we, f.ex., consider the following horizons:
$$\begin{align*}
\text{Time Horizon:}&\quad \tilde{t}^{i} &&\triangleq \{t_{i},t_{i+1},t_{i+2},\dots,t_{i+H_{i}}\}\\[0.1cm]
\text{(reference) State horizon:}&\quad x^{ref,i} &&\triangleq \{x^{ref}_{i},x^{ref}_{i+1},x^{ref}_{i+2},\dots,x^{ref}_{i+H_{i}}\}\\
\text{(reference) Input horizon:}&\quad u^{ref,i} &&\triangleq \{u^{ref}_{i},u^{ref}_{i+1},u^{ref}_{i+2},\dots,u^{ref}_{i+H_{i}-1}\}\\
\text{(predicted) State horizon:}&\quad \tilde{x}^{i} &&\triangleq \{\tilde{x}_{i},\tilde{x}_{i+1},\tilde{x}_{i+2},\dots,\tilde{x}_{i+H_{i}}\}\\
\text{(predicted) Input horizon:}&\quad \tilde{x}^{i} &&\triangleq \{\tilde{u}_{i},\tilde{u}_{i+1},\tilde{u}_{i+2},\dots,\tilde{u}_{i+H_{i}-1}\}
\end{align*}$$
To refer to the $j^{\text{th}}$ sample within the horizon considered at time $t_{i}$, we use: $$x^{i}_{j}$$ thus we have $$\tilde{x}^{i}_{j} = \tilde{x}_{i+j}$$