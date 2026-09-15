---
banner: "https://images.unsplash.com/photo-1583602621722-cbd1130b210b?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
banner_y: 0.116
---
# Outage Probability Analysis of BPSK in Flat-Fading Channels

## Definition

Outage probability is the probability that the channel quality falls below a threshold required for reliable communication, causing the system to be in "outage."

$$P_{out} = P(SNR < \gamma_{th}) = P(\gamma_b < \gamma_{th})$$

## Outage Probability in Rayleigh Fading

For Rayleigh fading channel, the SNR γ_b follows exponential distribution:

$$P_{out} = P(\gamma_b < \gamma_{th}) = 1 - \exp\left(-\frac{\gamma_{th}}{\bar{\gamma}_b}\right)$$

where:
- $\gamma_{th}$ = threshold SNR required for target BER
- $\bar{\gamma}_b$ = average SNR per bit

## Finding Threshold SNR

For BPSK with target BER $P_{target}$:

$$P_{target} = Q(\sqrt{2\gamma_{th}})$$

Solving for $\gamma_{th}$:

$$\gamma_{th} = \frac{[Q^{-1}(P_{target})]^2}{2}$$

### Common Threshold Values

| Target BER | γ_th (linear) | γ_th (dB) |
|-----------|--------------|----------|
| 10⁻³ | 4.67 | 6.7 dB |
| 10⁻⁴ | 6.92 | 8.4 dB |
| 10⁻⁵ | 9.34 | 9.7 dB |
| 10⁻⁶ | 11.9 | 10.8 dB |

## Example: 90% Reliability

**Problem:** Find average SNR such that 90% of the time, BER < 10⁻⁴

**Solution:**

1. For BER = 10⁻⁴, find γ_th:
$$\gamma_{th} = \frac{[Q^{-1}(10^{-4})]^2}{2} = \frac{13.83}{2} = 6.92$$

2. For 90% reliability:
$$P(\gamma_b > \gamma_{th}) = 0.9$$
$$\exp\left(-\frac{6.92}{\bar{\gamma}_b}\right) = 0.9$$

3. Solve:
$$\bar{\gamma}_b = \frac{6.92}{-\ln(0.9)} = \frac{6.92}{0.1054} = 65.66$$

4. In dB:
$$\bar{\gamma}_b(dB) = 10\log_{10}(65.66) = 18.2 \text{ dB}$$

## Outage vs Average Error Probability

| Metric | Definition | Use Case |
|--------|------------|----------|
| Average P_e | E[P(e|SNR)] | Long-term performance |
| Outage P_out | P(SNR < γ_th) | Reliability requirement |

## Key Insights

1. **Outage occurs** when instantaneous SNR drops below threshold due to deep fades
2. **Higher threshold** required → more outages
3. **Higher average SNR** → lower outage probability
