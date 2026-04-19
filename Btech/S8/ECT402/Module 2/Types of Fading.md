---
id: Types of Fading
aliases: []
tags:
  - academics
  - btech
  - s8
  - ect402
dg-publish: true
---

# Types of Fading in Wireless Systems

## Overview

Fading refers to the variation in signal strength (amplitude, phase) during propagation. It occurs due to multipath propagation and relative motion between transmitter and receiver.

Fading is classified along two axes:
1. **Scale**: Large-scale vs Small-scale
2. **Time**: Slow vs Fast
3. **Frequency**: Flat vs Frequency-selective

---

## 1. Large-Scale Fading

### Description
Signal strength variations over **large distances** (hundreds of wavelengths).

### Causes
- **Path loss**: Signal attenuates with distance ($d^{-n}$)
- **Shadowing**: Obstruction by buildings, hills, trees

### Characteristics
- Changes gradually over 10s-100s of meters
- Follows **log-normal distribution**
- Predictable (can be modeled)

### Impact
- Determines **cell coverage** and range planning
- Requires **link budget** margin for cell edge
- Not severely degrading on its own

---

## 2. Small-Scale Fading

### Description
Signal strength variations over **short distances** (few wavelengths).

### Causes
- **Multipath interference**: Multiple paths add constructively/destructively
- **Doppler effect**: Motion causes frequency shift

### Characteristics
- Rapid fluctuations (within meters)
- Follows **Rayleigh/Rician distribution**
- Harder to predict

### Impact
- **Severe signal degradation**
- Causes bit errors
- Requires mitigation (diversity, equalization)

---

## 3. Slow Fading

### Condition
$$T_s < T_c$$

(signal duration shorter than coherence time)

### What Happens
Channel appears **constant** during symbol transmission.

### Impact
- Easier to equalize
- Channel estimation valid
- Minimal ISI within symbol

---

## 4. Fast Fading

### Condition
$$T_s > T_c$$

(symbol duration longer than coherence time)

### What Happens
Channel **changes while transmitting** the symbol.

### Impact
| Problem | Effect |
|---------|--------|
| Outdated estimates | Channel tracking fails |
| Phase rotation | Carrier recovery errors |
| ISI within symbol | Detection errors |
| High error rate | Requires diversity |

### Mitigation
- Diversity techniques
- Interleaving + coding
- Adaptive equalization
- Lower symbol rate

---

## 5. Flat Fading

### Condition
$$B_s < B_c$$

(signal bandwidth narrower than coherence bandwidth)

### What Happens
**All frequency components** experience same channel gain.

### Impact
- No ISI between symbols
- Amplitude/phase distortion (same for all)
- Simple one-tap equalization
- Needs **fade margin**

---

## 6. Frequency-Selective Fading

### Condition
$$B_s > B_c$$

(signal bandwidth wider than coherence bandwidth)

### What Happens
**Different frequency components** experience different channel gains.

### Impact

| Problem | Effect |
|---------|--------|
| ISI | Symbols overlap |
| Amplitude distortion | Uneven across band |
| Phase distortion | Frequency-dependent |
| Requires | Multi-tap equalizer |

### Mitigation
- OFDM (subcarriers < B_c)
- Channel equalization
- Adaptive loading

---

## Classification Matrix

| | Flat Fading | Frequency-Selective |
|---|-------------|---------------------|
| **Slow** | Slow + Flat | Slow + Freq-Selective |
| **Fast** | Fast + Flat | Fast + Freq-Selective |

### Best Case
**Slow + Flat** — Channel constant, all frequencies equal

### Worst Case
**Fast + Frequency-Selective** — Channel varies rapidly, different gains across band

---

## Impact Summary Table

| Fading Type | Detection | Equalization | Data Rate | Mitigation |
|------------|-----------|--------------|----------|------------|
| Large-scale | Easy | Not needed | Limited | Link budget |
| Slow + Flat | Moderate | One-tap | Full | Fade margin |
| Fast + Flat | Hard | Tracking | Reduced | Diversity |
| Slow + Freq-Select | Moderate | Multi-tap | Reduced | OFDM |
| Fast + Freq-Select | Very hard | Adaptive | Very reduced | All techniques |

---

## Common Scenarios

| Environment | Typical Fading |
|--------------|----------------|
| Indoor static | Slow + Flat |
| Urban pedestrian | Fast + Flat |
| Indoor moving | Slow + Freq-Selective |
| Urban vehicle | Fast + Freq-Selective |

---

## Related Notes

- [[Module 2/Coherence Time]]
- [[Module 2/Coherence Bandwidth]]
- [[Module 2/Fading Theory]]