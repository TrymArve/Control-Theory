---
tags: 
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
The ***real-time dilemma*** is the dilemma one faces when having to choose between
- an exact/optimal control action based on outdated information
- and an inexact/sub-optimal control action based on up-to-date information.

The dilemma arises from the computation time of a control action, and is a major design choice in optimization based control, such as MPC.

When a new state estimate is available, one may spend much time computing the optimal control action, during which the system evolves further, rendering the estimate outdated by the time the control action is available. On the other hand, if one chooses to limit the time spent computing a control action, one may not have the time to compute an optimal control action, and must accept one that is sub-optimal The dilemma then arises as:
- Is it better to control optimally, but based on old estimates, or to control sub-optimally based on new estimates?

In general, the answer is going to lie somewhere in between, but it is not obvious how to find the best balance.