---
tags:
  - Optimization/QP
Note Author:
  - Trym A. Gabrielsen
Theory Author: 
Reviewed By:
---

$$\text{(QP):}\quad \min_{z\in\mathbb{R}^{n_z}} ~z^{\top}Gz+c^{\top}z\quad s.t. \quad A_{eq}z = b_{eq}\, , \quad A_{in}z \geq b_{in}$$ ^QP


where
- $z\in \mathbb{R}^{n_z}$ is the decision vector
- $G \in \mathbb{R}^{n_z\times n_z}$ is the cost/objective matrix
- $c\in \mathbb{R}^{n_z}$ is the cost/objective vector
- $A_{eq}\in \mathbb{R}^{n_{eq}\times n_z}$ is the equality constraint matrix
- $b_{eq} \in \mathbb{R}^{n_{eq}}$ is the equality constraint vector
- $A_{in}\in \mathbb{R}^{n_{in}\times n_z}$ is the inequality constraint matrix
- $b_{in} \in \mathbb{R}^{n_{in}}$ is the inequality constraint vector


**Remarks:**
- An LP is technically a QP, with $G=[0]$, but we often do not include LPs in the notion of a QP.