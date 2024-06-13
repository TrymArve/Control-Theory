#NonlinearSystems/Assumption

Assume that the solutions of feedback-interconnected system ![[Consider - Feedback Interconnection#^feedback-interconnected-system]]
are defined on $[t_\circ,t_{max}\rangle$.

More precisely, that there exists:
- class $\mathcal{K}$ functions $\sigma_{12}, \sigma_{21}, \sigma_{22}$
- positive constants: $c_{1}, c_{2}$
- and a function $\sigma_{11}$, that is
	- non-decreasing
	- such that $\sigma_{11}(s) \rightarrow \infty$, as $s\rightarrow t_{max}$
such that
-  $\forall~t\in[t_0,t_{max}\rangle$
	$$
	\begin{align}
	(1a):\quad&& |x_1(t,t_\circ,x_\circ)| \leq &~ \sigma_{11}(t-t_\circ) + \sigma_{12}(|x_\circ|) + c_{2} \\[0.1cm]
	 (1b):\quad&& |x_2(t,t_\circ,x_\circ,x_1)| \leq &~ \sigma_{21}(t-t_\circ) + \sigma_{22}(|x_\circ|) + c_{2}
	\end{align}
	$$
