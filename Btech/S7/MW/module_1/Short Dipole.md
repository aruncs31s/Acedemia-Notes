---
tags:
  - ECT401
module: 1
---

# Short Dipole (Far Field Derivation)
A short dipole has length $l \ll \lambda$.

**Far field electric field:** $E_\theta = \frac{60 I_0 l}{r} \sin\theta e^{j(kr - \omega t)}$ (in V/m, for free space)

**Directivity:** 1.5 (1.76 dB)

**Radiation resistance:** $R_r = 80 \pi^2 (l/\lambda)^2$ ohms

**Detailed Derivation:**
1. Current distribution: $I(z) = I_0$ (constant for short dipole).
2. Vector potential: $\vec{A} = \frac{\mu_0}{4\pi} \int \frac{I(z') e^{-jkr'}}{r'} dz'$.
3. Far field: $E_\theta = -j \frac{\omega \mu_0}{4\pi r} e^{-jkr} \sin\theta \int_{-l/2}^{l/2} I(z) e^{j k z \cos\theta} dz$.
4. For short dipole, integral $\approx I_0 l$.
5. Thus, $E_\theta = j \frac{60 I_0 l}{r} \sin\theta e^{j(kr - \omega t)}$ (time convention).

**Directivity Calculation:** From pattern, D = 4π / $\Omega_A$, where $\Omega_A$ is beam solid angle.

**Radiation Resistance:** From $P_{rad} = (1/2) \operatorname{Re} \int \mathbf{E} \times \mathbf{H}^* dS$, leads to $R_r = 80 \pi^2 (l/\lambda)^2$.
