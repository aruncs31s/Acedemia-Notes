# Module 5

# ADC Module 5

#### BPSK

^77bd04

Coherent Binary Phase Shift Keying

$$
s_1(t) = A \cos(2\pi f_ct )\tag{1}
$$

$$
s_2(t) = -A \cos (2 \pi f_ct)\tag{2}
$$

- Amplitude in terms of _bit energy($E_b$)_ and _Bit Duration($T_b$)_

$$
\begin{align}
Power &= \frac{E_b}{T_b}\tag{3}\\
Rms \ Value = \frac{A}{\sqrt{2}}
&= \frac{A^2}{\sqrt{2}}\tag{4}
\end{align}
$$

By comparing equation(3) and (4)

$$
\begin{align}
\frac{A^2}{\sqrt{2}} &= \frac{E_b}{T_b} \\
A &= \sqrt{\frac{2 E_b }{T}}
\end{align}
$$

now

$$
\boxed{\color{cyan}
\begin{align}
s_1(t) &= \sqrt{\frac{2 E_b }{T}}\cos(2\pi f_ct )\\
s_2(t) &=  \sqrt{\frac{2 E_b }{T}}\cos (2 \pi f_ct)
\end{align}
}
$$

> [!NOTE] Antipodal Signals
> Since $S_1(t)$ and $S_2(t)$ are in $180^o$ out of phase they are called Antipodal Signals

---

$$
\begin{align}
\Phi_1(t) &= {S_1(t) \over \sqrt{E_b}} \\
S_1(t) &= \sqrt{Eb} \frac{2}{T_b} \cos(\pi f_c t) \\
\end{align}
$$

by comparing above equation

$$
\Phi_1(t) = \sqrt{{2\over T_b}  \cos(\pi f_c t)  }
$$

$$
\begin{align}
S_1(t) = \sqrt{E_b} \Phi_1(t) \tag{a}\\
S_2(t) = -\sqrt{E_b} \Phi_1(t) \tag{b}\\
\end{align}
$$

\*For BPSK we only need 1 orthonormal basis function => $\Phi_1{t}$

## BPSK Error Probability

Binary Phase Shift Keying (BPSK) is a digital modulation scheme where binary data (0s and 1s) is represented by shifting the phase of a carrier signal by 0° or 180°.

The bit error probability (BER) for BPSK in an Additive White Gaussian Noise (AWGN) channel is given by:

$$ P_e = Q\left(\sqrt{\frac{2E_b}{N_0}}\right) $$

where:
- $E_b$ is the energy per bit,
- $N_0$ is the noise power spectral density,
- $Q(x)$ is the tail probability of the standard normal distribution, defined as $Q(x) = \frac{1}{\sqrt{2\pi}} \int_x^\infty e^{-t^2/2} \, dt$.

This formula assumes coherent detection and ideal synchronization. For non-coherent detection, the BER is higher, approximately $ \frac{1}{2} e^{-E_b/(2N_0)} $. In fading channels, the error probability depends on the fading model (e.g., Rayleigh fading).

### Related Notes
- [[AC_Module_4]] - Previous module on modulation basics
- [[Digital Communication Systems]] - Overview
