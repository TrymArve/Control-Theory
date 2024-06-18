---
tags:
  - NonlinearSystems/Definition
Note Author:
  - Trym A. Gabrielsen
Theory Author:
  - Antonio Loría
  - Ioel Malkin
Reviewed By:
---
The origin for $\dot{x} = f(t,x,0)$ is said to be ***Locally ISS** (totally stable)* iff
- The solutions, $x^\circ(t)$, of the system $\dot{x} = f(t,x,u),\quad x^\circ(t_\circ) = x_\circ$, are such that
	- $\forall~\epsilon>0$
		- $\exists~\delta>0 :$
$$ \max\{||x_\circ||,||u||_{\mathcal{L}_\infty}\} \leq \delta \quad \implies \quad ||x^\circ(t,u(t))|| \leq \epsilon \quad \forall t\geq t_0$$


**Intuition**
- For the system $\dot{x} = f(t,x,u)$,
	- small bounded inputs $u(t,x)$, and
	- small initial conditions $x_0$
	yield small state trajectories for all $t\geq t_0$.


**Reference:**
- I. Malkin. Ob ustochivosti pri postoyanno destvuyuschih vozmyscheniyah. Prikl.
Mat. i Mekh., Tom. VIII:241{245, 1944. In Russian. Engl. translation: On stability
under constantly acting disturbances.
- Antonio Loria's interpretation of the reference above is used as source of the definition.

**Remark:**
- Shares similarity with [[LISS - Local Input-to-State Stability]]

