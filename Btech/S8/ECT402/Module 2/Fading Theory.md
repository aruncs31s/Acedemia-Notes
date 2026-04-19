---
id: Fading Theory
aliases: []
tags:
  - academics
  - btech
  - s8
  - ect402
dg-publish: true
---

# Fading in Wireless Communications - Theory

See: [[Fading]]

---

## What is Fading?

**Fading** = Random variation in signal amplitude, phase, or angle of arrival as the signal propagates through the wireless channel.

Unlike wired channels, wireless signals don't travel along a single clean path. They bounce off buildings, trees, ground, and other objects, creating multiple "copies" that reach the receiver at different times.

---

## Causes of Fading

### 1. Multipath Propagation

See: [[Multipath Propagation]]

### 2. Relative Motion (Doppler Effect)

See: [[Doppler Shift]]

When transmitter/receiver moves, each multipath component experiences different Doppler shifts based on the angle of arrival.

### 3. Environmental Changes

- Moving objects (vehicles, people)
- Changing atmospheric conditions
- Seasonal changes (leaves vs bare trees)

---

## Types of Fading

### Large-Scale Fading

| Feature | Description |
|---------|-------------|
| **Scale** | Over hundreds of wavelengths |
| **Cause** | Path loss + shadowing |
| **Model** | Log-normal distribution |
| **Example** | Signal weakening as you move from city to suburb |

**Applications:**
- Cell radius planning
- Link budget calculations

### Small-Scale Fading

| Feature | Description |
|---------|-------------|
| **Scale** | Over few wavelengths (cm to m) |
| **Cause** | Multipath interference |
| **Model** | Rayleigh/Rician distribution |
| **Example** | Signal fluctuating while standing in one spot |

---

## Small-Scale Fading - Detailed

### Why Does It Happen?

When multiple copies of the same signal arrive at the receiver with different phases, they **add up**:

- **In-phase** → Constructive → Signal BOOST
- **Out-of-phase** → Destructive → Signal FADES

Since the relative phases change constantly (due to motion), the received signal amplitude fluctuates rapidly.

### The Mathematics

**Received signal (simplified):**

$$
r(t) = \sum_{i=1}^{N} a_i e^{j(\omega_d t + \phi_i)} \cdot s(t - \tau_i)
$$

For narrowband (all $\tau_i \approx \bar{\tau}$):

$$
r(t) \approx s(t - \bar{\tau}) \cdot \underbrace{\sum_{i=1}^{N} a_i e^{j\phi_i}}_{\text{Complex gain } h(t)}
$$

The complex gain $h(t)$ varies randomly → causes fading.

---

## Rayleigh Fading

### Scenario
- **No direct line-of-sight (NLOS)**
- Urban environments, indoor
- Many scatterers, no dominant path

### Derivation

Assume $N$ independent multipath components, each with:
- Random phase $\phi_i \sim U[0, 2\pi]$
- Similar amplitude (by central limit theorem)

The **envelope** $|h(t)|$ follows Rayleigh distribution:

$$
f_R(r) = \frac{r}{\sigma^2} e^{-r^2/2\sigma^2}, \quad r \geq 0
$$

### Properties

| Property | Expression |
|----------|------------|
| Mean | $\bar{r} = \sigma\sqrt{\pi/2}$ |
| Variance | $\text{Var}(r) = \frac{4-\pi}{2}\sigma^2$ |
| Median | $r_{med} = \sigma\sqrt{2\ln 2}$ |
| Mode | $\sigma$ |

### Power ( $|h|^2$ ) Distribution

Since $r = |h|$, power $P = r^2$ follows **exponential distribution**:

$$
f_P(p) = \frac{1}{2\sigma^2} e^{-p/2\sigma^2}
$$

---

## Rician Fading

### Scenario
- **Line-of-sight (LOS) component present**
- Suburban, highway, satellite links
- One strong path + many weak scatterers

### Model

Strong deterministic path + random scattered components:

$$
h(t) = \underbrace{A e^{j\phi_0}}_{\text{LOS}} + \underbrace{\sum_{i=1}^{N} a_i e^{j\phi_i}}_{\text{Scattered}}
$$

### Envelope Distribution

$$
f_R(r) = \frac{r}{\sigma^2} e^{-(r^2 + A^2)/2\sigma^2} \cdot I_0\left(\frac{rA}{\sigma^2}\right)
$$

Where $I_0$ = modified Bessel function of first kind (order 0)

### Rician K-Factor

$$
K = \frac{A^2}{2\sigma^2} = \frac{\text{LOS power}}{\text{Scattered power}}
$$

| K Value | Behavior |
|---------|----------|
| $K = 0$ | Rayleigh (no LOS) |
| $K \gg 1$ | Minimal fading (dominant LOS) |
| Typical (dB) | 4-10 dB for practical channels |

### Special Cases

- **High K**: $f_R(r) \approx \mathcal{N}(A, \sigma^2)$ (approximate Gaussian)
- **Low K**: Approaches Rayleigh

---

## Doppler Spread

### Origin

