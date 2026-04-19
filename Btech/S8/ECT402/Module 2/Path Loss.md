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

# Path Loss

**Path Loss** = Signal attenuation as it travels from transmitter to receiver through free space.

---

## Free Space Path Loss (FSPL)

$$PL_{dB} = 20\log_{10}\left(\frac{4\pi d}{\lambda}\right)$$

Or in terms of frequency:
$$PL_{dB} = 20\log_{10}(d) + 20\log_{10}(f) - 147.55$$

---

## Friis Transmission Formula

$$P_r = P_t G_t G_r \left(\frac{\lambda}{4\pi d}\right)^2$$

**With loss factor L:**
$$P_r = \frac{P_t G_t G_r \lambda^2}{(4\pi d)^2 L}$$

Where:
- $P_t$ = Transmit power
- $P_r$ = Received power
- $G_t$ = Transmit antenna gain
- $G_r$ = Receive antenna gain
- $\lambda$ = Wavelength
- $d$ = Distance
- $L$ = System loss factor

---

## Two-Ray Model

For ground-reflected signals (near ground):

$$P_r = P_t G_t G_r \frac{h_t^2 h_r^2}{d^4}$$

- $h_t$ = Transmit antenna height
- $h_r$ = Receive antenna height

**Breakpoint distance:**
$$d_{bp} = \frac{4 h_t h_r}{\lambda}$$

| Region | Path Loss Exponent |
|--------|-------------------|
| Free space (d < d_bp) | 2 |
| Two-ray (d > d_bp) | 4 |

---

## Shadowing

**Shadowing** = Random attenuation due to obstacles (buildings, hills, trees).

- **Distribution:** Log-normal
- **σ (typical):** 4-12 dB (urban)

See: [[Fading]] - Large-scale fading

---

## Related Notes

- [[Module 2/Module 2]] - Syllabus
- [[Module 2/Fading]] - Large-scale fading (shadowing)
- [[Important Topics/Path loss and Shadowing]] - Brief overview
- [[Module 2 PYQ]] - PYQs on path loss
- [[Fading]] - Large-scale fading
- [[Doppler Shift]] - Time variation (Module 2)