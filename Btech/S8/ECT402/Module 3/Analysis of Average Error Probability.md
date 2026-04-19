---
banner: "https://images.unsplash.com/photo-1583602621722-cbd1130b210b?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
banner_y: 0.116
id: callout
aliases: []
tags:
  - files
  - templates
  - templater
dg-publish: true
title: callout
---
# Analysis of Average Error Probability in Flat Fading Channels
- [[Derivation of Average Error Probability in Flat Fading Channel]]
- [[Module 3 PYQ#4. Derive an equation to calculate the average error probability of a BPSK based signalling in a flat fading channel. (7 Marks)]]

---

> [!important]+ Derivation Summary
> **Core Concept:** $\overline{P}_b = \int_{0}^{\infty} P_b(\gamma) p_{\gamma}(\gamma) d\gamma$
> 
> **SNR Distribution:** $p_{\gamma}(\gamma) = \frac{1}{\overline{\gamma}_b} e^{-\gamma/\overline{\gamma}_b}$ (exponential)
> 
> **Exact Expression:** $\overline{P}_b = \frac{1}{2}\left[1 - \sqrt{\frac{\overline{\gamma}_b}{1+\overline{\gamma}_b}}\right]$
> 
> **High SNR:** $\overline{P}_b \approx \frac{1}{4\overline{\gamma}_b}$ (3 dB penalty vs AWGN)

---

## 1. Flat Fading Channel Model

### Channel Definition

A flat fading channel is characterized by:

$$r(t) = \alpha s(t) + n(t)$$

where:
- $\alpha$ = complex channel amplitude (random variable)
- $s(t)$ = transmitted signal with energy $E_b$
- $n(t)$ = AWGN with power spectral density $N_0/2$

### SNR Definition

The instantaneous SNR per bit is:

$$\gamma_b = \frac{|\alpha|^2 E_b}{N_0}$$

> [!KEY POINT]
> The channel amplitude $\alpha$ follows a **Rayleigh distribution** for non-LOS environments.

---

## 2. Rayleigh Fading Statistics

### Probability Density Function

For Rayleigh fading, the amplitude $r$ follows:

$$p(r) = \frac{r}{\sigma^2} \exp\left(-\frac{r^2}{2\sigma^2}\right), \quad r \geq 0$$

Since $\gamma_b \propto r^2$, the SNR follows **exponential distribution**:

$$p(\gamma_b) = \frac{1}{\bar{\gamma}_b} \exp\left(-\frac{\gamma_b}{\bar{\gamma}_b}\right), \quad \gamma_b \geq 0$$

### Properties

| Property | Expression |
|----------|------------|
| Mean | $E[\gamma_b] = \bar{\gamma}_b$ |
| Variance | $\text{Var}(\gamma_b) = \bar{\gamma}_b^2$ |
| CDF | $F(\gamma_b) = 1 - e^{-\gamma_b/\bar{\gamma}_b}$ |

---

## 3. BPSK Conditional Error Probability

For BPSK in AWGN with SNR $\gamma_b$:

$$P(e|\gamma_b) = Q\left(\sqrt{2\gamma_b}\right)$$

where $Q(x) = \frac{1}{\sqrt{2\pi}} \int_x^{\infty} e^{-t^2/2} dt$

---

## 4. Average Error Probability

### Final Expression

$$\boxed{\overline{P}_b = \frac{1}{2}\left(1 - \sqrt{\frac{\bar{\gamma}_b}{1 + \bar{\gamma}_b}}\right)}$$

### High SNR Approximation ($\bar{\gamma}_b \gg 1$)

$$\overline{P}_b \approx \frac{1}{4\bar{\gamma}_b}$$

> [!TIP]
> This shows a **3 dB penalty** compared to AWGN where $P_b \approx 1/2\bar{\gamma}_b$.

### Low SNR Approximation ($\bar{\gamma}_b \ll 1$)

$$\overline{P}_b \approx \frac{1}{2} - \frac{1}{2}\sqrt{\bar{\gamma}_b}$$

At very low SNR, error probability approaches 0.5 (random guessing).

---

## 5. Numerical Comparison

| $\bar{\gamma}_b$ (dB) | AWGN $P_b$ | Rayleigh $P_b$ | Penalty |
|---------------------|-----------|-----------------|---------|
| 10 | 3.9×10⁻⁶ | 4.5×10⁻³ | ~10 dB |
| 20 | 2.2×10⁻¹¹ | 2.3×10⁻⁵ | ~6 dB |
| 30 | 3.9×10⁻¹⁶ | 2.5×10⁻⁷ | ~4 dB |

---

## 6. Outage Probability

### Definition

$$P_{out} = P(\gamma_b < \gamma_{th}) = 1 - e^{-\gamma_{th}/\bar{\gamma}_b}$$

### Threshold SNR for Target BER

$$\gamma_{th} = \frac{[Q^{-1}(P_{target})]^2}{2}$$

| Target BER | $\gamma_{th}$ (dB) |
|----------|---------------------|
| 10⁻³ | 6.7 dB |
| 10⁻⁴ | 8.4 dB |
| 10⁻⁵ | 9.7 dB |

---

## 7. Example: 90% Reliability

> [!EXAMPLE]
> Find $\bar{\gamma}_b$ such that 90% of time, BER < 10⁻⁴
> 
> **Answer:** $\bar{\gamma}_b = 18.2$ dB

---

## 8. Diversity Gain

With $M$-branch diversity (e.g., MRC):

$$P_b^{(M)} \approx \frac{1}{\bar{\gamma}_b^M}$$

Diversity order $M$ provides significant improvement in error rate.

---

## 9. Key Takeaways

> [!KEY POINT]
> - Fading causes linear (not exponential) decrease in error rate with SNR
> - 3 dB additional power needed compared to AWGN
> - Diversity techniques essential for reliable communication
