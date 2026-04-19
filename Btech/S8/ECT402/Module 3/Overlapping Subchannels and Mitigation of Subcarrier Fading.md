# Overlapping Subchannels and Mitigation of Subcarrier Fading

## Overlapping Subchannels

> [!NOTE]
> In OFDM, subcarriers are allowed to overlap in the frequency domain to achieve high spectral efficiency while maintaining orthogonality.

### Concept

Unlike FDM (Frequency Division Multiplexing) which uses guard bands between subchannels, OFDM uses overlapping subcarriers with **orthogonal** frequency response.

### Orthogonality Condition

The subcarrier spacing Δf satisfies:

$$\Delta f = \frac{1}{T_u}$$

where $T_u$ is the useful symbol duration.

Subcarriers are orthogonal when:

$$\int_{0}^{T_u} e^{j2\pi k \Delta f t} \cdot e^{-j2\pi m \Delta f t} dt = \begin{cases} T_u, & k = m \ 0, & k \neq m \end{cases}$$

### Spectral Efficiency Comparison

| Modulation | Guard Band | Spectral Efficiency |
|------------|------------|---------------------|
| FDM | Required (~10-50% of BW) | Low to Moderate |
| OFDM | Not required | High (up to 90-95%) |

### Frequency Response

The frequency response of each subcarrier follows a **sinc** function:

$$S_k(f) = \text{sinc}\left(\pi T_u (f - f_k)\right)$$

The nulls of each subcarrier occur at:

$$f = f_k \pm \frac{n}{T_u}, \quad n = 1, 2, 3, ...$$

---

## Mitigation of Subcarrier Fading

> [!WARNING]
> In frequency-selective channels, different subcarriers experience different attenuation → Some subcarriers may be in deep fade, degrading performance.

### Problem: Subcarrier Fading

- Each subcarrier k experiences gain $H_k$
- Deep fades: $|H_k|^2 \approx 0$ → high error rate
- Frequency-selective fading causes **unequal SNR** across subcarriers

### Solution Techniques

#### 1. Channel Estimation and Equalization

**One-Tap Zero-Forcing Equalizer:**

$$\hat{X}[k] = \frac{Y[k]}{H[k]}$$

**One-Tap MMSE Equalizer:**

$$\hat{X}[k] = \frac{H^*[k] Y[k]}{|H[k]|^2 + \sigma_n^2}$$

> [!TIP]
> MMSE is preferred when noise is significant, as it avoids noise enhancement in deep fades.

#### 2. Adaptive Bit Loading

**Principles:**
- Assign more bits to subcarriers with good SNR
- Assign fewer bits (or none) to subcarriers in deep fade
-Bits per subcarrier: $b_k = \log_2\left(1 + \frac{\gamma_k}{\Gamma}\right)$

where $\Gamma$ is SNR gap (typically 3-6 dB for practical systems).

**Algorithms:**
| Algorithm | Complexity | Performance |
|-----------|-----------|-------------|
| Hughes-Hartogs | High (greedy) | Optimal |
| Chow's Algorithm | Medium | Near-optimal |
| Levin-Campello | Medium | Optimal for given rate |
| Fading Margin Loading | Low | Suboptimal |

#### 3. Power Loading

**Water-Filling Algorithm:**

$$P_k = \max\left(\mu - \frac{\sigma_k^2}{|H_k|^2}, 0\right)$$

where $\mu$ is water level determined by total power constraint.

> [!NOTE]
> Subcarriers with higher channel gain receive more power, allocating more energy to "good" channels.

#### 4. Frequency Diversity

**Technique:** Code across multiple subcarriers

- Errors on deep-faded subcarriers can be corrected using correctly decoded bits from other subcarriers
- Techniques: Convolutional coding, Turbo coding, LDPC, OFDM with COFDM

**Diversity Order:** $D = N_{corr}$ where $N_{corr}$ is number of uncorrelated subcarriers

#### 5. Subcarrier Allocation (OFDMA)

In multi-user OFDMA systems:
- Allocate "good" subcarriers to each user
- Proportional fairness scheduling ensures fair resource allocation
- Adaptive subcarrier assignment based on channel conditions

#### 6. Tone Interleaving

**Method:** Map adjacent data bits to far apart subcarriers

- Converts frequency-selective errors into random errors
- With channel coding, random errors are easier to correct

**Example:**
- Original: bits [1,2,3,4] → subcarriers [1,2,3,4]
- Interleaved: bits [1,2,3,4] → subcarriers [1,50,25,75]

---

## Summary Table

| Technique | Complexity | Performance Gain | Overhead |
|-----------|-----------|-----------------|----------|
| ZF Equalizer | Low | Basic | Pilots |
| MMSE Equalizer | Low | Improved | Pilots |
| Adaptive Bit Loading | High | High | CSI at TX |
| Power Loading | Medium | Moderate | No |
| Frequency Diversity | Medium | Moderate | Coding |
| Tone Interleaving | Low | Low | None |

> [!KEY POINT]
> The key to mitigating subcarrier fading is **exploiting channel state information (CSI)** at the transmitter and/or receiver to adapt transmission parameters.