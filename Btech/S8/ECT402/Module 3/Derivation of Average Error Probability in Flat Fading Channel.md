Derivation: Average Error Probability of BPSK in Rayleigh Fading
Step 1: Conditional Error Probability
$$P(e|\gamma_b) = Q(\sqrt{2\gamma_b})$$
Step 2: SNR Distribution (Exponential)
$$p(\gamma_b) = \frac{1}{\bar{\gamma}_b} e^{-\gamma_b/\bar{\gamma}_b}, \quad \gamma_b \geq 0$$
Step 3: Average over Fading
$$\overline{P}_b = \int_0^\infty Q(\sqrt{2\gamma_b}) \cdot \frac{1}{\bar{\gamma}_b} e^{-\gamma_b/\bar{\gamma}_b} d\gamma_b$$
Step 4: Using Integral Identity
$$\int_0^\infty Q(\sqrt{2x}) e^{-x/a} dx = \frac{1}{2}\left(1 - \sqrt{\frac{a}{1+a}}\right)$$
Step 5: Final Answer
$$\boxed{\overline{P}_b = \frac{1}{2}\left[1 - \sqrt{\frac{\bar{\gamma}_b}{1 + \bar{\gamma}_b}}\right]}$$
High SNR (write if asked):
$$\overline{P}_b \approx \frac{1}{4\bar{\gamma}_b}$$