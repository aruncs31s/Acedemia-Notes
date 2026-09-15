---
banner: "https://images.unsplash.com/photo-1583602621722-cbd1130b210b?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
banner_y: 0.116
id: Coherence
aliases: []
tags:
  - academics
  - btech
  - s8
  - ect402
dg-publish: true
---

# Coherence (Time & Bandwidth)

## Coherence Time ($T_c$)

### Definition
**Coherence Time** is the time duration over which the wireless channel appears "constant" — the channel impulse response does not change significantly.

It is the **time domain dual of Doppler spread**, used to characterize the time-varying nature of a channel's frequency dispersiveness in the time domain.

At its core, coherence time defines the **time duration over which two received signals have a strong potential for amplitude correlation**. This means that if two signals arrive at the receiver with a time separation greater than the coherence time, they will be affected differently by the channel.

In a physical sense, it represents the **time-scale at which fading occurs**, such as the time it takes for a moving receiver to travel from a peak to a valley in a signal interference pattern.

### Formula

$$T_c \approx \frac{0.423}{f_m} = \frac{0.423\lambda}{v}$$

Where:
- $f_m = \frac{v}{\lambda}$ = maximum Doppler frequency
- $v$ = velocity (m/s)
- $\lambda$ = wavelength

### Various Formulas (Different Correlation Levels)

| Formula | Correlation Level |
|---------|-------------------|
| $T_c \approx \frac{1}{f_m}$ | General approximation |
| $T_c = \frac{1}{4D_s}$ | Order of magnitude |
| $T_c = \frac{9}{16\pi f_m}$ | 50% correlation |
| $T_c \approx \frac{0.423}{f_m}$ | Geometric mean (most common) |
| $T_c = \frac{\pi D_s}{J_0^{-1}(0.05)}$ | 5% correlation (Clarke's model) |

### Physical Meaning

- Channel samples taken within $T_c$ are **correlated** (similar)
- Channel samples taken $> T_c$ apart are **uncorrelated** (independent fading)

### Slow vs Fast Fading

| Condition | Fading Type |
|----------|-----------|
| $T_s < T_c$ | Slow fading (channel constant during symbol) |
| $T_s > T_c$ | Fast fading (channel varies during symbol) |

### Relationship to Doppler Spread

**Inversely proportional** — bigger Doppler spread means shorter coherence time.

---

## Coherence Bandwidth ($B_c$)

### Definition
**Coherence Bandwidth** is the frequency range over which the wireless channel appears "flat" — the channel frequency response does not change significantly.

It is the **frequency domain dual of delay spread**, used to characterize the frequency dispersiveness of a channel in the frequency domain.

**Coherence bandwidth is a statistical measure** defining the range of frequencies over which a channel is considered to be "flat," meaning that two frequency components within this range have a strong potential for amplitude correlation. Within this bandwidth limit, the pattern of constructive and destructive interference does not change appreciably.

### Formula

$$B_c \approx \frac{1}{5\tau_{rms}}$$

Where $\tau_{rms}$ = RMS delay spread

### Various Formulas (Different Correlation Levels)

| Formula | Correlation Level |
|---------|-------------------|
| $B_c \approx \frac{1}{50\tau_{\tau}}$ | 90% correlation |
| $B_c \approx \frac{1}{5\sigma_{\tau}}$ | 50% correlation |
| $B_c \approx \frac{1}{2\pi \tau_{rms}}$ | Precise (50% correlation) |
| $B_c \approx \frac{1}{5\tau_{rms}}$ | Common approximation |

### Physical Meaning

- Frequency components within $B_c$ experience **similar channel gain** (flat fading)
- Frequency components $> B_c$ apart experience **different channel gains** (frequency-selective fading)

### Flat vs Frequency-Selective Fading

| Condition | Fading Type |
|-----------|-----------|
| $B_s < B_c$ | Flat fading (all frequencies affected equally) |
| $B_s > B_c$ | Frequency-selective fading (different gains) |

### Relationship to Delay Spread

**Inversely proportional** — larger delay spread means smaller coherence bandwidth.

---

## Comparison

| Property | Coherence Time | Coherence Bandwidth |
|----------|--------------|------------------|
| **Domain** | Time | Frequency |
| **Dual of** | Doppler spread | Delay spread |
| **Formula** | $T_c \approx 0.423/f_m$ | $B_c \approx 1/5\tau_{rms}$ |
| **Condition** | $T_s < T_c$ → slow | $B_s < B_c$ → flat |
| **Measures** | Time selectivity | Frequency selectivity |

---

## Key Parameters

### Mean Excess Delay

$$\bar{\tau} = \frac{\sum_i P_i \tau_i}{\sum_i P_i}$$

### RMS Delay Spread

$$\tau_{rms} = \sqrt{\bar{\tau^2} - \bar{\tau}^2}$$

Where $\bar{\tau^2} = \frac{\sum_i P_i \tau_i^2}{\sum_i P_i}$

### Max Doppler

$$f_m = \frac{v}{\lambda}$$

---

## Practical Examples

### Coherence Time
At $f_c = 2$ GHz, vehicle speed = 60 km/h:
$$\lambda = 0.15\text{ m}, \quad v = 16.7\text{ m/s}$$
$$f_m = \frac{16.7}{0.15} = 111 \text{ Hz}$$
$$T_c \approx \frac{0.423}{111} = 3.8 \text{ ms}$$

### Coherence Bandwidth
For urban environment with $\tau_{rms} = 3$ $\mu$s:
$$B_c \approx \frac{1}{5 \times 3 \times 10^{-6}} = 66.7 \text{ kHz}$$

---

## Related Notes

- [[Module 2/Module 2 PYQ]]
- [[Module 2/Fading Theory]]
- [[Fading Theory]]
- [[Doppler Shift]] - Coherence time related to Doppler
- [[Shannon Capacity]] - Capacity relates to bandwidth
