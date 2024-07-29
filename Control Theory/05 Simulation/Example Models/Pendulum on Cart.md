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

$$\begin{align*} x :& \quad \text{horizontal position of cart}\\
\phi : & \quad \text{angle of pendulum}~(\phi=0 \implies \text{up-right position})\\
dx :& \quad \text{horizontal speed of cart}~(dx \equiv \dot{x})\\
d\phi : & \quad \text{anglular speed of pendulum}~(d\phi \equiv \dot{\phi})\\
L:& \quad \text{length of pendulum}\\
m_{x}: & \quad \text{mass of cart}\\
m_{\phi}: & \quad \text{mass of pendulum}\\
g: & \quad \text{gravitational field strength (pointing downwards)}
\end{align*}$$
## Dynamics
$$q = \begin{bmatrix}x  \\ \phi  \\ \dot{x}  \\ \dot{\phi} \end{bmatrix},\quad u = \begin{bmatrix}u_{x}  \\ u_{\phi}\end{bmatrix},\quad \dot{q} = f(q,u)$$

$$\ddot{x} = \frac{gm_{\phi}\cos(\phi)\sin(\phi) -u_{x} - L^{-1}u_{\phi}\cos(\phi) - L\dot{\phi}^{2}m_{\phi}\sin(\phi)}{m_{x} + m_{\phi}-m_{\phi}\cos(\phi)^{2}}$$
$$\ddot{\phi} = \frac{-m_{x}u_{\phi} - m_{\phi}u_{\phi} - Lm_{\phi}u_{x}\cos(\phi) + Lgm_{\phi}^{2}\sin(\phi) - L^{2}\dot{\phi}^{2}m_{\phi}^2\cos(\phi)\sin(\phi) + Lgm_{x}m_{\phi}\sin(\phi))}{ L^{2}m_{\phi}(- m_{\phi}\cos(\phi)^{2} + m_{x} + m_{\phi})}$$
## MATLAB CODE
``` MATLAB
% states
x       = casadi.SX.sym('x');    %[m]
phi     = casadi.SX.sym('phi');  %[radians]
dx      = casadi.SX.sym('dx');   %[m/s]
dphi    = casadi.SX.sym('dphi'); %[radians/s]

% inputs
ux      = casadi.SX.sym('ux');   %[N]  (force in cart)
uphi    = casadi.SX.sym('uphi'); %[Nm] (moment on pendulum)

% parameters
L       = 0.8;  %[m]
mx      = 5;    %[kg]
mphi    = 2;    %[kg]
gravity = 9.81; %[m/s^2]

% cart acceleration
ddx = -(L*ux + uphi*cos(phi) + L^2*dphi^2*mphi*sin(phi) - L*gravity*mphi*cos(phi)*sin(phi))/(L*(- mphi*cos(phi)^2 + mx + mphi));

% pendulum angular acceleration
ddphi = -(mx*uphi + mphi*uphi + L*mphi*ux*cos(phi) - L*gravity*mphi^2*sin(phi) + L^2*dphi^2*mphi^2*cos(phi)*sin(phi) - L*gravity*mx*mphi*sin(phi))/(L^2*mphi*(- mphi*cos(phi)^2 + mx + mphi));

% state vector
q = [x;
    phi;
    dx;
    dphi];
    
% input vector
u = [ux; uphi];

% dynamics (dq = f(q,u))
f = [dx;
	 dphi;
	 ddx;
     ddphi];
```
