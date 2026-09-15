---
banner: "https://images.unsplash.com/photo-1583602621722-cbd1130b210b?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
banner_y: 0.116
---
# Cyclic Prefix and Peak-to-Average-Power-Ratio

---
banner: "https://images.unsplash.com/photo-1583602621722-cbd1130b210b?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
banner_y: 0.116

## Cyclic Prefix

> [!NOTE]
> The cyclic prefix (CP) is a copy of the last part of the OFDM symbol that is prepended to the beginning of each symbol. It serves multiple critical functions in OFDM systems.

### Purpose of Cyclic Prefix

1. **Eliminate Inter-Symbol Interference (ISI)**
   - When $T_{cp} \geq \tau_{max}$, all multipath components arrive within the CP duration
   - No energy from previous symbol spills into current symbol

2. **Convert Linear to Circular Convolution**
   - Linear convolution: $y[n] = x[n] * h[n]$
   - With CP: effectively becomes circular convolution
   - Enables simple frequency-domain equalization

3. **Preserve Orthogonality**
   - Maintains subcarrier orthogonality despite multipath
   - Prevents inter-carrier interference

4. **Symbol Timing Acquisition**
   - CP provides known pattern for frame detection
   - Helps receiver synchronize to symbol boundaries

### CP Duration Selection

$$T_{cp} \geq \tau_{max}$$

where $\tau_{max}$ is the maximum channel delay spread.

| Channel Type | Typical τ_max | CP Duration |
|--------------|---------------|-------------|
| Indoor | 0.1-1 μs | 0.8 μs |
| Urban | 1-5 μs | 4.7 μs |
| Hilly terrain | 5-20 μs | 16.7 μs |

### CP Overhead

$$\text{Overhead} = \frac{T_{cp}}{T_u + T_{cp}} \times 100\%$$

> [!TIP]
> Typical CP overhead is 10-25% of symbol duration.

### Spectral Efficiency with CP

$$\eta = \frac{N}{N + N_{cp}} = \frac{T_u}{T_u + T_{cp}}$$

For $N_{cp} = N/4$ (25% CP): $\eta = 80\%$

---

## Peak-to-Average-Power-Ratio (PAPR)

> [!WARNING]
> PAPR is a major challenge in OFDM systems. When multiple subcarriers add constructively, the instantaneous power can be very high compared to the average power.

### Definition

$$PAPR = \frac{\max_{0 \leq n < N} |x[n]|^2}{E[|x[n]|^2|]}$$

In dB:
$$PAPR_{dB} = 10 \log_{10}(PAPR)$$

### Why PAPR is High in OFDM

The OFDM signal is the sum of $N$ independent subcarriers:

$$x[n] = \frac{1}{N} \sum_{k=0}^{N-1} X[k] e^{j 2\pi kn/N}$$

By the **Central Limit Theorem**, for large $N$, the real and imaginary parts of $x[n]$ become Gaussian distributed. The instantaneous amplitude follows a Rayleigh distribution, leading to high peaks.

### Distribution of PAPR

For $N$ subcarriers with i.i.d. QAM symbols:

$$P(PAPR > \lambda) \approx 1 - (1 - e^{-\lambda})^{N}$$

> [!EXAMPLE]
> For $N = 256$ and $\lambda = 10$ (10 dB):
> $$P(PARP > 10 \text{ dB}) \approx 1 - (1 - e^{-10})^{256} \approx 1 - 0.9996^{256} \approx 99.99\%$$

This means almost every OFDM symbol will have PAPR > 10 dB!

### Problems Caused by High PAPR

| Issue | Impact |
|-------|--------|
| Power amplifier non-linearity | Spectral regrowth, in-band distortion |
| Reduced amplifier efficiency | Battery drain, heat issues |
| ADC/DAC dynamic range | Quantization noise |
| Intermodulation distortion | EVM degradation |

### PAPR Reduction Techniques

#### 1. Clipping and Filtering

```python
# Simple clipping
if |x[n]| > threshold:
    x[n] = threshold * sign(x[n])
```

> [!CAUTION]
> Clipping causes in-band distortion and out-of-band noise.

#### 2. Selective Mapping (SLM)

- Generate $U$ different phase sequences
- Select sequence with lowest PAPR
- Requires side information

#### 3. Partial Transmit Sequence (PTS)

- Divide subcarriers into $V$ subgroups
- Find optimal phase rotation to minimize PAPR

#### 4. Tone Reservation (TR)

- Reserve $R$ subcarriers for PAPR reduction
- No data on reserved tones

| Technique | PAPR Reduction | Complexity | Distortion |
|-----------|-----------------|------------|------------|
| Clipping | High | Low | Yes |
| SLM | Moderate | High | No |
| PTS | High | High | No |
| TR | Moderate | Medium | No |

---

## Summary

| Parameter | Cyclic Prefix | PAPR |
|-----------|---------------|------|
| Purpose | ISI elimination, circular convolution | High peak problem |
| Trade-off | Spectral efficiency | Power amplifier linearity |
| Typical value | 10-25% CP | 8-13 dB for 256 subcarriers |
| Key requirement | $T_{cp} \geq \tau_{max}$ | Minimize without distortion |

> [!KEY POINT]
