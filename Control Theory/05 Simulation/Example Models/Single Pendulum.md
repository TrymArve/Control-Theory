---
tags:
  - Dynamic-Model
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---

## System
Consider:
![[ExMod - Pendulum on Cart.pdf]]

$$\begin{align*}
\phi : & \quad \text{angle of pendulum}~(\phi=0 \implies \text{up-right position})\\
d\phi : & \quad \text{anglular speed of pendulum}~(d\phi \equiv \dot{\phi})\\
L:& \quad \text{length of pendulum}\\
m_{\phi}: & \quad \text{mass of pendulum}\\
g: & \quad \text{gravitational field strength (pointing downwards)}
\end{align*}$$
## Dynamics
$$q = \begin{bmatrix}\phi  \\ \dot{\phi} \end{bmatrix},\quad \dot{q} = f(q,u)$$
$$\ddot{\phi} = \frac{-u_{\phi} + Lgm\sin(\phi)}{mL^{2}}$$
## MATLAB CODE
``` MATLAB
% states
phi     = casadi.SX.sym('phi');  %[radians]
dphi    = casadi.SX.sym('dphi'); %[radians/s]

% inputs
u       = casadi.SX.sym('uphi'); %[Nm] (moment on pendulum)

% parameters
L       = 0.8;  %[m]
m       = 5;    %[kg]
gravity = 9.81; %[m/s^2]

% pendulum angular acceleration
ddphi = (-u_phi + L*gravity*m*sin(phi))/(L^2*m)

% state vector
q = [phi;
     dphi];

% dynamics (dq = f(q,u))
f = [dphi;
     ddphi];
```
