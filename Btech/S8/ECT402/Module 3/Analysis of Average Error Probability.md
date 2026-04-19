# Analysis of Average Error Probability in Flat Fading Channels

---

## Introduction

> [!NOTE]
> In wireless communication systems, the transmitted signal experiences fading due to multipath propagation. When the signal bandwidth is less than the coherence bandwidth ($B < B_c$), all frequency components experience the same attenuation — this is called **flat fading**.

This analysis derives the average bit error probability for BPSK modulation in flat Rayleigh fading channels, which is a fundamental result in wireless communications.

---

## 1. Flat Fading Channel Model

### 1.1 Channel Definition

A flat fading channel is characterized by:

$$r(t) = \alpha s(t) + n(t)$$

where:
- $\alpha$ = complex channel amplitude (random variable)
- $s(t)$ = transmitted signal with energy $E_b$
- $n(t)$ = AWGN with power spectral density $N_0/2$

### 1.2 SNR Definition

The instantaneous SNR per bit is:

$$\gamma_b = \frac{|\alpha|^2 E_b}{N_0}$$

> [!KEY POINT]
> The channel amplitude $\alpha$ is a random variable that follows a **Rayleigh distribution** for environments with no dominant line-of-sight (LOS) path.

### 1.3 Rayleigh Distribution

For Rayleigh fading:

$$p(\alpha) = \frac{\alpha}{\sigma^2} \exp\left(-\frac{\alpha^2}{2\sigma^2}\right), \quad \alpha \geq 0$$

where $\sigma^2 = E[\alpha^2]/2$ is the variance.

The squared amplitude $|\alpha|^2$ follows exponential distribution:

$$p(|\alpha|^2) = \frac{1}{2\sigma^2} \exp\left(-\frac{|\alpha|^2}{2\sigma^2}\right)$$

---

## 2. Conditional Error Probability

### 2.1 BPSK in AWGN

For BPSK modulation in AWGN (assuming perfect channel state):

$$P(e|\gamma_b) = Q\left(\sqrt{2\gamma_b}\right)$$

where the Q-function is:

$$Q(x) = \frac{1}{\sqrt{2\pi}} \int_x^{\infty} e^{-t^2/2} dt$$

### 2.2 Derivation

For BPSK, the transmitted signals are:

$$s_1(t) = \sqrt{\frac{2E_b}{T_b}} \cos(2\pi f_c t)$$

$$s_0(t) = -\sqrt{\frac{2E_b}{T_b}} \cos(2\pi f_c t)$$

The decision boundary is at 0. With received amplitude $A = \alpha \sqrt{E_b}$:

$$P_e = P(A > 0) \cdot P(n > A) + P(A < 0) \cdot P(n < A)$$

Since signal is equally likely:

$$P_e = \frac{1}{2} Q\left(\frac{A}{\sigma_n}\right) + \frac{1}{2} Q\left(\frac{A}{\sigma_n}\right) = Q\left(\sqrt{2\gamma_b}\right)$$

---

## 3. PDF of SNR in Rayleigh Fading

### 3.1 Derivation

Since $|\alpha|^2$ is exponentially distributed with mean $E[|\alpha|^2]$:

$$\bar{\gamma}_b = E\left[\frac{|\alpha|^2 E_b}{N_0}\right] = \frac{E_b}{N_0} \cdot E[|\alpha|^2]$$

Substituting into exponential PDF:

$$p(\gamma_b) = \frac{1}{\bar{\gamma}_b} \exp\left(-\frac{\gamma_b}{\bar{\gamma}_b}\right), \quad \gamma_b \geq 0$$

### 3.2 Properties

| Property | Expression |
|----------|------------|
| Mean | $E[\gamma_b] = \bar{\gamma}_b$ |
| Variance | $\text{Var}(\gamma_b) = \bar{\gamma}_b^2$ |
| CDF | $F(\gamma_b) = 1 - e^{-\gamma_b/\bar{\gamma}_b}$ |

---

## 4. Average Error Probability Derivation

### 4.1 Mathematical Formulation

The average error probability is obtained by **averaging** the conditional error probability over the fading distribution:

$$P_b = \int_0^{\infty} P(e|\gamma_b) \cdot p(\gamma_b) \, d\gamma_b$$

