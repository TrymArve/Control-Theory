---
tags:
  - Unfinished
Note Author:
  - Trym A. Gabrielsen
Theory Author:
  - Moritz Diehl
Reviewed By: 
Relevant Paper:
  - '"Real-time optimization and nonlinear model predictive control of processes governed by diﬀerential-algebraic equations" (2002)'
  - '"Nominal Stability of the Real-Time Iteration Scheme for Nonlinear Model Predictive Control" (2005)'
  - '"A Real-Time Iteration Scheme for Nonlinear Optimization in Optimal Feedback Control" (2005)'
---
The Real-Time Iteration (RTI) scheme is a method of approximating the [[ideal NMPC]] controller. The idea is that the given a good initial guess, the solution of [[ideal NMPC]] is approximated by a single Newton-type iteration at each sampling instance. The approximation causes sub-optimality and even infeasibility, although the computation time is drastically reduced compared to a classical NMPC algorithm, which iterates until convergence. 
The RTI scheme can therefore be seen as an algorithm that continually provides control updates at very high speeds, by continuously solving an optimization problem, which itself is continuously changing as the system state continuously changes.

# Real-Time Iterations

## Classical NMPC
In classical NMPC, we attempt to approximate the  [[ideal NMPC]] controller by solving the NLP to very high accuracy and after some time, when the solution has converged, delivering the corresponding control input:
![[Gros ~ NMPC#^NMPC]]
This methods yield very good approximations of the optimal control input, but in practice, the control input is outdated by the time the computations are done. Therefore this approach is not suitable for systems where the state varies rapidly.
## RTI Approximations

