---
tags:
  - wireless_communication
  - ect402
  - modulation
---

# Multi-Carrier Modulation (MCM)
![[MultiCarrier Modulation.png|653]]
- In a traditional Single Carrier system, all the data is transmitted over a single frequency channel. In contrast, Multi-Carrier Modulation (MCM) divides **the data stream into multiple parallel lower-bit rate subcarriers**[^1], each modulated onto a separate carrier frequency. This approach allows for **more efficient use of the spectrum** and improved performance in challenging wireless environments.

**Advantages:**

- **Resilience:** It is highly resilient to interference, narrow band fading[^2], and multipath effects[^3].
- **Reduced ISI:** By dividing a wideband data stream into multiple lower-rate streams, the symbol period on each sub-channel is significantly increased, which almost **completely eliminates Inter-Symbol Interference (ISI)**[^3].

**Disadvantages:**

- **High Complexity:** A traditional MCM implementation requires $N$ independent modulators and demodulators, making it complex, expensive, and power-hungry.
- **Spectral Inefficiency:** If the sub-channels are non-overlapping, it requires expensive near-ideal lowpass filters and a larger overall bandwidth, making it spectrally inefficient.

---

[^1]: **Subcarriers** are multiple orthogonal carrier waves used in Multi-Carrier systems like OFDM. Each subcarrier carries a portion of the data at a lower symbol rate, making the system more robust against frequency-selective fading.

[^2]: **Narrowband fading** occurs when the signal bandwidth is much smaller than the channel's coherence bandwidth. In such cases, all frequency components of the signal experience the same fading, causing amplitude variations but preserving the signal shape.

[^3]: **ISI (Inter-Symbol Interference) from multipath effects** occurs when multiple delayed copies of the transmitted signal arrive at the receiver, causing symbols to overlap. Multi-Carrier systems combat this by using longer symbol periods on each subcarrier—since the symbol duration becomes much larger than the channel's maximum delay spread, the delayed multipath components fall within the symbol period without causing overlap.