$$P_b = \int_0^{\infty} Q\left(\sqrt{2\gamma_b}\right) \cdot \frac{1}{\bar{\gamma}_b} \exp\left(-\frac{\gamma_b}{\bar{\gamma}_b}\right) d\gamma_b$$

### 4.2 Solution Using Integration Identity

Using the identity:

$$\int_0^\infty Q(\sqrt{2x}) e^{-x/a} \, dx = \frac{1}{2}\left(1 - \sqrt{\frac{a}{1+a}}\right)$$

With $a = \bar{\gamma}_b$:

$$\boxed{P_b = \frac{1}{2}\left(1 - \sqrt{\frac{\bar{\gamma}_b}{1 + \bar{\gamma}_b}}\right)}$$

> [!KEY POINT]
> This is the **exact** average bit error probability for BPSK in Rayleigh flat fading.

### 4.3 Alternative Forms

The result can also be expressed as:

$$P_b = \frac{1}{2} \left[ 1 - \frac{1}{\sqrt{1 + 1/\bar{\gamma}_b}} \right]$$

or using the relationship with the geometry of hyperbolic functions:

$$P_b = \frac{1}{2} \left(1 - \frac{1}{\sqrt{1 + \bar{\gamma}_b^{-1}}}\right)$$

---

## 5. Special Case Analysis

### 5.1 High SNR Approximation

When $\bar{\gamma}_b \gg 1$:

$$\sqrt{\frac{\bar{\gamma}_b}{1 + \bar{\gamma}_b}} = \sqrt{1 - \frac{1}{1 + \bar{\gamma}_b}} \approx 1 - \frac{1}{2\bar{\gamma}_b}$$

Therefore:

$$P_b \approx \frac{1}{2} \left[1 - \left(1 - \frac{1}{2\bar{\gamma}_b}\right)\right] = \frac{1}{4\bar{\gamma}_b}$$

> [!TIP]
> At high SNR, Rayleigh fading causes a **3 dB penalty** compared to AWGN (where $P_b \approx 1/2\bar{\gamma}_b$).

### 5.2 Low SNR Approximation

When $\bar{\gamma}_b \ll 1$:

$$\sqrt{\frac{\bar{\gamma}_b}{1 + \bar{\gamma}_b}} \approx \sqrt{\bar{\gamma}_b}$$

So:

$$P_b \approx \frac{1}{2}(1 - \sqrt{\bar{\gamma}_b}) \approx \frac{1}{2} - \frac{1}{2}\sqrt{\bar{\gamma}_b}$$

At very low SNR, error probability approaches 0.5 (random guessing).

### 5.3 Numerical Comparison

| $\bar{\gamma}_b$ (dB) | AWGN $P_b$ | Rayleigh $P_b$ | Penalty (dB) |
|---------------------|-----------|-----------------|--------------|
| 5 | 3.1×10⁻³ | 8.6×10⁻² | ~14 dB |
| 10 | 3.9×10⁻⁶ | 4.5×10⁻³ | ~10 dB |
| 20 | 2.2×10⁻¹¹ | 2.3×10⁻⁵ | ~6 dB |
| 30 | 3.9×10⁻¹⁶ | 2.5×10⁻⁷ | ~4 dB |

---

## 6. Outage Probability

### 6.1 Definition

Outage occurs when the instantaneous SNR falls below a threshold $\gamma_{th}$ required for reliable communication:

$$P_{out} = P(\gamma_b < \gamma_{th})$$

### 6.2 Derivation

For Rayleigh fading:

$$P_{out} = \int_0^{\gamma_{th}} p(\gamma_b) \, d\gamma_b = \int_0^{\gamma_{th}} \frac{1}{\bar{\gamma}_b} e^{-\gamma_b/\bar{\gamma}_b} d\gamma_b$$

$$P_{out} = 1 - e^{-\gamma_{th}/\bar{\gamma}_b}$$

### 6.3 Finding Threshold SNR

For BPSK with target BER $P_{target}$:

$$P_{target} = Q(\sqrt{2\gamma_{th}})$$

Solving for $\gamma_{th}$:

$$\sqrt{2\gamma_{th}} = Q^{-1}(P_{target})$$

$$\gamma_{th} = \frac{[Q^{-1}(P_{target})]^2}{2}$$

