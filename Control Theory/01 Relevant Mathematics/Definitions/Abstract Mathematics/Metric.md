---
tags: []
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
A *metric*  or *distance function*, is a function that maps to elements of any set $\mathbb{S}$, to a positive real number:
$$d:\mathbb{S} \times \mathbb{S}\mapsto \mathbb{R}_{+}$$
and that satisfies, for $x,y,z \in \mathbb{S}$:
- $d(x,x) = 0$   
- $x \centernot= y \implies d(x,y) \centernot= 0$    ("positivity")
- $d(x,y) = d(y,x)$   ("symmetric")
- $d(x,z) \leq d(x,y) + d(y,z)$  ("triangle inequality")


2) (the distance between an object an itself is zero)
3)  (distance between distinct objects is not zero)
	(notice that the $d$ maps to the positive reals, thus the distance between two distinct objects is strictly positive)
4) (the distance between two objects is the minimum distance traversed when navigating from one to the other.)

**Remarks:**
- Note that the set $\mathbb{S}$ can be any arbitrary set, and does not have to only consist of numbers. 
	- One may define the set $\mathbb{S} \triangleq \{green, blue, yellow\}$
	- and the metric: $d(x,y) \triangleq$ the minimum number of rooms I must go through in my house, to get from a room with x-colored walls, to a room with y-colored walls.
	- Then,  the newly ordered set of colors is a [[Metric Space]].
