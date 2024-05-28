#Theory/Lemma 
#resources/Lecture/Loria
Consider: ![[Consider - Cascade Interconnection (Time-Invariant)#^ae7b80]]
Let $\theta_1$, $\theta_2$ be 
- continuous
- non-decreasing 
and assume that 
$$ |g_1(x_1,x_2)| \leq \theta_1(|x_2|)|x_1| + \theta_2(|x_2|) $$then:    *(see [[Lyapunov Stability]])*
$$
 \begin{align}
 \text{GAS}_{\Sigma_1} &+ ~\,\text{GES}_{\Sigma_2} & \implies \text{GAS}_{\Sigma_1\rightarrow\Sigma_2} \\
 \text{GAS}_{\Sigma_1} &+ \text{(GAS+LES)}_{\Sigma_2} & \implies \text{GAS}_{\Sigma_1\rightarrow\Sigma_2} \\
 \text{GES}_{\Sigma_1} &+ ~\,\text{GES}_{\Sigma_2} & \implies \text{GES}_{\Sigma_1\rightarrow\Sigma_2}
 \end{align}
 $$
*(Alternative format):*  
- GAS$_{\Sigma_1}$ +   GES$_{\Sigma_2}$            $\implies$ GAS$_{\Sigma_1\rightarrow\Sigma_2}$
- GAS$_{\Sigma_1}$ +  (GAS+LES)$_{\Sigma_2}$  $\implies$ GAS$_{\Sigma_1\rightarrow\Sigma_2}$
- GES$_{\Sigma_1}$ +   GES$_{\Sigma_2}$            $\implies$ GES$_{\Sigma_1\rightarrow\Sigma_2}$



# Idea
We want to regard the stability properties of this system, such as ISS, GAS, etc...
We notice that for the system to be ISS, it seems like the growth of $f_1(\cdot)$ must be faster than that of $g_1(\cdot)$, when far enough from the origin. This results in the linear growth condition.