### 6.4 Common Threshold Values

| Target BER | $\gamma_{th}$ (linear) | $\gamma_{th}$ (dB) |
|----------|---------------------|---------------------|
| 10⁻² | 2.67 | 4.3 dB |
| 10⁻³ | 4.67 | 6.7 dB |
| 10⁻⁴ | 6.92 | 8.4 dB |
| 10⁻⁵ | 9.34 | 9.7 dB |
| 10⁻⁶ | 11.9 | 10.8 dB |

---

## 7. Example: 90% Reliability Requirement

> [!EXAMPLE]
> **Problem:** Find the average SNR such that 90% of the time, BER < 10⁻⁴.
>
> **Solution:**
>
> **Step 1:** Find threshold for BER = 10⁻⁴
> $$\gamma_{th} = \frac{[Q^{-1}(10^{-4})]^2}{2} = \frac{13.83}{2} = 6.92$$
>
> **Step 2:** For 90% reliability (10% outage)
> $$P_{out} = 1 - e^{-\gamma_{th}/\bar{\gamma}_b} = 0.1$$
> $$e^{-\gamma_{th}/\bar{\gamma}_b} = 0.9$$
> $$\bar{\gamma}_b = \frac{6.92}{-\ln(0.9)} = \frac{6.92}{0.1054} = 65.66$$
>
> **Step 3:** Convert to dB
> $$\bar{\gamma}_b(dB) = 10\log_{10}(65.66) = 18.2 \text{ dB}$$

---

## 8. Comparison with Other Modulation Schemes

> [!TIP]
> The average error probability for different modulations in Rayleigh fading follows similar form.

| Modulation | Average $P_b$ |
|------------|---------------|
| BPSK | $\frac{1}{2}\left(1 - \sqrt\frac{\bar{\gamma}_b}{1 + \bar{\gamma}_b}\right)$ |
| DBPSK | $\frac{1}{2\bar{\gamma}_b}$ (approx for high SNR) |
| Coherent QPSK | Same as BPSK |
| Non-coherent FSK | $\frac{1}{2\bar{\gamma}_b(1 + \bar{\gamma}_b)}$ |

---

## 9. DiversityGain

### 9.1 Concept

Diversity techniques improve performance by providing multiple independent copies of the transmitted signal. With $M$-branch diversity:

$$P_b \approx \frac{1}{\bar{\gamma}_b^M} \cdot \frac{1}{2^M}$$

The diversity order $M$ provides significant improvement.

### 9.2 With MRC

For Maximum Ratio Combining with $M$ branches:

$$P_b^{(M)} \approx \frac{1}{\bar{\gamma}_b^M} \cdot \frac{1}{2^M} \cdot \frac{(2M-1)!!}{2^M M!}$$

---

## 10. Key Takeaways

> [!KEY POINT]
> 1. **Average Error Probability**: $P_b = \frac{1}{2}\left(1 - \sqrt{\frac{\bar{\gamma}_b}{1 + \bar{\gamma}_b}}\right)$
> 
> 2. **Diversity Order**: Each diversity branch improves error rate by ~1/$\bar{\gamma}_b$
> 
> 3. **High SNR Behavior**: Error floor drops as $1/\bar{\gamma}_b$ with 3 dB penalty vs AWGN
> 
> 4. **Outage Probability**: $P_{out} = 1 - e^{-\gamma_{th}/\bar{\gamma}_b}$
> 
> 5. **Adaptation**: Use adaptive modulation/coding to maintain target BER

---

## 11. Summary Table

| Parameter | Expression |
|-----------|------------|
| Conditional $P_e$ | $Q(\sqrt{2\gamma_b})$ |
| SNR PDF | $\frac{1}{\bar{\gamma}_b} e^{-\gamma_b/\bar{\gamma}_b}$ |
| Average $P_e$ | $\frac{1}{2}(1 - \sqrt{\frac{\bar{\gamma}_b}{1 + \bar{\gamma}_b}})$ |
| High SNR $P_e$ | $\frac{1}{4\bar{\gamma}_b}$ |
| Outage $P_{out}$ | $1 - e^{-\gamma_{th}/\bar{\gamma}_b}$ |
| Diversity order | $M$ branches → $P_e \propto 1/\bar{\gamma}_b^M$ |