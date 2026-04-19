---
id: Path Loss
tags:
  - academics
  - btech
  - s8
  - ect402
  - module2
dg-publish: true
---

# Two-Ray Model

The **Two-Ray Ground Reflection Model** considers **two propagation paths**:
1. **Direct Line-of-Sight (LOS)** path
2. **Ground-reflected path** (reflected off the ground)

This model is more accurate than free space model for practical terrestrial communication where antennas are mounted above ground level.

---

## How It Works

When transmitting and receiving antennas are positioned above a flat ground surface:
- The radio signal reaches the receiver through both a **direct path** and a **path reflected off the ground**
- At large distances, the difference in path length between direct and reflected paths becomes very small relative to the wavelength
- Because the reflection causes the **phase to reverse** (180° phase shift), the direct and reflected waves begin to **cancel each other out**
- This causes **destructive interference** → rapid power decay

---

## Received Power Formula

$$P_r = P_t G_t G_r \frac{h_t^2 h_r^2}{d^4}$$

Where:
- $P_t$ = Transmit power
- $P_r$ = Received power
- $G_t$ = Transmit antenna gain
- $G_r$ = Receive antenna gain
- $h_t$ = Transmit antenna height
- $h_r$ = Receive antenna height
- $d$ = Distance between antennas

---

## Breakpoint Distance (Crossover Distance)

The distance at which the propagation mechanism changes from free space to ground-reflected:

$$d_{bp} = \frac{4 h_t h_r}{\lambda}$$

Or equivalently:
$$d_c = \frac{4\pi h_t h_r}{\lambda}$$

| Region | Condition | Path Loss Exponent | Power Decay |
|--------|-----------|-------------------|-------------|
| **Near Region** (d < d_bp) | Free space dominant | 2 | $P_r \propto 1/d^2$ |
| **Far Region** (d > d_bp) | Two-ray dominant | 4 | $P_r \propto 1/d^4$ |

---

## Key Characteristics

### 1. Path Loss Exponent Change
- **Near distance (d < d_bp):** Constructive/destructive interference causes ripple patterns
- **Far distance (d > d_bp):** Fast power falloff ($d^4$) — worse than free space ($d^2$)

### 2. Ground Reflection Coefficient
- For **perfect conductor ground**: $\Gamma \approx -1$ (180° phase shift)
- For **real ground**: $\Gamma$ depends on frequency, polarization, and ground properties

### 3. Phase Cancellation
- The ground reflection reverses the phase of the electric field
- At far distances, the direct and reflected signals become nearly equal in amplitude but opposite in phase
- Results in destructive interference and rapid signal decay

---

## Frequency Range

The Two-Ray model is significant at **VHF and above (30 MHz - 3 GHz)** where:
- Wavelength is small enough for ground reflections to cause interference effects
- Antennas are typically mounted above ground level

---

## Applications

- **Line-of-sight radio communication** — Microwave relay links
- **Wireless communication systems** — Cellular and Wi-Fi in suburban/rural areas
- **Broadcasting** — FM and TV signals over flat terrain
- **Mobile communication** — Practical path loss prediction

---

## Limitations

1. **Requires smooth reflecting surface** — Rough terrain disrupts coherent reflection
2. **Signal fading due to interference** — Constructive/destructive interference causes rapid fading
3. **Dependent on ground characteristics** — Varies with conductivity/permittivity (soil, water, urban)
4. **Polarization sensitivity** — Reflection coefficients differ for vertical/horizontal polarization

---

## Comparison: Free Space vs Two-Ray

| Property | Free Space | Two-Ray (Far) |
|----------|-----------|--------------|
| Power Decay | $1/d^2$ | $1/d^4$ |
| Path Loss Exponent | 2 | 4 |
| Used For | Satellite, LOS | Terrestrial mobile |
| Condition | Clear path | Ground reflection present |

---

## Related Notes

- [[Module 2/Path Loss|Path Loss]] — Free Space Path Loss, Friis Equation
- [[Module 2/Module 2 PYQ]] — PYQs on Two-Ray Model
- [[Module 5/propagation/Plane earch reflection|Plane Earth Reflection]] — More detailed ground reflection theory
- [[PYQs/most_asked_questions]] — Two-Ray crossover distance formula