---
tags: []
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
**Definition:**
A [[Metric Space|metric space]] $(\mathbb{S},d)$ is *complete*, iff:
- Every [[Cauchy Sequence|cauchy sequence]] in $\mathbb{S}$ has a limit that is also in $\mathbb{S}$



**Intuition:**
A *Complete Metric Space* is a [[Metric Space]], $(\mathbb{S},d)$, where $\mathbb{S}$ contains the limit points of all [[Cauchy Sequence|cauchy sequences]] contained in $\mathbb{S}$.




**Examples:**

- **Rationals**
	- The [[Set|set]] of rational numbers, $\mathbb{Q}$, paired with the [[Metric|metric]]; $|\cdot|$ (absolute value), they form a metric space; $(\mathbb{Q},|\cdot|)$ 
	- An example of a [[Cauchy Sequence]] in $\mathbb{Q}$ is $$x_{0} = 1, \qquad x_{n+1} = \frac{x_{n}}{2} + \frac{1}{x_{n}}$$
	- We see that every element of the sequence is contained in $\mathbb{Q}$, since the elements remain rational.
	- However, the limit point; $$\begin{align}x_{lim} & = \frac{x_{lim}}{2} + \frac{1}{x_{lim}}\\ \implies x_{lim}^{2} & = 2 \\ \implies x_{lim} &= \sqrt{2} \end{align}$$ does not exists in $\mathbb{Q}$, since no rational number can be a square root of two.
	- We therefore see that the metric space $(\mathbb{Q},|\cdot|)$ is not complete.

- **Reals**
	- It turns out that all cauchy sequences of rational numbers that to not have a rational limit point, have irrational limit points.
	- By extending the rational set by the irrationals $\mathbb{I}$, such that one obtains the reals; $\mathbb{R} = \mathbb{Q} \cup \mathbb{I}$, all the rational cauchy sequences are contained in our set $\mathbb{R}$.
	- It turns out that all new cauchy sequences that are now possible because of the addition of the irrationals, also have limit points in the reals.
	- Therefore the metric space $(\mathbb{R},|\cdot|)$ is a complete metric space
	- In fact, there are exactly two different ways of completing the rationals, the other being with p-adic numbers, under a slightly different metric.