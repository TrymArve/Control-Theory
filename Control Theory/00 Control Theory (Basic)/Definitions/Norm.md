#Theory/Definition/Norm 

# Norm
A real valued function 
- $||\cdot||$ 
is a **norm on $\mathbb{X}$** iff:
- $\forall~x,y\in\mathbb{X}$
	- $\bigg\{ \begin{matrix} ||x|| > 0, &~ x\not=0 \\ ||x||=0,&~x=0 \end{matrix}$       *(positive definiteness)*
	- $||x+y|| \leq ||x||+||y||$   *(triangle inequality)*
	- $||\alpha x|| = |\alpha| ||x||$             *(homogeneity)*



# $p$-Norms on $\mathbb{R}^{n}$  (vector norms)
$$||x||_p \triangleq \bigg(\sum_{i=1}^{n} |x_i|^{p} \bigg)^{\frac{1}{p}} , \quad \forall p \in [1,\infty\rangle$$
$$||x||_\infty \triangleq \lim_{p\rightarrow\infty}||x||_p = \max_{i}(|x_i|) \quad \text{Largest element of x}$$
$$||x||_0 \triangleq \text{Number of non-zero elements of x}$$

**Note:**
- $||x||_1 = \sum_{i}^n |x|_i$         *(sum of elements)*
- $||x||_2 = \sqrt{\sum_i^n |x|_i^2}$    *(magnitude)*


# $\mathcal{L}_p$-Norms on $\mathbb{C}[a,b]$   (function norms)
$$ ||f||_{\mathcal{L}_p} \triangleq  \bigg(\int_{a}^{b} |f(\tau)|^{p} ~d\tau \bigg)^{\frac{1}{p}}, \quad \forall p \in [1,\infty\rangle$$
$$ ||f||_{\mathcal{L}_\infty} \triangleq  \sup_{a<t<b}|f(t)|$$
**note:**
- $||f||_{\mathcal{L}_1} = \int_{a}^{b} |f(\tau)| ~d\tau$          *(area under graph)*
- $||f||_{\mathcal{L}_2} = \sqrt{\int_{a}^{b} |f(\tau)|^2 ~d\tau}$    *(?? used in some lemmas)*

## $\mathcal{L}_p$-space
Select a function space $\mathbb{C}[a,b]$ and an $\mathcal{L}_p$-norm, these then form an $\mathcal{L}_p$-space:
- $\mathcal{L}_p$-space $\triangleq$ ( $\mathbb{C}[a,b]$, $\mathcal{L}_p$-norm)
- $f$ is an element of $\mathcal{L}_p$  ($f\in\mathcal{L}_p$) if its $\mathcal{L}_p$-norm is bounded
	- i.e. $f\in\mathcal{L}_p) \Longleftrightarrow ||f||_{\mathcal{L}_p} \leq L < \infty$


# Norms of $\mathbb{R}^{n\times m}$  (matrix norms)
$$ ||A||_p \triangleq \sup_{x\not=0} \frac{||Ax||_p}{||x||_p} \quad\bigg(=\max_{||x||_p=1}||Ax||_p \bigg) \quad  \forall~p\in[1,\infty\rangle$$
$$ ||A||_\infty \triangleq \max_i\bigg(\sum_{j=1}^n|a_{ij}|\bigg)$$
**Note:**
- $||A||_1 =  \max_j\bigg(\sum_{i=1}^n|a_{ij}|\bigg)$
- $||A||_2 = \sqrt{\lambda_{max}(A^\top A)}$ 



# $\mathcal{L}_p$-Norm for vector functions
consider:  $u:[a,b]\mapsto\mathbb{R}^m$
$$ ||u||_{\mathcal{L}_p} \triangleq  \bigg(\int_{a}^{b} ||u(\tau)||_{\bar{p}}^{p} ~d\tau \bigg)^{\frac{1}{p}}, \quad \forall p \in [1,\infty\rangle$$
where $||\cdot||_\bar{p}$  is any $\bar{p}$-norm on $\mathbb{R}^m$.
## $\mathcal{L}_p^m$-space    ($\mathcal{L}_p$-space, but for vector functions)
A vector function $u:[a,b]\mapsto\mathbb{R}^m$ is an element of $\mathcal{L}_p^m$-space iff:
- its $\mathcal{L}_p$-norm is bounded
- i.e. $$u\in\mathcal{L}_p^m \Longleftrightarrow ||u||_{\mathcal{L}_p} \leq L < \infty$$
**Note:**
- $u\in\mathcal{L}_2^m \Longleftrightarrow ||u||_{\mathcal{L}_2} = \sqrt{\int_{a}^{b}u(\tau)^\top u(\tau) ~d\tau} < \infty$     *(with $\bar{p}=2$,  implies finite integral/area under curve)*
- $u\in\mathcal{L}_\infty^m \Longleftrightarrow ||u||_{\mathcal{L}_\infty} = \sup_{a\leq t\leq b}||u(t)||_{\bar{p}} < \infty$       *([[Uniform Boundedness|uniformly bounded]] magnitude in t)*






