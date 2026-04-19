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

*See:* [[Module 2/2 Ray Model|Two-Ray Model]]

---

## Free Space Path Loss (FSPL)

This model predicts the received signal strength when there is a **clear,** **unobstructed line-of-sight path between the transmitter and receiver**, such as in satellite communications.
- It describes the absolute best-case scenario for how a signal travels through a perfect vacuum without any obstacles like buildings or trees.

In this model, the signal's power decreases proportionally to the square of the distance ($d^2$) and the square of the frequency ($f^2$). The standard Friis transmission formula for calculating received power ($P_r$) is:

$$P_r = \frac{P_t G_t G_r \lambda^2}{(4\pi d)^2 L}$$

_(Where $P_t$ is transmit power, $G_t$ and $G_r$ are the antenna gains, $\lambda$ is the wavelength, $d$ is distance, and $L$ is the system loss factor)_.

---
Calculating path loss in decibels (dB):

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


## Shadowing

**Shadowing** = Random attenuation due to obstacles (buildings, hills, trees).

- **Distribution:** Log-normal
- **σ (typical):** 4-12 dB (urban)

See: [[Fading Theory]] - Large-scale fading

---

## Related Notes

- [[Module 2/Module 2]] - Syllabus
- [[Fading Theory]] - Large-scale fading (shadowing)
- [[Important Topics/Path loss and Shadowing]] - Brief overview
- [[Module 2 PYQ]] - PYQs on path loss
- [[Doppler Shift]] - Time variation
- [[Shannon Capacity]] - Capacity theorem