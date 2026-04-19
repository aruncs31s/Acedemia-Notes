---
banner: "https://images.unsplash.com/photo-1583602621722-cbd1130b210b?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
banner_y: 0.116
id: Doppler Shift
tags:
  - academics
  - btech
  - s8
  - ect402
  - module2
dg-publish: true
---

# Doppler Shift

The **Doppler shift** (or Doppler effect) is the observed change in frequency of a wave when there is relative motion between the transmitter and receiver.

---

## Formula

$$f_d = \frac{v}{\lambda} \cos\theta = f_m \cos\theta$$

For maximum Doppler (θ = 0°):
$$f_m = \frac{v}{\lambda} = \frac{v f_c}{c}$$

> [!callout] **What is f? Where did -ve sign go?**
> **f** = original transmit frequency (carrier f_c)
>
> **-ve sign** indicates direction:
> - **Negative** = moving **away** (frequency decreases)
> - **Positive** = moving **toward** (frequency increases)
>
> **f_m = v/λ** = **magnitude** (always positive)

Where:
- $v$ = velocity (m/s)
- $\lambda$ = **wavelength** = c/f_c (m)
- $f_c$ = **carrier frequency** (signal being transmitted)
- $c$ = speed of light (3×10⁸ m/s)
- $f_m$ = maximum Doppler shift

**Carrier frequency examples:**

| Application | f_c (carrier) | λ |
|-------------|--------------|-----|
| WiFi | 2.4 GHz | 12.5 cm |
| 4G LTE | 1.8 GHz | 16.7 cm |
| 5G | 3.5 GHz | 8.6 cm |
| FM Radio | 100 MHz | 3 m |
- $\theta$ = angle of arrival

---

## Key Relationships

| Parameter | Formula | Meaning |
|-----------|---------|---------|
| Coherence Time | $T_c \approx \frac{0.423}{f_m}$ | Time channel appears constant |
| Doppler Spread | $B_D = 2f_m$ | Spread in frequencies |

---

## Related Notes

- [[Statistical Multipath Channel Models]] - Doppler spread & coherence time
- [[Fading Theory]] - Doppler effects on fading
- [[Coherence]] - Coherence time related to Doppler
- [[Module 2 PYQ]] - PYQs on Doppler shift
