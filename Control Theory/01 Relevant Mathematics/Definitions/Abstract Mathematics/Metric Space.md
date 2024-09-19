---
tags: []
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
**Definition:**
A *metric space* is an ordered pair $(\mathbb{S},d)$, where
- $\mathbb{S}$ is a [[Set|set]]
- $d$ is a [[Metric|metric]] on $\mathbb{S}$   (distance function)
satisfying:
- $\forall(x,y,z)\in \mathbb{S}$
	1) $d(x,x) = 0$   (distance to itself is zero)
	2) $x \centernot= y \implies d(x,y) > 0$  (no two elements can be in the same 'place', and all distances are positive)


**Intuition:**
A *metric space* is a pair consisting of 
- a [[Set]]
- a [[Metric]] / notion of distance between elements of the set

In a sense, a *metric space* is a set, where all elements have been given a 'placement' relative to the other elements. The elements have been given an 'order'.

F.ex., the real numbers have been given order when placed on a number-line, which naturally gives rise to a way of measuring the distance between each number. Mathematically, it is the other way around: the set of real numbers is paired with the metric "absolute value of their difference"; $d(x,y)\triangleq|x-y|$, which imposes the linear structure we draw as the 'number-line'.

