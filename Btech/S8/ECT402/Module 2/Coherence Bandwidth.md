---
id: Coherence Bandwidth
aliases: []
tags:
  - academics
  - btech
  - s8
  - ect402
dg-publish: true
---

# Coherence Bandwidth ($B_c$)

## Definition

**Coherence Bandwidth** is the frequency range over which the wireless channel appears "flat" — the channel frequency response does not change significantly.

It is the **frequency domain dual of delay spread**, used to characterize the frequency dispersiveness of a channel in the frequency domain.

**Coherence bandwidth is a statistical measure** defining the range of frequencies over which a channel is considered to be "flat," meaning that two frequency components within this range have a strong potential for amplitude correlation. Within this bandwidth limit, the pattern of constructive and destructive interference does not change appreciably.

At its core, coherence bandwidth defines the **frequency range over which two received signals have a strong potential for amplitude correlation**. This means that if two frequency components are separated by more than the coherence bandwidth, they will be affected differently by the channel.

In a physical sense, it represents the **frequency-scale at which frequency-selective fading occurs**, determined by the multipath delay spread.

## Key Characteristics

### 1. Inverse Relationship with Delay Spread

Coherence bandwidth is fundamentally **inversely proportional** to the multipath delay spread (or RMS delay spread, $\tau_{rms}$) of the channel.

### 2. Order of Magnitude Estimate

As a general rule of thumb, it is often approximated as:

$$W_c \approx \frac{1}{2\tau_d}$$

Where $\tau_d$ is the multipath delay spread.

### 3. Correlation-Based Definitions

The specific mathematical formula used to calculate coherence bandwidth depends on how strictly the correlation threshold is defined:

| Formula | Correlation Level |
|---------|-------------------|
| $B_c \approx \frac{1}{50\tau_{\tau}}$ | 90% correlation threshold |
| $B_c \approx \frac{1}{5\sigma_{\tau}}$ | 50% correlation threshold |
| $B_c \approx \frac{1}{2\pi \tau_{rms}}$ | Precise (50% correlation) |
| $B_c \approx \frac{1}{5\tau_{rms}}$ | Common approximation |

Where $\sigma_{\tau}$ = RMS delay spread

## Formula

$$B_c \approx \frac{1}{5\tau_{rms}}$$

Where $\tau_{rms}$ = RMS delay spread

### Various Formulas (Summary)

| Formula | Correlation Level |
|---------|-------------------|
| $B_c \approx \frac{1}{2\pi \tau_{rms}}$ | Precise (50% correlation) |
| $B_c \approx \frac{1}{5\tau_{rms}}$ | Common approximation |
| $B_c \approx \frac{1}{50\tau_{rms}}$ | Strict (90% correlation) |
| $B_c \approx \frac{1}{2\tau_{max}}$ | Using maximum excess delay |

## Physical Meaning

- Frequency components within $B_c$ experience **similar channel gain** (flat fading)
- Frequency components $> B_c$ apart experience **different channel gains** (frequency-selective fading)
- The pattern of constructive and destructive interference remains stable within this bandwidth

## Flat vs Frequency-Selective Fading

**Coherence bandwidth is the primary metric** used to determine if a signal will experience flat fading or frequency-selective fading.

| Condition | Fading Type |
|-----------|-----------|
| $B_s < B_c$ | Flat fading (all frequencies affected equally) |
| $B_s > B_c$ | Frequency-selective fading (different gains at different frequencies) |

Where $B_s$ = signal bandwidth

### Flat Fading
- All frequency components experience same amplitude/phase distortion
- No ISI if symbol period >> delay spread
- Simple one-tap equalization

### Frequency-Selective Fading
- Different frequency components experience different amplitude/phase
- Causes inter-symbol interference (ISI)
- Requires multi-tap equalization or OFDM

## Relationship to Delay Spread

**Inversely proportional** — larger delay spread means smaller coherence bandwidth.

| Parameter | Formula | Meaning |
|-----------|---------|---------|
| RMS Delay Spread | $\tau_{rms}$ | Time dispersion |
| Coherence Bandwidth | $B_c \approx 1/5\tau_{rms}$ | Frequency selectivity |
| Product | $B_c \tau_{rms} \approx 0.2$ | Time-frequency tradeoff |

## Key Parameters

### Mean Excess Delay

$$\bar{\tau} = \frac{\sum_i P_i \tau_i}{\sum_i P_i}$$

### RMS Delay Spread

$$\tau_{rms} = \sqrt{\bar{\tau^2} - \bar{\tau}^2}$$

Where $\bar{\tau^2} = \frac{\sum_i P_i \tau_i^2}{\sum_i P_i}$

### Maximum Excess Delay

$$\tau_{max} = \tau_{max} - \tau_{min}$$

## Example

For an urban environment with $\tau_{rms} = 3$ $\mu$s:

$$B_c \approx \frac{1}{5 \times 3 \times 10^{-6}} = 66.7 \text{ kHz}$$

A 200 kHz LTE channel ($B_s > B_c$) would experience frequency-selective fading, while a 10 kHz voice channel ($B_s < B_c$) would experience flat fading.

## Practical Impact

- **Larger delay spread** → **smaller $B_c$** → more frequency-selective
- OFDM divides bandwidth into subcarriers $< B_c$ for flat fading per subcarrier
- Channel equalization complexity depends on $B_s$ vs $B_c$
- Determines equalizer tap length requirements

## Coherence Bandwidth vs Coherence Time

| Property | Coherence Bandwidth | Coherence Time |
|----------|---------------------|------------------|
| Domain | Frequency | Time |
| Dual of | Delay spread | Doppler spread |
| Formula | $B_c \approx 1/5\tau_{rms}$ | $T_c \approx 0.423/f_m$ |
| Condition | $B_s < B_c$ → flat | $T_s < T_c$ → slow |
| Measures | Frequency selectivity | Time selectivity |

## Links

- [[Module 2/Coherence Time]]
- [[Module 2/Fading Theory]]
- [[Module 2/Statistical Multipath Channel Models]]