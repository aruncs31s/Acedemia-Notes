---
id: Statistical Multipath Channel Models
aliases: []
tags:
  - academics
  - btech
  - s8
  - ect402
dg-publish: true
---

# 2.2 Statistical Multipath Channel Models

In real wireless environments, signals reach the receiver via multiple paths due to reflection, diffraction, and scattering. This causes **multipath propagation** which leads to fading. Statistical models characterize these random channel behaviors.

---

## Time-Varying Channel Impulse Response

The wireless channel is modeled as a **linear time-varying (LTV) system**.

### Continuous-Time Model

$$
h(\tau, t) = \sum_{i=1}^{N(t)} a_i(t) e^{-j\phi_i(t)} \delta(\tau - \tau_i(t))
$$

Where:
- $a_i(t)$ = amplitude of $i^{th}$ path
- $\phi_i(t)$ = phase of $i^{th}$ path
- $\tau_i(t)$ = delay of $i^{th}$ path
- $N(t)$ = number of multipath components

### Key Parameters

| Parameter | Definition |
|-----------|------------|
| **Multipath Delay Spread** | Time difference between earliest and latest arriving paths |
| **Doppler Spread** | Spread in frequencies due to motion |
| **Coherence Time** | Time duration over which channel is "stationary" |
| **Coherence Bandwidth** | Frequency range over which channel is "flat" |

---

## Narrowband Fading

When signal bandwidth << coherence bandwidth, all multipath components arrive within the symbol duration → **flat fading**.

### Types of Narrowband Fading

#### 1. Rayleigh Fading
- No dominant line-of-sight (LOS) component
- Applicable to urban environments

$$
f_R(r) = \frac{r}{\sigma^2} e^{-r^2/2\sigma^2}, \quad r \geq 0
$$

**PDF of Envelope:**
- $r$ = signal envelope
- $\sigma^2$ = average received power

**CDF:**
$$
F_R(r) = 1 - e^{-r^2/2\sigma^2}
$$

#### 2. Rician Fading
- Dominant LOS component exists
- Common in suburban/microwave links

$$
f_R(r) = \frac{r}{\sigma^2} e^{-(r^2 + A^2)/2\sigma^2} I_0\left(\frac{rA}{\sigma^2}\right)
$$

Where:
- $A$ = amplitude of dominant path
- $I_0$ = modified Bessel function of first kind

**Rician Factor:** $K = \frac{A^2}{2\sigma^2}$ (ratio of LOS to scattered power)

- $K \to 0$ → Rayleigh
- $K \to \infty$ → No fading (deterministic)

---

---

## Discrete-Time Model

For digital communication, convert continuous-time channel to discrete-time tapped-delay-line:

$$y[m] = \sum_l h_l[m] \cdot x[m-l] + w[m]$$

Where:
- $h_l[m]$ = discrete channel filter tap
- $x[m]$ = transmitted symbol
- $y[m]$ = received symbol
- $w[m]$ = noise

By sampling at bandwidth W, physical paths are grouped into resolvable bins.

---

## Wideband Fading Models

When signal bandwidth > coherence bandwidth, different frequency components experience different gains → **frequency-selective fading**.

### Power Delay Profile (PDP)

Describes average power vs time delay:

$$
P(\tau) = E\{|h(\tau)|^2\}
$$

### Common Models

#### 1. Exponential PDP
$$
P(\tau) = \frac{1}{\tau_{rms}} e^{-\tau/\tau_{rms}}
$$
where $\tau_{rms}$ = RMS delay spread

#### 2. Uniform PDP
Equal power for all paths within delay window

---

## Delay Spread and Coherence Bandwidth

### Delay Spread Parameters

| Parameter | Formula | Significance |
|-----------|---------|--------------|
| **Mean Excess Delay** | $\bar{\tau} = \frac{\sum P(\tau_i)\tau_i}{\sum P(\tau_i)}$ | Average delay |
| **RMS Delay Spread** | $\sigma_\tau = \sqrt{\bar{\tau^2} - \bar{\tau}^2}$ | Spread of delays |
| **Maximum Excess Delay** | $\tau_m = \tau_N - \tau_1$ | Total span |

### Coherence Bandwidth ($B_c$)

Frequency range where channel response is correlated (almost flat).

$$
B_c \approx \frac{1}{5\sigma_\tau}
$$

**Rule of Thumb:**
- $B_s \ll B_c$ → Flat fading
- $B_s > B_c$ → Frequency-selective fading

Where $B_s$ = signal bandwidth

---

## Doppler Spread and Coherence Time

### Doppler Shift

When receiver/transmitter moves, apparent frequency changes:

$$
f_d = \frac{v}{\lambda} \cos\theta = f_m \cos\theta
$$

Where:
- $v$ = velocity (m/s)
- $\lambda$ = wavelength
- $f_m = \frac{v}{\lambda}$ = maximum Doppler frequency
- $\theta$ = angle of arrival

### Doppler Power Spectrum

For isotropic scattering (Clarke model):
$$
S(f) = \frac{1}{\pi f_m \sqrt{1 - (f/f_m)^2}}, \quad |f| \leq f_m
$$

**Jakes' Model** - Simplified version for simulation

### Coherence Time ($T_c$)

Time duration where channel characteristics remain correlated:

$$
T_c \approx \frac{0.423}{f_m}
$$

**Alternate form:**
$$
T_c = \sqrt{\frac{9}{16\pi f_m^2}} \approx \frac{0.423}{f_m}
$$

---

## Classification of Fading

### Based on Bandwidth: Flat vs Frequency-Selective

| Type | Condition | Effect |
|------|-----------|--------|
| **Flat Fading** | $B_s < B_c$ | No ISI, amplitude variation only |
| **Frequency-Selective** | $B_s > B_c$ | ISI present, different gains across frequencies |

### Based on Time: Slow vs Fast

| Type | Condition | Effect |
|------|-----------|--------|
| **Slow Fading** | $T_s < T_c$ | Channel varies slowly within symbol |
| **Fast Fading** | $T_s > T_c$ | Channel changes within symbol |

Where $T_s$ = symbol duration

### Combined Classification

| | Flat Fading | Frequency-Selective |

See also: [[Fading Theory]]

---

### Fading Classification Summary

```
Signal Bandwidth (Bs)
      │
      ├─── Bs < Bc ──── Flat Fading
      │         │
      │         ├─── Ts < Tc ──── Slow Flat Fading
      │         └─── Ts > Tc ──── Fast Flat Fading
      │
      └─── Bs > Bc ──── Frequency-Selective Fading
                │
                ├─── Ts < Tc ──── Slow Freq-Selective
                └─── Ts > Tc ──── Fast Freq-Selective
```

---

## Key Formulas Summary

1. **Rayleigh PDF:** $f_R(r) = \frac{r}{\sigma^2} e^{-r^2/2\sigma^2}$
2. **Doppler:** $f_d = f_m \cos\theta = \frac{v}{\lambda}\cos\theta$
3. **Coherence Bandwidth:** $B_c \approx \frac{1}{5\sigma_\tau}$
4. **Coherence Time:** $T_c \approx \frac{0.423}{f_m}$
5. **Discrete Model:** $y[n] = \sum_{k=0}^{L-1} h_k[n]x[n-k] + w[n]$

---

## PYQ Links

- [[October 2023 PYQ#3. How does fading occur? Derive the expression for doppler shift.]]
- [[May 2024.md#3. Multipath causing small-scale fading (3 Marks)]]
- [[October 2023 PYQ#14. (c) Time selective fading]]