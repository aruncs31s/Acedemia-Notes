---
tags:
  - ECT401
module: 1
---

# Half-Wave Dipole (Far Field Derivation)
Length $l = \lambda/2$.

**Far field electric field:** $E_\theta = \frac{60 I_0}{r} \frac{\cos((\pi/2)\cos\theta)}{\sin\theta} e^{j(kr - \omega t)}$

**Directivity:** 2.15 (3.4 dB)

**Radiation resistance:** 73 ohms

**Detailed Derivation:**
1. Current distribution: $I(z) = I_0 \cos(kz)$ for z from -λ/4 to λ/4.
2. Vector potential similar.
3. Integral: $\int I(z) e^{j k z \cos\theta} dz = I_0 \int_{-\lambda/4}^{\lambda/4} \cos(kz) e^{j k z \cos\theta} dz$.
4. Evaluate using trigonometric identities.
5. Result: $E_\theta = j \frac{60 I_0}{r} \frac{\cos((\pi/2)\cos\theta)}{\sin\theta} e^{j(kr - \omega t)}$.

**Directivity:** Calculated from pattern factor.

**Radiation Resistance:** 73 Ω, standard value for half-wave dipole.
