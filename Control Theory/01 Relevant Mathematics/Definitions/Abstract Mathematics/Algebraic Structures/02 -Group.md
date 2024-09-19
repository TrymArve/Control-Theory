---
tags: 
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---
**Definition:**
A *group* is a [[01 Magma (binar) (Groupoid)|magma]]; $(\mathbb{S},\oplus)$, such that:
- **(Associativity)** $$a\oplus(b\oplus c) = (a\oplus b)\oplus c \quad \forall a,b,c \in \mathbb{S}$$
- **(Identity)** $$\exists e \in \mathbb{S} : \quad (e\oplus a =  a \oplus e = a) \wedge (\centernot\exists \tilde{e} \in \mathbb{S}: (\tilde{e}\centernot=e) \wedge (\tilde{e}\oplus a =  a \oplus \tilde{e} = a)) \quad \forall a\in \mathbb{S}$$
- **(Inverse)** $$\exists b\in \mathbb{S}: a\oplus b = b \oplus a = e \quad \forall a \in \mathbb{S} \quad\text{($e$ is the identity)}$$



**Remarks:**
- For example; the magma $(\mathbb{R},+)$ is a group, since all the conditions above are satisfied.
	- $0$ is the identity
	- $-a$ is the inverse of $a$
- The "identity" property simply states that there is an element such that the output of the binary operation is simply the other input-element, AND that this element is the only one with this property.
