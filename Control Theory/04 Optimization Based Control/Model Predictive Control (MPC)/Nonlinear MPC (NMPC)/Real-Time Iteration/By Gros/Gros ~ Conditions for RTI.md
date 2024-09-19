---
tags:
  - Optimization/NMPC/RTI
Note Author:
  - Trym A. Gabrielsen
Theory Author:
  - Sébastien Gros
Reviewed By:
---
The [[Gros ~ RTI|RTI]] scheme will closely track the global optimum of the corresponding [[Gros ~ NMPC||NMPC]] scheme if:
1) the RTI scheme is [[Warm Start|warm started]] at the global optimum
2) the sampling frequency is sufficiently high
3) the state-reference and true/estimated state values do not 'jump' from on sample to the next
	- they remain the same/change gradually between samples
4) The [[Optimal Control Problem]] underlying the NMPC/RTI schemes fulfills the [[Second Order Sufficient Condition (SOSC)]] for every feasible initial condition $x_{0}^{i}$
5) the global optimum depends continuously on the initial state; $x^{i}_{0}$, and reference $x^{ref,i}$

