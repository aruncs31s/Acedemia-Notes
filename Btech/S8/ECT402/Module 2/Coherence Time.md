---
id: Coherence Time
aliases: []
tags:
  - academics
  - btech
  - s8
  - ect402
dg-publish: true
---

# Coherence Time ($T_c$)

## Definition

**Coherence Time** is the time duration over which the wireless channel appears "constant" — the channel impulse response does not change significantly.

It is the **time domain dual of Doppler spread**, used to characterize the time-varying nature of a channel's frequency dispersiveness in the time domain.

At its core, coherence time defines the **time duration over which two received signals have a strong potential for amplitude correlation**. This means that if two signals arrive at the receiver with a time separation greater than the coherence time, they will be affected differently by the channel.

In a physical sense, it represents the **time-scale at which fading occurs**, such as the time it takes for a moving receiver to travel from a peak to a valley in a signal interference pattern.

## Formula

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

Where $D_s$ = Doppler spread, $J_0$ = zeroth-order Bessel function

## Physical Meaning

- Channel samples taken within $T_c$ are **correlated** (similar)
- Channel samples taken $> T_c$ apart are **uncorrelated** (independent fading)

## Fast vs Slow Fading

The relationship between channel coherence time ($T_c$) and symbol period ($T_s$) determines the type of small-scale fading:

| Condition | Fading Type |
|----------|-----------|
| $T_s < T_c$ | Slow fading (channel constant during symbol) |
| $T_s > T_c$ | Fast fading (channel varies during symbol) |

Where $T_s$ = symbol duration

### Fast Fading
- Channel impulse response changes very rapidly within a single symbol
- $T_s > T_c$
- Requires adaptive equalization, diversity

### Slow Fading
- Channel variations are much slower than baseband signal variations
- $T_s \ll T_c$
- Easier to equalize demodulate

## Relationship to Doppler Spread

**Inversely proportional** — bigger Doppler spread means shorter coherence time.

| Parameter | Formula | Meaning |
|-----------|---------|---------|
| Max Doppler | $f_m = v/\lambda$ | Frequency spread |
| Coherence Time | $T_c \approx 0.423/f_m$ | Time selectivity |
| Product | $f_m T_c \approx 0.423$ | Time-bandwidth tradeoff |

## Example

At $f_c = 2$ GHz, vehicle speed = 60 km/h:

$$\lambda = \frac{c}{f} = \frac{3\times10^8}{2\times10^9} = 0.15\text{ m}$$
$$v = 60 \text{ km/h} = 16.7 \text{ m/s}$$
$$f_m = \frac{v}{\lambda} = \frac{16.7}{0.15} = 111 \text{ Hz}$$
$$T_c \approx \frac{0.423}{111} = 3.8 \text{ ms}$$

## Practical Impact

- **Higher velocity** → larger $f_m$ → **smaller $T_c$** → faster fading
- Adaptive systems need update rates $> 1/T_c$
- Channel estimation must refresh within $T_c$
- Diversity/interleaving must span $> T_c$ for effective diversity gain

## Links

- [[Module 2/Fading Theory]]
- [[Module 2/Module 2 PYQ]]