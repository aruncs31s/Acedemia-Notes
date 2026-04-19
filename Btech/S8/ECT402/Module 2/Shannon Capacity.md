---
id: Shannon Capacity
tags:
  - academics
  - btech
  - s8
  - ect402
  - module2
dg-publish: true
---

# Shannon Capacity

**Shannon Capacity** = Maximum data rate for reliable communication over a noisy channel.

---

## Formula

$$C = B \log_2(1 + \text{SNR})$$

Where:
- $B$ = Bandwidth (Hz)
- $\text{SNR}$ = Signal-to-noise ratio

**AWGN form:**
$$C = W \log_2\left(1 + \frac{\bar{P}}{N_0 W}\right)$$

Where:
- $W$ = Channel bandwidth
- $\bar{P}$ = Average received power
- $N_0$ = Noise power spectral density

---

## Key Principle

If Data Rate > C → **Errors become unavoidable**

No coding, modulation, or tech can exceed this limit.

---

## Bandwidth vs Power Tradeoff

| Parameter | Relationship |
|-----------|--------------|
| Bandwidth | Capacity grows linearly (doubling B → doubling C) |
| Power | Capacity grows logarithmically (3 dB SNR → +B bits/s at high SNR) |

**Spectral Efficiency:**
$$\eta = \log_2(1 + \text{SNR}) \text{ bits/s/Hz}$$

---

## Practical Example

For B = 1 MHz, SNR = 100 (20 dB):

$$C = 1 \times 10^6 \times \log_2(101) \approx 6.66 \text{ Mbps}$$

---

## Related Notes

- [[Module 2/Module 2 PYQ]] - PYQs on capacity
- [[Module 2/Path Loss]] - Path loss affects SNR