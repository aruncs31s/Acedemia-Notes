# Analysis of Average Error Probability

## Average Error Probability and Outage Probability of BPSK in Flat-Fading Channels

### Flat Fading Channel Model

In a flat fading channel, the channel amplitude α varies over time but the signal experiences the same attenuation across all frequency components. The received signal is:

$$r(t) = \alpha s(t) + n(t)$$

where:
- α = channel amplitude (random variable)
- s(t) = transmitted signal
- n(t) = AWGN

### Average Error Probability Derivation

For BPSK modulation in flat fading (Rayleigh fading) channel:

**Step 1: Conditional Error Probability**

For a given channel amplitude α (or SNR γ_b), the conditional error probability is:

$$P(e|\gamma_b) = Q\left(\sqrt{2\gamma_b}\right)$$

where $\gamma_b = \frac{\alpha^2 E_b}{N_0}$ is the instantaneous SNR per bit.

**Step 2: PDF of SNR in Rayleigh Fading**

For Rayleigh fading, α is Rayleigh distributed. The SNR γ_b follows exponential distribution:

$$p(\gamma_b) = \frac{1}{\bar{\gamma}_b} \exp\left(-\frac{\gamma_b}{\bar{\gamma}_b}\right), \quad \gamma_b \geq 0$$

where $\bar{\gamma}_b = E[\gamma_b]$ is the average SNR per bit.

**Step 3: Average Error Probability**

The average error probability is obtained by averaging the conditional error probability over the fading distribution:

$$P_b = \int_0^{\infty} Q\left(\sqrt{2\gamma_b}\right) \cdot p(\gamma_b) d\gamma_b$$

$$P_b = \int_0^{\infty} Q\left(\sqrt{2\gamma_b}\right) \cdot \frac{1}{\bar{\gamma}_b} \exp\left(-\frac{\gamma_b}{\bar{\gamma}_b}\right) d\gamma_b$$

**Solving the integral using identity:**

$$\int_0^\infty Q(\sqrt{2x}) e^{-x/a} dx = \frac{1}{2}\left(1 - \sqrt{\frac{a}{1+a}}\right)$$

**Final Result:**

$$\boxed{P_b = \frac{1}{2}\left(1 - \sqrt{\frac{\bar{\gamma}_b}{1 + \bar{\gamma}_b}}\right)}$$

This is the average error probability of BPSK in Rayleigh flat fading channel.

### Special Cases

- **High SNR** ($\bar{\gamma}_b \gg 1$): 
$$P_b \approx \frac{1}{4\bar{\gamma}_b}$$

This shows a 3 dB penalty compared to AWGN (which has $P_b = Q(\sqrt{2\gamma_b}) \approx \frac{1}{2\bar{\gamma}_b}$ for high SNR).

- **Low SNR** ($\bar{\gamma}_b \ll 1$):
$$P_b \approx \frac{1}{2} - \frac{1}{2}\sqrt{\bar{\gamma}_b}$$

### Outage Probability

Outage probability is the probability that the instantaneous SNR falls below a threshold $\gamma_{th}$:

$$P_{out} = P(\gamma_b < \gamma_{th}) = 1 - e^{-\gamma_{th}/\bar{\gamma}_b}$$

For a target error probability $P_{target}$, find $\gamma_{th}$ such that $Q(\sqrt{2\gamma_{th}}) = P_{target}$, then:
$$P_{out} = 1 - e^{-\gamma_{th}/\bar{\gamma}_b}$$

### Comparison: AWGN vs Fading

| SNR (dB) | AWGN BER | Fading BER (Rayleigh) |
|---------|---------|----------------------|
| 10 | 3.9×10⁻⁶ | 4.5×10⁻³ |
| 20 | 2.2×10⁻¹¹ | 2.3×10⁻⁵ |
| 30 | 3.9×10⁻¹⁶ | 2.5×10⁻⁷ |

The fading channel has significantly higher error rates due to deep fades.

### Key Takeaways

1. **Diversity Gain**: With diversity techniques (MRC, equal gain combining), the error probability improves significantly.

2. **3 dB Penalty**: Flat Rayleigh fading requires ~3 dB more power than AWGN for the same error rate.

3. **Outage Events**: Even at high average SNR, occasional deep fades cause outage errors.

4. **Adaptation**: Adaptive modulation and coding can mitigate fading effects by adjusting transmission parameters based on channel conditions.