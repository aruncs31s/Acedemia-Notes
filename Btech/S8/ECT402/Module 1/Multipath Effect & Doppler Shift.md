---
banner: "https://images.unsplash.com/photo-1583602621722-cbd1130b210b?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
banner_y: 0.116
tags:
  - wireless_communication
  - multipath
  - fading
---

# Multipath Effect & Doppler Shift

> **Multipath** is the phenomenon where radio signals reach the receiver via multiple paths due to reflection, diffraction, and scattering.

---

## 1. Multipath Effect

### How Multipath Occurs

```
Transmitter (Tx)
      │
      ├──► Path 1 (Direct/LoS) ──►────────► Receiver
      │
      ├──► Path 2 (Reflection) ───►───►
      │
      ├──► Path 3 (Diffraction) ─────────►    (constructive/destructive 
      │                                      interference)
      └──► Path 4 (Scattering) ────►─────►
```

### Causes of Multipath

| Mechanism | Description | Example |
|-----------|-------------|---------|
| **Reflection** | Signal bounces off surfaces | Buildings, vehicles |
| **Diffraction** | Signal bends around edges | Building corners, hills |
| **Scattering** | Signal scatters in many directions | Rough surfaces, foliage |

### Multipath Parameters

#### Time Dispersion
- **Delay Spread (τ_rms)**: RMS delay of multipath components
- **Maximum Excess Delay (τ_max)**: Delay of last significant echo

| Environment | τ_rms |
|-------------|-------|
| Indoor | 10-100 ns |
| Urban | 1-10 μs |
| Rural | 0.1-1 μs |

#### Coherence Bandwidth
Frequency range over which channel is approximately flat:

$$B_c \approx \frac{1}{5\tau_{rms}}$$

| Condition | Coherence Bandwidth |
|-----------|--------------------|
| Flat fading | $B > B_c$ |
| Frequency-selective fading | $B < B_c$ |

---

## 2. Types of Fading

### 2.1 Small-Scale Fading (Multipath Fading)

> Rapid signal variations due to multipath interference

#### Flat Fading
- Signal bandwidth < coherence bandwidth
- All frequency components affected equally
- No distortion, only amplitude variation

#### Frequency-Selective Fading
- Signal bandwidth > coherence bandwidth
- Different frequencies experience different attenuation
- Causes **Inter-Symbol Interference (ISI)**

### 2.2 Large-Scale Fading

> Slow variations due to path loss and shadowing (covered in [[Path Loss, Shadowing & Doppler Shift]])

---

## 3. Doppler Shift

> **Doppler Shift** is the apparent frequency change due to relative motion between Tx and Rx.

### Formula

$$f_d = \frac{v}{\lambda} \cos\theta = f_c \cdot \frac{v}{c} \cos\theta$$

where:
- $v$ = velocity of mobile (m/s)
- $\lambda$ = wavelength = $c/f_c$
- $\theta$ = angle between motion and signal direction

### Maximum Doppler Shift

$$f_{d_{max}} = \frac{v f_c}{c} = \frac{v}{\lambda}$$

### Example: Cellular Systems

| Technology | Frequency | Velocity | Max Doppler |
|------------|-----------|----------|-------------|
| 2G (GSM) | 900 MHz | 100 km/h | ~83 Hz |
| 3G | 2100 MHz | 120 km/h | ~233 Hz |
| 4G | 2600 MHz | 100 km/h | ~240 Hz |
| 5G | 3.5 GHz | 500 km/h | ~1625 Hz |

---

## 4. doppler Spread & Coherence Time

> **Doppler Spread (B_d)** is the range of doppler shifts from multipath components

$$B_d = 2 f_{d_{max}}$$

### Coherence Time (T_c)
Time over which channel response is highly correlated:

$$T_c \approx \frac{9}{16\pi f_{d_{max}} \approx \frac{0.423}{f_{d_{max}}}$$

### Fading Classification

| Condition | Symbol Period (T_s) | Relationship |
|------------|---------------------|--------------|
| **Fast Fading** | $T_s > T_c$ | Channel changes within symbol |
| **Slow Fading** | $T_s < T_c$ | Channel quasi-static |

```
Fast Fading:     Slow Fading:
│                 │
├─────┐     ┌─────┤     │       Channel changes
│     │     │     │     │       within symbol
│ ▓▓▓ │     │ ▓▓▓ │     │       → causes distortion
│  ▓▓│     │ ▓▓▓ │     │       
┴─────┴     ┴─────┴     │      Channel ~ constant
 symbol              symbol     within symbol
                     
Fast fading           Slow fading
```

---

## 5. Rayleigh & Rician Fading

### Rayleigh Fading
- No direct (LoS) component
- All multipath components are reflected/diffracted
- Amplitude follows Rayleigh distribution

$$p(r) = \frac{r}{\sigma^2} e^{-r^2/2\sigma^2}$$

### Rician Fading
- Direct (LoS) component present + multipath
- Amplitude follows Rician distribution
- K-factor: Ratio of LoS to scattered power

$$K(dB) = 10\log_{10}\left(\frac{A^2}{2\sigma^2}\right)$$

where $A$ = amplitude of direct component

| K-factor | Environment |
|----------|------------|
| K → -∞ dB | Rayleigh (no LoS) |
| K ≈ 0 dB | Heavy multipath |
| K >> 0 dB | Strong LoS (satellite) |

---

## 6. Mitigation Techniques

| Technique | Approach |
|-----------|----------|
| **Equalizers** | Compensate for ISI caused by delay spread |
| **OFDM** | Divide bandwidth into flat-fading subcarriers |
| **Diversity** | Multiple antennas/paths for reliability |
| **RAKE Receiver** | Combine multipath components |
| **Error Correction** | FEC to correct burst errors |
| **Interleaving** | Spread errors across time |

---

## 7. Combined Channel Model

```
Total Fading = Large-Scale × Small-Scale
                  │
                  ├── Path Loss (d⁻ⁿ)
                  ├── Shadowing (log-normal)
                  └── Multipath (Rayleigh/Rician)
```

---

## Summary

| Parameter | Symbol | Unit | Typical Values |
|-----------|--------|------|---------------|
| Delay spread | τ_rms | ns/μs | 10 ns - 10 μs |
| Coherence bandwidth | B_c | MHz | 0.1 - 20 MHz |
| Doppler spread | B_d | Hz | 10 - 2000 Hz |
| Coherence time | T_c | ms | 0.1 - 100 ms |

---

**Related Topics:**
- [[Cellular System Design Fundamentals]]
- [[Significance of Diversity in Wireless Communication]]
- [[Path Loss, Shadowing & Doppler Shift]]
