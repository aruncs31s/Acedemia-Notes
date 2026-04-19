---
id: Outage Probability
tags:
  - academics
  - btech
  - s8
  - ect402
  - module2
dg-publish: true
---

# Outage Probability

**Outage** = Event when channel quality drops below threshold, making reliable communication impossible.

---

## Definition

In slow fading channels, the channel stays **constant** for long bursts. If the instantaneous SNR falls below a minimum threshold ($\rho_{min}$), the receiver cannot decode the signal reliably — this is an **outage**.

$$P_{outage} = P(SNR < \rho_{min})$$

---

## Computation Methods

### For Rayleigh Fading

When signal envelope follows Rayleigh distribution:

$$P_{outage} = 1 - \exp\left(-\frac{\rho_{min}}{\bar{\rho}}\right)$$

Where:
- $\rho_{min}$ = threshold SNR
- $\bar{\rho}$ = average SNR

### For Rician Fading

$$P_{outage} = 1 - Q_1\left(\frac{A}{\sigma}, \sqrt{\frac{2\rho_{min}}{1+K}}\right)$$

Where:
- $Q_1$ = Marcum Q-function
- $K$ = Rician K-factor
- $A$ = amplitude of LOS component

### General Formula

For any fading distribution:

$$P_{outage} = \int_0^{\rho_{min}} f_{\rho}(\rho) d\rho$$

Where $f_{\rho}(\rho)$ is the PDF of SNR.

---

## Capacity with Outage

The achievable rate considering outage:

$$C_{outage} = (1 - P_{outage}) W \log_2(1 + \rho_{min})$$

This is the rate reliably supported in $(1-P_{outage})$% of the time.

---

## Example Calculation

Given:
- Average SNR $\bar{\rho} = 10$ (10 dB)
- Threshold $\rho_{min} = 1$ (0 dB)

For Rayleigh:
$$P_{outage} = 1 - \exp\left(-\frac{1}{10}\right) = 1 - 0.905 = 0.095 = 9.5\%$$

---

## Relationship with Diversity

| Diversity Order (N) | Outage Reduction |
|-------------------|------------------|
| 1 | P_outage (baseline) |
| 2 | $(P_{outage})^2$ |
| N | $(P_{outage})^N$ |

More diversity branches → lower outage probability.

---

## Related Notes

- [[Module 2/Shannon Capacity]] - Capacity with outage formula
- [[Module 2/Fading]] - Rayleigh/Rician distributions
- [[Module 2/Diversity]] - Diversity reduces outage