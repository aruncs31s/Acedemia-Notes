---
banner: "https://images.unsplash.com/photo-1583602621722-cbd1130b210b?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
banner_y: 0.116
tags:
  - pyq
  - ect402
---
# Module 3 PYQ - OFDM Systems

> See: [[PYQ Index]] | [[most_asked_questions]]

## Questions

Here are the Module 3 questions from both of your previous year's question papers:

**From QP 1 (September 2025)**

| #   | Question                                                                                                                                                   | Marks | Answer                                                                                                                          |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | ----- | ------------------------------------------------------------------------------------------------------------------------------- |
| 1   | Analyse the different factors that affect the performance of OFDM systems?                                                                                 | 3     | [[#1. Analyse the different factors that affect the performance of OFDM systems? (3 Marks) { 1-analyse-the-different-factors}]] |
| 2   | Discuss the advantages and disadvantages of multicarrier modulation?                                                                                       | 3     | [[#2-discuss-the-advantages]]                                                                                                   |
| 3   | How does the cyclic prefix mitigate inter-symbol interference (ISI) in frequency-selective fading channels?                                                | 7     | [[#3-how-does-the-cyclic-prefix]]                                                                                               |
| 4   | Derive an equation to calculate the average error probability of a BPSK based signalling in a flat fading channel.                                         | 7     | [[#4-derive-an-equation-to-calculate-the-average-error-probability]]                                                            |
| 5   | Explain the different interferences in OFDM systems. How does it affect data transmission and what techniques are used to mitigate it?                     | 7     | [[#5-explain-the-different-interferences]]                                                                                      |
| 6   | For an OFDM system with a cyclic prefix length of 2 μs and a maximum channel delay spread of 15 μs, determine the maximum subcarrier spacing to avoid ISI. | 7     | [[#6-for-an-ofdm-system]]                                                                                                       |

**From QP 2 (October 2023)**

| # | Question | Marks | Answer |
|---|----------|-------|--------|
| 1 | Explain the significance of using cyclic prefix in an OFDM system. | 3 | [[#1-explain-the-significance-of-using-cyclic-prefix]] |
| 2 | With the help of mathematical equations show how linear convolution is converted to circular convolution in OFDM using Cyclic prefix. | 7 | [[#2-with-the-help-of-mathematical]] |
| 3 | Determine the average SNR per bit of BPSK modulation in Rayleigh slow fading channel in such that 90% of the times, the average probability of bit error is less than 10⁻⁴. | 7 | [[#3-determine-the-average-snr-per-bit]] |
| 4 | How can the subcarrier fading be mitigated in multicarrier modulation system? | 7 | [[#4-how-can-the-subcarrier-fading-be-mitigated]] |
| 5 | Explain the techniques employed to reduce PAPR in OFDM. | 7 | [[#5-explain-the-techniques-employed-to-reduce-papr]] |


## Important Equations

| Category | Parameter | Formula | Description |
|----------|-----------|---------|------------|
| **OFDM** | Subcarrier Spacing | $\Delta f = \frac{1}{T_u}$ | $T_u$ = useful symbol duration |
| | OFDM Symbol Duration | $T_s = T_u + T_{cp}$ | $T_{cp}$ = cyclic prefix duration |
| | Number of Subcarriers | $N = \frac{1}{\Delta f \cdot T_s}$ | Total subcarriers |
| | ISI-free Condition | $T_{cp} \geq \tau_{max}$ | $\tau_{max}$ = max channel delay spread |
| | Spectral Efficiency | $\eta = \frac{N}{N+N_{cp}} = \frac{T_u}{T_u+T_{cp}}$ | With CP overhead |
| **BPSK BER**[^1] | AWGN | $P_b = Q\left(\sqrt{\frac{2E_b}{N_0}}\right)$ | No fading |
| | Flat Fading (Rayleigh) | $P_b = \frac{1}{2}\left(1 - \sqrt{\frac{\bar{\gamma}_b}{1 + \bar{\gamma}_b}}\right)$ | $\bar{\gamma}_b = E_b/N_0$ avg SNR |
| | High SNR Approx | $P_b \approx \frac{1}{4\bar{\gamma}_b}$ | For $\bar{\gamma}_b \gg 1$ (3 dB penalty) |
| | Outage Probability[^2] | $P_{out} = 1 - e^{-\gamma_{th}/\bar{\gamma}_b}$ | $\gamma_{th}$ = threshold SNR |
| **PAPR**[^3] | Definition | $PAPR = \frac{\max \|x_n\|^2}{E[\|x_n\|^2]}$ | OFDM signal peak/avg power |
| | CCDF | $P(PAPR > \lambda) \approx 1 - (1 - e^{-\lambda})^{N}$ | N subcarriers |
| **Capacity** | Shannon | $C = B\log_2(1 + SNR)$ | Single channel bps/Hz |
| | OFDM Subcarrier | $C = \sum_{i=0}^{N-1} \log_2(1 + \gamma_i)$ | Total capacity |

---

[^1]: **BER (Bit Error Rate)** is the fraction of transmitted bits that are received incorrectly. It's a key performance metric for digital communication systems. BPSK in AWGN has BER = Q(√(2Eb/N₀)), while in Rayleigh fading it becomes P_b = ½(1 - √(γ̄/(1+γ̄))).

[^2]: **Outage Probability** is the probability that the channel SNR falls below a required threshold (γth), making reliable communication impossible. For Rayleigh fading: P_out = 1 - exp(-γth/γ̄). This determines the reliability of the link.

[^3]: **PAPR (Peak-to-Average Power Ratio)** measures the ratio of peak power to average power in an OFDM signal. High PAPR (typically 10-13 dB for 64-QAM OFDM) requires linear power amplifiers, otherwise causes intermodulation distortion and spectral spreading.

[^4]: **CFO (Carrier Frequency Offset)** is the difference between the transmitter and receiver carrier frequencies due to oscillator instability or Doppler shift. It causes loss of orthogonality between subcarriers, resulting in ICI (Inter-Carrier Interference).

[^5]: **Phase Noise** is random phase jitter introduced by oscillator imperfections. It causes constellation rotation and spreads the signal energy, leading to ICI and degraded BER performance.

[^6]: **Frequency-Selective Fading** occurs when the signal bandwidth exceeds the channel's coherence bandwidth. Different subcarriers experience different attenuation, causing some subcarriers to have poor SNR while others are strong.

[^7]: **Channel Delay Spread** (τmax) is the time difference between the first and last arriving multipath components. If it exceeds the cyclic prefix duration, ISI occurs.

---
banner: "https://images.unsplash.com/photo-1583602621722-cbd1130b210b?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
banner_y: 0.116

## QP 1: September 2025

### 1. Analyse the different factors that affect the performance of OFDM systems? (3 Marks)

**Answer:**

The performance of OFDM systems is affected by:

1. **Carrier Frequency Offset (CFO)**[^4]: Due to oscillator instability and Doppler shift, CFO causes inter-carrier interference (ICI) which degrades system performance.

2. **Phase Noise**[^5]: Generated by oscillator imperfections, causes rotation of constellation points and ICI.

3. **Peak-to-Average Power Ratio (PAPR)**[^3]: High PAPR requires linear power amplifiers with large dynamic range, otherwise causes intermodulation distortion.

4. **Frequency-Selective Fading**[^6]: Causes different attenuation across subcarriers, leading to unequal SNR across carriers.

5. **Timing Offset**: Incorrect symbol timing causes ISI and phase rotation.

6. **Channel Delay Spread**[^7]: Must be less than cyclic prefix duration to avoid ISI.

7. **Noise and Interference**: AWGN and adjacent channel interference affect SNR.

---

### 2. Discuss the advantages and disadvantages of multicarrier modulation? (3 Marks)

**Answer:**

**Advantages:**
- Efficient utilization of bandwidth through frequency multiplexing
- Robust against frequency-selective fading due to flat fading per subcarrier
- Simple equalization using one-tap equalizer per subcarrier
- Eliminates ISI caused by multipath fading
- Excellent spectral efficiency with tight subcarrier spacing
- Easy implementation using FFT/IFFT

**Disadvantages:**
- High PAPR requires expensive linear power amplifiers
- Sensitive to carrier frequency offset and phase noise
- Complex transmitter/receiver structure
- Cyclic prefix overhead reduces spectral efficiency
- More susceptible to narrowband interference
- Peak power issue causes intermodulation distortion

---

### 3. How does the cyclic prefix mitigate inter-symbol interference (ISI) in frequency-selective fading channels? (7 Marks)

**Answer:**

In frequency-selective fading channels, the transmitted signal arrives at the receiver through multiple paths with different delays, causing the symbol to spread in time. This results in ISI where the current symbol overlaps with previous and next symbols.

**Mechanism of Cyclic Prefix in Mitigating ISI:**

The cyclic prefix transforms linear convolution with the channel into circular convolution. Here's how:

1. **Channel Impulse Response**: Consider a channel with impulse response $h[l]$ where $l = 0, 1, ..., L$ and maximum delay spread $\tau_{max}$.

2. **Symbol Division**: The OFDM symbol of duration $T_u$ is divided into $N$ subcarriers. A cyclic prefix of length $N_{cp}$ samples (duration $T_{cp}$) is appended to the beginning of each symbol.

3. **CP Duration Condition**: If $T_{cp} \geq \tau_{max}$, then all multipath components of the current symbol arrive before the next OFDM symbol begins.

4. **Circular Convolution**: At the receiver, after removing the CP, the received signal is:
$$y_k = \sum_{l=0}^{L} h_l x_{k-l} \quad \text{(circular convolution)}$$

This becomes circular convolution because the CP ensures that the delayed portions of the signal wrap around to the beginning of the symbol.

5. **FFT Property**: Circular convolution in time domain becomes multiplicative operation in frequency domain:
$$Y_k = H_k \cdot X_k$$
where $H_k$ is the channel frequency response at subcarrier $k$.

6. **One-Tap Equalization**: Simple one-tap equalizer recovers the transmitted symbol:
$$\hat{X}_k = \frac{Y_k}{H_k}$$

Thus, the cyclic prefix converts the dispersive channel (causing ISI) into non-dispersive subchannels through circular convolution, completely eliminating ISI.

---

### 4. Derive an equation to calculate the average error probability of a BPSK based signalling in a flat fading channel. (7 Marks) 

**Answer:**

**Derivation for Average Error Probability of BPSK in Flat Fading Channel:**

For BPSK modulation in flat fading (Rayleigh fading) channel:
- Transmitted signal: $s(t) = \sqrt{E_b} \cos(2\pi f_c t)$ for bit "1"
- Received signal: $r(t) = \alpha s(t) + n(t)$
- SNR per bit: $\gamma_b = \frac{\alpha^2 E_b}{N_0}$

**Step 1: Conditional Error Probability**

For a given channel amplitude $\alpha$ (or SNR $\gamma_b$), the conditional error probability is:
$$P(e|\gamma_b) = Q\left(\sqrt{2\gamma_b}\right)$$

**Step 2: PDF of SNR in Rayleigh Fading**

For Rayleigh fading, $\alpha$ is Rayleigh distributed with parameter $\sigma$, so $\alpha^2$ is exponentially distributed. The PDF of $\gamma_b$ is:
$$p(\gamma_b) = \frac{1}{\bar{\gamma}_b} \exp\left(-\frac{\gamma_b}{\bar{\gamma}_b}\right), \quad \gamma_b \geq 0$$
where $\bar{\gamma}_b = E\left[\frac{E_b}{N_0}\right] = \frac{E_b}{N_0} E[\alpha^2]$ is average SNR.

**Step 3: Average Error Probability**

The average error probability is obtained by averaging the conditional error probability over the fading distribution:
$$P_b = \int_0^{\infty} Q\left(\sqrt{2\gamma_b}\right) \cdot p(\gamma_b) d\gamma_b$$

Substituting the Rayleigh PDF:
$$P_b = \int_0^{\infty} Q\left(\sqrt{2\gamma_b}\right) \cdot \frac{1}{\bar{\gamma}_b} \exp\left(-\frac{\gamma_b}{\bar{\gamma}_b}\right) d\gamma_b$$

**Step 4: Solving the Integral**

Using the identity $\int_0^\infty Q(\sqrt{2x}) e^{-x/a} dx = \frac{1}{2}\left(1 - \sqrt{\frac{a}{1+a}}\right)$ for $a > 0$:

Let $a = \bar{\gamma}_b$, then:
$$P_b = \frac{1}{2}\left(1 - \sqrt{\frac{\bar{\gamma}_b}{1 + \bar{\gamma}_b}}\right)$$

This is the **average error probability of BPSK in Rayleigh flat fading channel**.

**Verification:**
- At high SNR ($\bar{\gamma}_b \gg 1$): $P_b \approx \frac{1}{4\bar{\gamma}_b}$ (3 dB penalty compared to AWGN)
- At low SNR ($\bar{\gamma}_b \ll 1$): $P_b \approx \frac{1}{2} - \frac{1}{2}\sqrt{\bar{\gamma}_b} \approx 0.5$

---

### 5. Explain the different interferences in OFDM systems. How does it affect data transmission and what techniques are used to mitigate it? (7 Marks)

**Answer:**

**Different Interferences in OFDM Systems:**

1. **Inter-Symbol Interference (ISI)**
   - Caused by multipath propagation in frequency-selective channels
   - When channel delay spread > cyclic prefix duration
   - Effect: Symbol from previous OFDM block spills into current block

2. **Inter-Carrier Interference (ICI)**
   - Caused by carrier frequency offset (CFO) due to oscillator drift or Doppler shift
   - Effect: Leakage from other subcarriers contaminates desired subcarrier
   - Causes constellation rotation and amplitude distortion

3. **Peak-to-Average Power Ratio (PAPR) Issues**
   - Large number of subcarriers added in phase can create high peaks
   - Effect: Causes non-linear distortion when passed through power amplifier
   - Results in intermodulation products creating both in-band and out-of-band interference

4. **Adjacent Channel Interference (ACI)**
   - Caused by imperfect filtering and spectral leakage
   - Effect: Interference to/from neighboring frequency bands

5. **Narrowband Interference (NBI)**
   - Interference from narrowband signals in the OFDM bandwidth
   - Effect: Complete corruption of affected subcarriers

**Mitigation Techniques:**

| Interference | Mitigation Technique |
|-------------|---------------------|
| ISI | Use cyclic prefix with $T_{cp} \geq \tau_{max}$; channel estimation and equalization |
| ICI | Frequency synchronization; offset correction algorithms; pilots for CFO estimation |
| PAPR | Clipping and filtering; Selective Mapping (SLM); Partial Transmit Sequence (PTS); tone reservation |
| ACI | Sharp roll-off filters; guard bands; windowing |
| NBI | Adaptive filtering; subcarrier loading; frequency hopping |

---

### 6. For an OFDM system with a cyclic prefix length of 2 μs and a maximum channel delay spread of 15 μs, determine the maximum subcarrier spacing to avoid ISI. (7 Marks)

**Answer:**

**Given:**
- Cyclic prefix length: $T_{cp} = 2 \mu s$
- Maximum channel delay spread: $\tau_{max} = 15 \mu s$

**To avoid ISI, we require:**
$$T_{cp} \geq \tau_{max}$$

However, here $T_{cp} = 2 \mu s < \tau_{max} = 15 \mu s$, which is insufficient.

**But the question asks for maximum subcarrier spacing to avoid ISI:**

For OFDM system to avoid ISI, the **total symbol duration** must be greater than channel delay spread:
$$T_s = T_u + T_{cp} \geq \tau_{max}$$

Given $T_{cp} = 2 \mu s$:
$$T_u \geq \tau_{max} - T_{cp} = 15 - 2 = 13 \mu s$$

**Subcarrier spacing is:**
$$\Delta f = \frac{1}{T_u}$$

For maximum subcarrier spacing (minimum $T_u$):
$$\Delta f_{max} = \frac{1}{13 \mu s} = \frac{1}{13 \times 10^{-6}} = 76.92 kHz \approx 77 kHz$$

**Therefore, maximum subcarrier spacing to avoid ISI is 77 kHz.**

**Verification:**
- With $\Delta f = 77 kHz$, $T_u = 13 \mu s$
- $T_s = 13 + 2 = 15 \mu s = \tau_{max}$
- This satisfies the condition exactly, so there will be no ISI.

---

## QP 2: October 2023

### 1. Explain the significance of using cyclic prefix in an OFDM system. (3 Marks)

**Answer:**

The cyclic prefix in OFDM systems serves several critical purposes:

1. **Eliminates ISI**: Converts linear convolution with channel to circular convolution, ensuring each multipath component stays within the symbol boundary.

2. **Enables Simple Equalization**: Makes the channel convolution circular, allowing simple one-tap equalization in frequency domain.

3. **Preserves Orthogonality**: Maintains subcarrier orthogonality even with multipath propagation.

4. **Copy of Symbol**: The CP is a copy of the last part of the OFDM symbol, allowing the receiver to acquire symbol timing easily.

**Trade-off**: However, the cyclic prefix introduces overhead, reducing spectral efficiency. Typically 10-25% of symbol duration is used as CP.

---

### 2. With the help of mathematical equations show how linear convolution is converted to circular convolution in OFDM using Cyclic prefix. (7 Marks)

**Answer:**

**Proof: Linear Convolution to Circular Convolution using CP:**

**Step 1: Transmitted Signal**

The OFDM symbol after IFFT:
$$x[n] = \sum_{k=0}^{N-1} X[k] e^{j2\pi kn/N}, \quad n = 0, 1, ..., N-1$$

**Step 2: Adding Cyclic Prefix**

A cyclic prefix of length $L$ (where $L$ is channel maximum delay in samples) is appended:
$$x_{cp}[n] = \begin{cases} x[N-L+n], & n = 0, 1, ..., L-1 \ x[n-L], & n = L, L+1, ..., N+L-1 \end{cases}$$

The CP contains the last $L$ samples of the OFDM symbol.

**Step 3: Channel Linear Convolution**

The channel with impulse response $h[n]$ (length $L+1$) performs linear convolution:
$$y_{lin}[n] = x[n] * h[n] = \sum_{k=0}^{L} h[k] x[n-k]$$

**Step 4: Receiver - Removing CP**

At receiver, after sampling, we remove the first $L$ samples (CP). The remaining $N$ samples are:
$$y[n] = y_{lin}[n+L], \quad n = 0, 1, ..., N-1$$

**Step 5: Proof of Circular Convolution**

Considering $n = 0$:
$$y[0] = \sum_{k=0}^{L} h[k] x[0+L-k] = \sum_{k=0}^{L} h[k] x[L-k]$$

For the index $L-k$, when $k > L$, we wrap around because CP contains $x[N-L]$ to $x[N-1]$.

This is equivalent to:
$$y[n] = \sum_{m=0}^{N-1} h_{circ}[m] x[(n-m) \mod N]$$

where $h_{circ}[m]$ is the circular version of $h[n]$ extended to length $N$.

**Mathematical Representation:**

Linear convolution: $y_{lin}[n] = x[n] * h[n]$

With CP: $y_{cp}[n] = x_{cp}[n] * h[n]$

After CP removal: $y_{circ}[n] = x[n] \otimes h[n]$

where $\otimes$ denotes circular convolution.

**Step 6: Frequency Domain**

Taking N-point FFT:
$$Y[k] = X[k] \cdot H[k]$$

where $H[k]$ is the channel frequency response at subcarrier k.

This proves that cyclic prefix successfully converts linear convolution to circular convolution, enabling simple one-tap equalization.

---

### 3. Determine the average SNR per bit of BPSK modulation in Rayleigh slow fading channel such that 90% of the times, the average probability of bit error is less than 10^{-4}. (7 Marks)

**Answer:**

**Given:**
- Target bit error probability: $P_b < 10^{-4}$
- Probability requirement: 90% of the times, i.e., $P(P_b < 10^{-4}) = 0.9$

**Interpretation:**

This is an outage probability problem. We need to find threshold $\gamma_{th}$ such that when $\gamma_b \geq \gamma_{th}$, the error probability is $< 10^{-4}$.

**Step 1: Find SNR threshold for $P_b = 10^{-4}$**

For BPSK, $P_b = Q(\sqrt{2\gamma_b})$. Solving for $\gamma_b$ when $P_b = 10^{-4}$:
$$Q(\sqrt{2\gamma_{th}}) = 10^{-4}$$

Using Q-function inverse: $\sqrt{2\gamma_{th}} = Q^{-1}(10^{-4})$

From Q-function tables or approximation:
$Q^{-1}(10^{-4}) \approx 3.719$ (for $P = 10^{-4}$)

So:
$$\gamma_{th} = \frac{3.719^2}{2} = \frac{13.83}{2} = 6.915 \approx 6.92$$

**Step 2: Find average SNR such that $P(\gamma_b > \gamma_{th}) = 0.9$**

In Rayleigh fading:
$$P(\gamma_b > \gamma_{th}) = \exp\left(-\frac{\gamma_{th}}{\bar{\gamma}_b}\right)$$

Setting this equal to 0.9:
$$\exp\left(-\frac{6.92}{\bar{\gamma}_b}\right) = 0.9$$

Taking natural log:
$$-\frac{6.92}{\bar{\gamma}_b} = \ln(0.9) = -0.1054$$

$$\bar{\gamma}_b = \frac{6.92}{0.1054} = 65.66 \approx 66$$

**Step 3: Convert to dB**

$$\bar{\gamma}_b(dB) = 10 \log_{10}(66) = 18.2 dB$$

**Answer:** The average SNR per bit required is approximately **66 (18.2 dB)** to ensure 90% of the time, the bit error probability is less than $10^{-4}$.

---

### 4. How can the subcarrier fading be mitigated in multicarrier modulation system? (7 Marks)

**Answer:**

**Subcarrier Fading Mitigation Techniques in Multicarrier Modulation:**

1. **Adaptive Loading/Bit Loading**
   - Dynamically allocate bits and power based on subcarrier SNR
   - More bits to subcarriers with better channel conditions
   - Algorithms: Chow's algorithm, Hughes-Hartogs algorithm, Levin-Campello algorithm

2. **Channel Estimation and Equalization**
   - Insert pilot subcarriers for channel estimation
   - One-tap equalizer per subcarrier: $\hat{X}[k] = Y[k]/H[k]$ (Zero-Forcing)
   - MMSE equalizer: $\hat{X}[k] = \frac{H^* Y}{|H|^2 + \sigma_n^2}$

3. **Frequency Diversity**
   - Apply coding across multiple subcarriers (OFDM with channel coding)
   - Use interleaving to spread errors across fading
   - Techniques: Convolutional coding, Turbo coding, LDPC, OFDM with COFDM

4. **Power Loading**
   - Transmit more power on subcarriers with deep fades
   - Water-filling algorithm distributes power optimally

5. **Subcarrier Allocation**
   - In multi-user OFDM (OFDMA), allocate good subcarriers to each user
   - Proportional fairness scheduling

6. **Automatic Gain Control (AGC)**
   - Normalize received signal power across subcarriers

7. **Tone Interleaving**
   - Spread adjacent data across different frequency locations
   - Makes frequency-selective fading appear as random errors

---

### 5. Explain the techniques employed to reduce PAPR in OFDM. (7 Marks)

**Answer:**

**Peak-to-Average Power Ratio (PAPR) Reduction Techniques:**

PAPR is defined as:
$$PAPR = \frac{\max_n |x[n]|^2}{E[|x[n]|^2|]}$$

where $x[n]$ is the OFDM signal after IFFT.

**Why PAPR is Problematic:**
- High PAPR requires power amplifier to operate in linear region
- Causes spectral spreading and in-band distortion
- Reduces efficiency of power amplifier

**Reduction Techniques:**

1. **Clipping and Filtering**
   - Clip the peaks above a threshold
   - Apply filtering to reduce spectral regrowth
   - Simple but causes in-band distortion and out-of-band noise

2. **Selective Mapping (SLM)**
   - Generate $U$ different phase sequences
   - Select the one with lowest PAPR for transmission
   - Requires side information at receiver
   - Complexity: $U$ IFFT operations

3. **Partial Transmit Sequence (PTS)**
   - Divide subcarriers into $V$ subgroups
   - Apply phase rotation to each segment
   - Find optimal phase combination to minimize PAPR
   - Requires side information

4. **Tone Reservation (TR)**
   - Reserve some subcarriers (tones) for PAPR reduction
   - These tones carry no data
   - Requires knowledge at receiver

5. **Tone Injection**
   - Map data to larger constellation
   - Inject redundant constellation points to reduce PAPR
   - Spectral inefficiency

6. **Coding-based Techniques**
   - Use special codes that inherently have low PAPR
   - Convolutional coding with special patterns
   - Trade-off between coding gain and PAPR reduction

7. **Interleaving**
   - Rearrange subcarriers in different patterns
   - Select arrangement with lowest PAPR
   - Less complexity than SLM

8. ** pulse Shaping**
   - Apply pulse shaping to each subcarrier
   - Reduces spectral leakage but limited PAPR improvement

**Comparison Table:**

| Technique | PAPR Reduction | Complexity | Data Loss | Distortion |
|-----------|---------------|------------|----------|------------|
| Clipping | High | Low | No | Yes |
| SLM | Moderate | High | Yes (SI) | No |
| PTS | Moderate | High | Yes (SI) | No |
| TR | Moderate | Medium | Yes (tones) | No |
| Coding | Low | Medium | No | No |

---

## Additional Notes

### Key Concepts Summary

1. **OFDM Main Advantage**: Converts frequency-selective channel into flat fading subchannels
2. **Key Requirement**: $T_{cp} \geq \tau_{max}$ for ISI-free operation
3. **Trade-off**: Cyclic prefix overhead vs. system complexity
4. **BPSK in Rayleigh**: $P_b = \frac{1}{2}(1 - \sqrt{\bar{\gamma}_b/(1+\bar{\gamma}_b)})$
5. **PAPR Problem**: Due to central limit theorem, OFDM signal has Gaussian-like distribution

### Important Relationships

- Bandwidth efficiency with CP: $\eta = \frac{N}{N+N_{cp}}$
- For 25% CP overhead: $\eta$ = 80%$
- Typical subcarrier spacing: 10-100 kHz
- Typical CP duration: 1-4 μs


### Determine the required average SNR ($\overline{\gamma}_b$) for BPSK modulation in slow Rayleigh fading such that for 95% of the time, the probability of error $P_b < 10^{-4}$:

- [ ] Practice this 📅 2026-04-20 

**1. Find the target SNR threshold ($\gamma_0$)** For BPSK modulation in an AWGN channel, a target bit error rate (BER) of $10^{-4}$ is achieved at an SNR of approximately $8.5 \text{ dB}$. Converting this to a linear scale: $\gamma_0 = 10^{0.85}$.

**2. Determine the Outage Probability ($P_{out}$)** Since the system must maintain this error rate for 95% of the time, the acceptable outage probability is 5%. $P_{out} = 0.05$.

**3. Calculate the Average SNR ($\overline{\gamma}_b$)** Using the outage probability formula for Rayleigh fading ($P_{out} = 1 - e^{-\gamma_0/\overline{\gamma}_b}$), we rearrange to solve for the average SNR: $$\overline{\gamma}_b = \frac{\gamma_0}{-\ln(1 - P_{out})}$$ $$\overline{\gamma}_b = \frac{10^{0.85}}{-\ln(1 - 0.05)}$$ $$\overline{\gamma}_b \approx 138 \text{ (linear scale)}$$ Converting back to decibels, the required average SNR is **$21.4 \text{ dB}$**.

_(Note: Your October 2023 exam features this exact problem but asks for 90% of the time instead of 95%, so you would just swap $0.05$ for $0.10$ in the final equation)._

Since we've hit the major concepts in Module 3, are you ready to jump into Module 4? We can start by looking at **Multiple Access Techniques (FDMA/TDMA/CDMA)** or the difference between **Diversity and Equalization**.


