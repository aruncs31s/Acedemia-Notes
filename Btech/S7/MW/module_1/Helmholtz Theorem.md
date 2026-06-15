---
tags:
  - ECT401
module: 1
---

# Helmholtz Theorem
Helmholtz theorem states that any vector field that satisfies certain conditions can be decomposed into the sum of an irrotational (curl-free) vector field and a solenoidal (divergence-free) vector field.

For electromagnetic fields, it allows decomposition into Transverse Electric (TE) and Transverse Magnetic (TM) modes.

### Derivation
Consider a vector field $\vec{A}$ that is twice differentiable and vanishes at infinity.

$\vec{A} = \vec{A}_1 + \vec{A}_2$, where $\nabla \times \vec{A}_1 = 0$ (irrotational) and $\nabla \cdot \vec{A}_2 = 0$ (solenoidal).

Using vector identities and Green's theorem, we can show that such a decomposition is possible.

In waveguides, this leads to TE and TM modes.

**Detailed Derivation:**
1. Define $\vec{A}_1 = \nabla \phi$, where $\nabla^2 \phi = \nabla \cdot \vec{A}$.
2. Then $\vec{A}_2 = \vec{A} - \vec{A}_1$, and show $\nabla \cdot \vec{A}_2 = 0$.
3. For uniqueness, boundary conditions are needed.

**Importance:** Fundamental in solving wave equations in bounded regions.
