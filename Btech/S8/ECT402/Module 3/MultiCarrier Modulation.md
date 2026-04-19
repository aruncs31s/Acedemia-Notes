
# Multi-Carrier Modulation (MCM)
![[MultiCarrier Modulation.png|653]]
- In a traditional Single Carrier system, all the data is transmitted over a single frequency channel. In contrast, Multi-Carrier Modulation (MCM) divides **the data stream into multiple parallel lower-bit rate subcarriers**, each modulated onto a separate carrier frequency. This approach allows for **more efficient use of the spectrum** and improved performance in challenging wireless environments.

**Advantages:**

- **Resilience:** It is highly resilient to interference, narrow band fading, and multipath effects.
- **Reduced ISI:** By dividing a wideband data stream into multiple lower-rate streams, the symbol period on each sub-channel is significantly increased, which almost completely eliminates Inter-Symbol Interference (ISI).

**Disadvantages:**

- **High Complexity:** A traditional MCM implementation requires $N$ independent modulators and demodulators, making it complex, expensive, and power-hungry.
- **Spectral Inefficiency:** If the sub-channels are non-overlapping, it requires expensive near-ideal lowpass filters and a larger overall bandwidth, making it spectrally inefficient.

Shall we look at how a **Cyclic Prefix** mitigates ISI next, or would you prefer the numerical problem calculating the **average SNR for BPSK modulation**?