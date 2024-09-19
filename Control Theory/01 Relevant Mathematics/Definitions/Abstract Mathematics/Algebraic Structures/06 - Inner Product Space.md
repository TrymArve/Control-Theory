---
tags: []
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
An *inner product space* is an ordered septuple $(\mathbb{F},\oplus,\circ,\mathbb{V},+,\cdot,\langle\cdot,\cdot\rangle)$ such that
- $(\mathbb{F} = \mathbb{R}) \vee (\mathbb{F} = \mathbb{C})$
- $(\mathbb{F},\oplus,\circ,\mathbb{V},+,\cdot)$ forms a [[05 -Vector Space|vector space]]
- and $\langle\cdot,\cdot\rangle: \mathbb{V}\times \mathbb{V} \mapsto \mathbb{F}$ is an [[Inner Product|inner product]]


**Remarks:**
- Note that an inner product space is only defined over the reals or the complex numbers. Thus an inner product space is not completely general, as both [[04 -Field|fields]] and [[05 -Vector Space|vector spaces]] are
- Notice that the inner product can easily be used to define a metric, via a norm; $$d(x,y) \triangleq \sqrt{\langle x-y ~,~x-y\rangle}$$thus naturally allowing us to define a metric space $(\mathbb{V},d(x,y))$.