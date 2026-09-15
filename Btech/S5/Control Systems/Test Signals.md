In control systems, **test signals** are used to analyze the performance and stability of a system. 

### Standard Test Signals

1. **Impulse Function (Dirac Delta):** Represents a sudden, short-duration input.
   $$r(t) = A\delta(t), \quad R(s) = A$$

2. **Step Function:** Represents a sudden change in input that remains constant.
   $$r(t) = A u(t), \quad R(s) = \frac{A}{s}$$

3. **Ramp Function:** Represents an input that increases linearly with time.
   $$r(t) = At u(t), \quad R(s) = \frac{A}{s^2}$$

4. **Parabolic Function:** Represents an input with constant acceleration.
   $$r(t) = \frac{At^2}{2} u(t), \quad R(s) = \frac{A}{s^3}$$

In these equations, $A$ represents the **magnitude** of the signal, $r(t)$ is the time-domain representation, and $R(s)$ is the Laplace transform of the signal.