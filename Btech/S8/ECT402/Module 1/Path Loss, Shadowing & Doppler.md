---
tags:
  - wireless_communication
  - propagation
  - path_loss
  - doppler
---

# Path Loss, Shadowing & Doppler Shift

These are fundamental **propagation effects** that affect signal strength and quality in wireless channels.

---

## 1. Path Loss

> **Path Loss** is the attenuation of signal strength as radio waves propagate through free space or medium.

### Free Space Path Loss (FSPL)

For isotropic antennas (theoretical, equal power in all directions):

$$P_{r} = P_{t} \cdot \left( \frac{\lambda}{4\pi d} \right)^2$$

In dB form:

$$L_{fs}(dB) = 20\log_{10}(d) + 20\log_{10}(f) - 147.55$$

where:
- $d$ = distance in meters
- $f$ = frequency in Hz
- $\lambda$ = wavelength = $c/f$

### Key Observations

| Distance Doubles | Frequency Doubles |
|-----------------|-------------------|
| **-6 dB loss** (1/4 power) | **-6 dB loss** (1/4 power) |
| Or **-20 dB/decade** | Or **-20 dB/decade** |

> ⚡ The $\mathbf{20\log_{10}(d)}$ term shows path loss increases as **20 dB for every decade** of distance.

### Path Loss Exponent

In real environments, path loss follows:

$$L(d) = L(d_0) + 10n\log_{10}\left(\frac{d}{d_0}\right)$$

where $n$ = path loss exponent:

| Environment | n |
|-------------|---|
| Free space | 2 |
| Urban (NLOS) | 2.7-3.5 |
| Obstructed | 3-5 |
| In-building | 1.6-1.8 |

---

## 2. Shadowing (Slow Fading)

> **Shadowing** occurs when large obstacles (buildings, hills) block the signal, causing additional attenuation beyond path loss.

```
Signal Path:
Tx ───╲─────────────╱───Rx
      ╲ Shadowed ╱
       ╲  Zone  ╱
        ╲──────╱  <-- Additional loss due to obstruction
```

### Characteristics

- **Log-normal distribution**: Shadowing loss in dB follows Gaussian distribution
- **Standard deviation** (σ): Typically 4-12 dB in urban areas
- **Correlation distance**: Spatial correlation typically 10-50 m for vehicles

### Combined Model

$$P_{r}(d) = P_{t} - L_{fs}(d) - X_{\sigma}$$

where $X_{\sigma}$ ~ N(0, σ²) is shadowing loss in dB.

---

## 3. Doppler Shift

> **Doppler Shift** is the apparent change in frequency due to relative motion between transmitter and receiver.

### Formula

$$f_d = \frac{v}{\lambda} \cos\theta = f_c \cdot \frac{v}{c} \cos\theta$$

where:
- $v$ = relative velocity (m/s)
- $f_c$ = carrier frequency (Hz)
- $c$ = speed of light (3×10⁸ m/s)
- $\theta$ = angle of arrival relative to direction of motion

### Maximum Doppler Shift

$$f_{d_{max}} = \frac{v}{\lambda} = \frac{v f_c}{c}$$

### Practical Examples

| Speed | Frequency | Doppler Shift |
|-------|-----------|---------------|
| 100 km/h | 900 MHz (2G) | ±83 Hz |
| 120 km/h | 1800 MHz (3G) | ±200 Hz |
| 60 km/h | 2.4 GHz (Wi-Fi) | ±133 Hz |
| 500 km/h | 6 GHz (5G) | ±3333 Hz |

### Effect on Signal

- **Time-varying channel**: Channel changes as mobile moves
- **Doppler spread**: Causes frequency dispersion in channel
- **Coherence time**: Time over which channel remains approximately constant

$$T_c \approx \frac{0.423}{f_{d_{max}}}$$

- **Fast fading**: When symbol duration > coherence time
- **Slow fading**: When symbol duration < coherence time

---

## 4. Combined Channel Model

The complete large-scale path loss model:

$$P_{r}(d)_{dB} = P_{t_{dB}} - L_{fs}(d)_{dB} - X_{\sigma_{dB}}$$

```
Total Signal Loss:

┌─────────────────────────────────────────────┐
│                                             │
│   FSPL    +    Shadowing    +    Doppler    │
│  (Distance)   (Obstructions)   (Motion)    │
│                                             │
│   d⁻ⁿ         Log-normal         f_d       │
│                                             │
└─────────────────────────────────────────────┘
```

---

## Summary

| Effect | Cause | Variation Time | Mitigation |
|--------|-------|---------------|------------|
| **Path Loss** | Distance | Deterministic | Power control, cell planning |
| **Shadowing** | Obstacles | Slow (~dB/sec) | Diversity, averaging |
| **Doppler** | Motion | Fast (~Hz-msec) | Equalizer, interleaving |

---

**Related Topics:**
- [[Cellular System Design Fundamentals]]
- [[Interference and System Capacity]]
- [[Significance of Diversity in Wireless Communication]]
- [[MultiCarrier Modulation]]