# Data Transmission using Multicarrier Modulation for Frequency-Selective Fading Channels

---

## Problem: Frequency-Selective Fading

> [!NOTE]
> In frequency-selective fading channels, different frequency components experience different attenuation due to multipath propagation. This causes **Inter-Symbol Interference (ISI)** and requires complex equalization in single-carrier systems.

### Channel Characteristics

The channel impulse response is given by:

$$h(\tau) = \sum_{i=0}^{L} h_i \delta(\tau - \tau_i)$$

where:
- $L$ = number of multipath components
- $\tau_i$ = delay of $i$-th path
- $h_i$ = complex amplitude of $i$-th path

### Key Parameters

| Parameter | Symbol | Definition |
|-----------|--------|------------|
| Coherence bandwidth | $B_c$ | $B_c \approx \frac{1}{\tau_{max}}$ |
| Coherence time | $T_c$ | Time over which channel is approximately constant |
| Delay spread | $\tau_{max}$ | $\tau_{max} = \max(\tau_i) - \min(\tau_i)$ |

> [!KEY POINT]
> When symbol duration $T_s \ll \tau_{max}$, the channel causes significant ISI.

---

## Solution: Multicarrier Modulation

### Basic Principle

Divide the total bandwidth into $N$ narrow subchannels:
- Each subcarrier has bandwidth $\Delta f \ll B_c$
- Each subcarrier experiences **flat fading** (not frequency-selective)
- ISI is eliminated by making symbol duration $T_s \gg \tau_{max}$

### Conditions for Flat Fading per Subcarrier

1. **Subcarrier spacing condition:**
$$\Delta f \ll B_c = \frac{1}{\tau_{max}}$$

2. **Symbol duration condition:**
$$T_s \gg \tau_{max}$$

---

## OFDM Implementation

### Transmitter

```
Data → Serial-to-Parallel → QAM Mapping → IFFT → Add CP → Parallel-to-Serial → Channel
```

**Mathematical Representation:**

1. **QAM Mapping:** Convert bits to complex symbols $X[k]$ for $k = 0, 1, ..., N-1$

2. **IFFT:** Apply $N$-point IFFT
$$x[n] = \frac{1}{N} \sum_{k=0}^{N-1} X[k] e^{j 2\pi kn/N}, \quad n = 0, 1, ..., N-1$$

3. **Add Cyclic Prefix:** Append CP of length $N_{cp} \geq L$

4. **Parallel to Serial:** Convert to serial for transmission

### Receiver

```
Received Signal → Serial-to-Parallel → Remove CP → FFT → Equalizer → QAM Demap → Parallel-to-Serial → Data
```

**Mathematical Representation:**

1. **Serial to Parallel:** Convert received serial to parallel blocks

2. **Remove CP:** Discard first $N_{cp}$ samples

3. **FFT:** Apply $N$-point FFT
$$Y[k] = \sum_{n=0}^{N-1} y[n] e^{-j 2\pi kn/N}$$

4. **One-Tap Equalization:** $\hat{X}[k] = \frac{Y[k]}{H[k]}$ (Zero-Forcing)

5. **QAM Demapping:** Recover bits

---

## Why Multicarrier Works

### Comparison Table

| Aspect | Single Carrier | Multicarrier (OFDM) |
|--------|---------------|-------------------|
| Equalizer | Complex (L taps) | Simple (1 tap per subcarrier) |
| ISI | Difficult to mitigate | Completely eliminated with CP |
| Noise enhancement | Significant | Minimal with MMSE |
| Receiver complexity | High | Low |
| Frequency diversity | Limited | Inherent across subcarriers |

### Mathematical Proof

Without CP (linear convolution):
$$y[n] = \sum_{l=0}^{L} h[l] x[n-l]$$

With CP removed, and $N_{cp} \geq L$:
$$y[n] = \sum_{l=0}^{L} h[l] x[(n-l) \mod N]$$

This is **circular convolution**, which in frequency domain becomes:
$$Y[k] = H[k] \cdot X[k]$$

Thus:
$$\hat{X}[k] = \frac{Y[k]}{H[k]} = X[k]$$

---

## Spectral Efficiency

> [!TIP]
> The cyclic prefix introduces overhead but maintains orthogonality.

**Spectral Efficiency:**

$$\eta = \frac{N}{N + N_{cp}} = \frac{T_u}{T_u + T_{cp}}$$

| CP Overhead | Spectral Efficiency |
|------------|-------------------|
| 10% | 90% |
| 20% | 83% |
| 25% | 80% |

---

## Example Calculation

> [!EXAMPLE]
> **Given:**
> - Maximum channel delay spread: $\tau_{max} = 5 \mu s$
> - Required data rate: $R = 10$ Mbps
> - Available bandwidth: $B = 10$ MHz
>
> **Solution:**
> - Choose subcarrier spacing: $\Delta f \leq \frac{1}{\tau_{max}} = 200$ kHz → Choose $\Delta f = 100$ kHz
> - Number of subcarriers: $N = \frac{B}{\Delta f} = \frac{10 \text{ MHz}}{100 \text{ kHz}} = 100$
> - Useful symbol duration: $T_u = \frac{1}{\Delta f} = 10 \mu s$
> - CP duration: $T_{cp} \geq \tau_{max} = 5 \mu s$ → Choose $T_{cp} = 5 \mu s$
> - Total symbol duration: $T_s = T_u + T_{cp} = 15 \mu s$
> - Data rate per subcarrier: $\frac{R}{N} = \frac{10 \text{ Mbps}}{100} = 100$ kbps

---

## Key Advantages

1. **Robust to frequency-selective fading** - Each subcarrier experiences flat fading
2. **Simple equalization** - One-tap equalizer per subcarrier in frequency domain
3. **High spectral efficiency** - Overlapping subcarriers without guard bands
4. **Natural frequency diversity** - Different subcarriers can be combined
5. **Easy to implement** - Efficient FFT/IFFT algorithm

> [!KEY POINT]
> Multicarrier modulation transforms a challenging frequency-selective fading problem into $N$ simple flat fading problems, each requiring only one-tap equalization.