When receiver moves with velocity $v$, each multipath component experiences different Doppler shifts:

$$
f_{d,i} = \frac{v}{\lambda} \cos\theta_i = f_m \cos\theta_i
$$

Where:
- $f_m = v/\lambda$ = maximum Doppler frequency
- $\theta_i$ = angle of arrival of $i$th path

### Doppler Power Spectrum

The spectrum of the fading process is NOT flat - it's spread around the carrier.

**Clarke Model (theoretical):**

$$
S(f) = \frac{1}{\pi f_m \sqrt{1 - (f/f_m)^2}}, \quad |f| \leq f_m
$$

This gives **U-shaped** spectrum (for isotropic scattering).

### Practical: Jakes' Model

Simplified simulator-friendly version:

$$
h(t) = \sum_{n=1}^{N} c_n \cos(\omega_m t + \phi_n)
$$

Where coefficients $c_n$ designed to match Clarke's spectrum.

---

## Coherence Time & Time Selectivity

### Coherence Time ($T_c$)

Time interval over which channel impulse response is **correlated** (changes minimally).

$$
T_c \approx \frac{0.423}{f_m} = \frac{0.423\lambda}{v}
$$

**Physical meaning:** If you sample the channel at intervals < $T_c$, you'll get similar values.

### Relationship to Fading Rate

| Parameter | Expression | Meaning |
|-----------|------------|---------|
| $T_c \propto 1/f_m$ | Higher velocity → faster fading | More Doppler spread |
| $T_s$ vs $T_c$ | Symbol duration vs coherence time | Determines fast/slow |

### Time-Selective Fading

- **Fast fading**: Channel changes within one symbol ($T_s > T_c$)
- **Slow fading**: Channel constant over many symbols ($T_s < T_c$)

---

## Coherence Bandwidth & Frequency Selectivity

### Coherence Bandwidth ($B_c$)

Frequency range over which channel frequency response is correlated.

$$
B_c \approx \frac{1}{5\sigma_\tau} \quad \text{(for 50% correlation)}
$$

Or more precisely:
$$
B_c \approx \frac{1}{2\pi\sigma_\tau}
$$

### Delay Spread

- **$\tau_{max}$**: Maximum excess delay (first to last path)
- **$\sigma_\tau$**: RMS delay spread (standard deviation)

### Frequency-Selective Fading

- **Flat fading**: $B_s < B_c$ (narrowband signal)
- **Frequency-selective**: $B_s > B_c$ (wideband signal)

**Why frequency-selective?**
Different frequency components see different channel gains because different multipath contributions dominate at different frequencies.

---

## Fading Classification Summary

```
Signal Bandwidth (Bs)
      │
      ├─── Bs < Bc ──── Flat Fading
      │         │
      │         ├─── Ts < Tc ──── Slow Flat Fading
      │         │         Channel almost constant
      │         └─── Ts > Tc ──── Fast Flat Fading
      │                   Channel varies during symbol
      │
      └─── Bs > Bc ──── Frequency-Selective Fading
                │
                ├─── Ts < Tc ──── Slow Freq-Selective
                │         Deep fades at some frequencies
                └─── Ts > Tc ──── Fast Freq-Selective
                          Worst case: ISI + deep fades
```

---

## Fading Mitigation Techniques

### 1. Diversity

Send multiple copies via different:
- **Time** (interleaving, coding)
- **Frequency** (OFDM, frequency hopping)
- **Space** (MIMO, antenna switching)

### 2. Equalization

Compensate for ISI in frequency-selective channels:
- Linear: Zero-Forcing, MMSE
- Nonlinear: DFE, MLSE

### 3. Adaptive Techniques

- Modulation order adaptation
- Power control
- Antenna beamforming

---

## Key Formulas Summary

| Concept | Formula |
|---------|---------|
| Rayleigh PDF | $f_R(r) = \frac{r}{\sigma^2} e^{-r^2/2\sigma^2}$ |
| Rician PDF | $f_R(r) = \frac{r}{\sigma^2} e^{-(r^2+A^2)/2\sigma^2} I_0(\frac{rA}{\sigma^2})$ |
| Rician K | $K = A^2/2\sigma^2$ |
| Doppler | $f_d = f_m \cos\theta = (v/\lambda)\cos\theta$ |
| Coherence BW | $B_c \approx 1/5\sigma_\tau$ |
| Coherence Time | $T_c \approx 0.423/f_m$ |
| Max Doppler | $f_m = v/\lambda$ |

---

## Important Points to Remember

1. **Fading is random but predictable statistically** - we use distributions (Rayleigh/Rician) not deterministic models

2. **Multipath is the root cause** - different path lengths = different delays & phases

3. **Two dimensions of selectivity**:
   - Frequency (delay spread → $B_c$)
   - Time (Doppler spread → $T_c$)

4. **Trade-off**: Fast fading is harder to track but provides more diversity gain with coding

5. **Practical values**:
   - Urban delay spread: 1-10 μs
   - Vehicle at 60 km/h @ 2 GHz: $f_m$ ≈ 111 Hz, $T_c$ ≈ 3.8 ms