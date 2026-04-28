---
banner: "https://images.unsplash.com/photo-1583602621722-cbd1130b210b?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
banner_y: 0.116
---
# Discrete Implementation of Multicarrier – OFDM

## Overview

> [!NOTE]
> OFDM can be efficiently implemented using **IFFT** (Inverse Fast Fourier Transform) at the transmitter and **FFT** (Fast Fourier Transform) at the receiver, reducing complexity from $O(N^2)$ to $O(N \log N)$.

---
banner: "https://images.unsplash.com/photo-1583602621722-cbd1130b210b?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
banner_y: 0.116

## Discrete-Time OFDM System

### Transmitter Block Diagram

```
┌─────────────┐    ┌───────────┐    ┌──────────┐    ┌────────────┐    ┌─────────────┐
│  Data Bits  │ →  │ S/P Conv  │ → │ QAM Map  │ → │   IFFT    │ → │  Add CP   │ → │  P/S Conv  │
└─────────────┘    └───────────┘    └──────────┘    └──────────┘    └────────────┘    └─────────────┘
```

### Receiver Block Diagram

```
┌─────────────┐    ┌───────────┐    ┌──────────┐    ┌──────────┐    ┌────────────┐    ┌─────────────┐
│  Received   │ →  │ S/P Conv  │ → │Remove CP │ → │   FFT    │ → │  Equalizer│ → │ QAM Demap  │ → │  Data Bits │
└─────────────┘    └───────────┘    └──────────┘    └──────────┘    └────────────┘    └─────────────┘
```

---

## Mathematical Derivation

### Step 1: Serial to Parallel Conversion

Given input data stream with bits $\{b_0, b_1, b_2, ...\}$, convert to parallel blocks of $N$ symbols:

$$\mathbf{X} = [X_0, X_1, X_2, ..., X_{N-1}]^T$$

where $X_k$ is the QAM symbol for subcarrier $k$.

### Step 2: IFFT Operation

Apply N-point IFFT to convert frequency domain to time domain:

$$x[n] = \frac{1}{N} \sum_{k=0}^{N-1} X[k] e^{j 2\pi kn/N}, \quad n = 0, 1, ..., N-1$$

> [!TIP]
> The factor $\frac{1}{N}$ normalizes the IFFT output power.

### Step 3: Cyclic Prefix Insertion

Append the last $N_{cp}$ samples as cyclic prefix:

$$x_{cp}[n] = \begin{cases} x[N - N_{cp} + n], & n = 0, 1, ..., N_{cp} - 1 \\ x[n - N_{cp}], & n = N_{cp}, ..., N + N_{cp} - 1 \end{cases}$$

**Total OFDM symbol length:** $N_{sym} = N + N_{cp}$

### Step 4: Parallel to Serial Conversion

Convert parallel time-domain samples to serial stream for channel transmission.

---

## Channel and Receiver Processing

### Step 5: Channel Convolution

The transmitted signal passes through a frequency-selective channel with impulse response $h[n]$ of length $L+1$:

$$y_{cp}[n] = x_{cp}[n] * h[n]$$

where $*$ denotes linear convolution.

### Step 6: Remove Cyclic Prefix

At the receiver, discard the first $N_{cp}$ samples:

$$y[n] = y_{cp}[n + N_{cp}], \quad n = 0, 1, ..., N-1$

> [!KEY POINT]
> This removes ISI, converting linear convolution to circular convolution when $N_{cp} \geq L$.

### Step 7: FFT Operation

Apply N-point FFT to convert time domain to frequency domain:

$$Y[k] = \sum_{n=0}^{N-1} y[n] e^{-j 2\pi kn/N}, \quad k = 0, 1, ..., N-1$$

### Step 8: Channel Equalization

**Zero-Forcing (ZF) Equalizer:**

$$\hat{X}[k] = \frac{Y[k]}{H[k]}$$

**MMSE Equalizer:**

$$\hat{X}[k] = \frac{H^*[k] Y[k]}{|H[k]|^2 + \sigma_n^2}$$

where $H[k]$ is the channel frequency response at subcarrier $k$.

### Step 9: QAM Demapping and Parallel to Serial

Recover original data bits from QAM symbols.

---

## Parameter Selection

### Required Parameters

| Parameter | Symbol | Selection Criterion |
|-----------|--------|---------------------|
| Number of subcarriers | $N$ | $N \geq 10 \cdot L$ for diversity |
| Subcarrier spacing | $\Delta f$ | $\Delta f \ll B_c = 1/\tau_{max}$ |
| CP length | $N_{cp}$ | $N_{cp} \geq L$ (channel length) |
| Symbol duration | $T_s$ | $T_s = T_u + T_{cp}$ |

### Example: LTE-like System

> [!EXAMPLE]
> - Channel delay spread: $\tau_{max} = 5 \mu s$
> - Subcarrier spacing: $\Delta f = 15$ kHz
> - Useful symbol: $T_u = 66.67 \mu s$
> - CP duration: $T_{cp} = 4.69 \mu s$ (7% of symbol)
> - FFT size: $N = 2048$ (for 20 MHz BW)

---

## Complexity Comparison

| Operation | DFT/DFT | FFT/IFFT |
|-----------|---------|----------|
| Multiplications | $N^2$ | $N \log_2 N$ |
| For N = 1024 | 1,048,576 | 10,240 |

> [!KEY POINT]
> FFT reduces complexity by ~100x for typical OFDM system sizes, making real-time implementation feasible.

---

## Implementation Considerations

### Padding Requirements

- FFT size must be power of 2: $N = 2^m$
- Common sizes: 256, 512, 1024, 2048, 4096

### Windowing

Apply windowing before FFT to reduce spectral leakage:

$$w[n] = \begin{cases} \sin^2\left(\frac{\pi n}{N_{win}}\right), & 0 \leq n < N_{win} \\ 1, & N_{win} \leq n < N - N_{win} \\ \sin^2\left(\frac{\pi (N-n)}{N_{win}}\right), & N - N_{win} \leq n < N \end{cases}$$

### Carrier Frequency Offset (CFO) Correction

CFO causes ICI. Estimate and correct using:
- Training sequences
- Pilot subcarriers
- Feedback from phase detector

---

## Summary

| Step | Transmitter | Receiver |
|------|-------------|----------|
| 1 | Data → S/P | Received → S/P |
| 2 | QAM Mapping | Remove CP |
| 3 | IFFT | FFT |
| 4 | Add CP | Channel Equalization |
| 5 | P/S → Channel | QAM Demap → P/S → Data |

> [!KEY POINT]
