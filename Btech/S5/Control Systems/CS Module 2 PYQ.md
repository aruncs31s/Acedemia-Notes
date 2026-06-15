---
tags:
  - pyq
  - ect307
---

## Question 13 a): Define position, velocity, and acceleration error constants for a unity feedback control system
In a unity feedback control system, the steady-state error (the difference between the desired input and the actual output as time approaches infinity) depends on the type of input applied and the system's open-loop transfer function, denoted as $G(s)$.

To quantify this, control theory uses three static error constants: position, velocity, and acceleration.

### 1. Position Error Constant ($K_p$)

The position error constant defines the system's ability to reduce steady-state error when subjected to a **unit step input** (a sudden, constant change in the desired reference).
- **Definition:**
$$K_p = \lim_{s \to 0} G(s)$$
- **Steady-State Error ($e_{ss}$):**
$$e_{ss} = \frac{1}{1 + K_p}$$
- **System Type Implication:** For a system to perfectly track a step input with zero steady-state error, $K_p$ must be infinite. This naturally occurs in Type 1 systems (systems with at least one integrator at the origin).

### 2. Velocity Error Constant ($K_v$)

The velocity error constant defines the system's ability to reduce steady-state error when subjected to a **unit ramp input** (a reference signal changing at a constant velocity).

- **Definition:**
$$K_v = \lim_{s \to 0} s G(s)$$
- **Steady-State Error ($e_{ss}$):**
$$e_{ss} = \frac{1}{K_v}$$
- **System Type Implication:** To track a ramp input with zero steady-state error, $K_v$ must be infinite. This requires a Type 2 system (at least two integrators at the origin). For a Type 1 system, the error will be a finite, non-zero constant.
    

### 3. Acceleration Error Constant ($K_a$)

The acceleration error constant defines the system's ability to reduce steady-state error when subjected to a **unit parabolic input** (a reference signal changing at a constant acceleration).
- **Definition:**
    $$K_a = \lim_{s \to 0} s^2 G(s)$$
- **Steady-State Error ($e_{ss}$):**
$$e_{ss} = \frac{1}{K_a}$$
- **System Type Implication:** To track a parabolic input with zero steady-state error, $K_a$ must be infinite. This requires a Type 3 system (at least three integrators at the origin).

### Summary Reference Table

|**Error Constant**|**Symbol**|**Test Input**|**Formula**|**Steady-State Error (ess​)**|
|---|---|---|---|---|
|**Position**|$K_p$|Unit Step|$\lim_{s \to 0} G(s)$|$\frac{1}{1 + K_p}$|
|**Velocity**|$K_v$|Unit Ramp|$\lim_{s \to 0} s G(s)$|$\frac{1}{K_v}$|
|**Acceleration**|$K_a$|Unit Parabolic|$\lim_{s \to 0} s^2 G(s)$|$\frac{1}{K_a}$|
## Question 13 b): For the second-order system with complex poles on the left half of the s-plane, derive the expression for rise time, settling time, and steady-state error parameters

To derive these expressions, we must first establish the foundation of our system. A standard **second-order closed-loop transfer** function is given by:

$$T(s) = \frac{C(s)}{R(s)} = \frac{\omega_n^2}{s^2 + 2\zeta\omega_n s + \omega_n^2}$$

Because the system has complex poles in the left half of the s-plane, it is an **underdamped system**, meaning the damping ratio is $0 < \zeta < 1$.

To derive the time-domain specifications (rise time and settling time), we analyze the system's response to a unit step input ($R(s) = \frac{1}{s}$). Taking the inverse Laplace transform yields the time-domain step response:

$$c(t) = 1 - \frac{e^{-\zeta\omega_n t}}{\sqrt{1-\zeta^2}} \sin(\omega_d t + \theta)$$

Where:

- **$\omega_n$** is the undamped natural frequency.
    
- **$\omega_d = \omega_n\sqrt{1-\zeta^2}$** is the damped natural frequency.
    
- **$\theta = \tan^{-1}\left(\frac{\sqrt{1-\zeta^2}}{\zeta}\right)$** or equivalently $\theta = \cos^{-1}(\zeta)$.
    

### 1. Derivation of Rise Time ($t_r$)

**Definition:** For an underdamped system, the rise time is the time required for the step response $c(t)$ to reach 100% of its final steady-state value (which is 1) for the very first time.

**Derivation:**

We set $c(t_r) = 1$ and solve for $t_r$:

$$1 = 1 - \frac{e^{-\zeta\omega_n t_r}}{\sqrt{1-\zeta^2}} \sin(\omega_d t_r + \theta)$$

Subtracting 1 from both sides gives:

$$0 = - \frac{e^{-\zeta\omega_n t_r}}{\sqrt{1-\zeta^2}} \sin(\omega_d t_r + \theta)$$

Since the exponential term $\frac{e^{-\zeta\omega_n t_r}}{\sqrt{1-\zeta^2}}$ cannot be zero at a finite time, the sine term must be zero:

$$\sin(\omega_d t_r + \theta) = 0$$

The sine function equals zero at integer multiples of $\pi$ ($0, \pi, 2\pi, \dots$). Since we want the _first_ time the response crosses 1, we set the argument to $\pi$:

$$\omega_d t_r + \theta = \pi$$

Solving for $t_r$, we get the final expression for rise time:

$$t_r = \frac{\pi - \theta}{\omega_d}$$

### 2. Derivation of Settling Time ($t_s$)

**Definition:** The settling time is the time required for the response curve to reach and remain within a specified tolerance band (usually 2% or 5%) of the final steady-state value.

**Derivation:**

Looking at the step response equation $c(t)$, the term $\sin(\omega_d t + \theta)$ causes the oscillation, while the term $e^{-\zeta\omega_n t}$ dictates the rate at which those oscillations decay. The decaying exponential acts as an envelope wrapping the oscillations.

To find when the response settles, we only need to look at this exponential envelope:

$$Envelope = \frac{e^{-\zeta\omega_n t}}{\sqrt{1-\zeta^2}}$$

For most practical engineering derivations, $\sqrt{1-\zeta^2}$ is approximated as $1$ because settling time is a conservative estimate. Thus, the envelope bounding the error is approximately $e^{-\zeta\omega_n t}$.

**For a 2% tolerance band:**

We find the time $t_s$ when the decaying envelope reaches 0.02:

$$e^{-\zeta\omega_n t_s} = 0.02$$

Taking the natural logarithm of both sides:

$$-\zeta\omega_n t_s = \ln(0.02) \approx -4$$

$$t_s = \frac{4}{\zeta\omega_n}$$

**For a 5% tolerance band:**

We find the time $t_s$ when the decaying envelope reaches 0.05:

$$e^{-\zeta\omega_n t_s} = 0.05$$

Taking the natural logarithm of both sides:

$$-\zeta\omega_n t_s = \ln(0.05) \approx -3$$

$$t_s = \frac{3}{\zeta\omega_n}$$

### 3. Derivation of Steady-State Error Parameters

To find the steady-state error parameters ($K_p$, $K_v$, $K_a$), we must determine the system's **open-loop transfer function**, $G(s)$, assuming a unity feedback configuration.

We know the closed-loop transfer function is $T(s) = \frac{G(s)}{1 + G(s)}$. Rearranging this to solve for $G(s)$:

$$G(s) = \frac{T(s)}{1 - T(s)}$$

Substitute the standard second-order $T(s)$:

$$G(s) = \frac{\frac{\omega_n^2}{s^2 + 2\zeta\omega_n s + \omega_n^2}}{1 - \frac{\omega_n^2}{s^2 + 2\zeta\omega_n s + \omega_n^2}}$$

$$G(s) = \frac{\omega_n^2}{s^2 + 2\zeta\omega_n s + \omega_n^2 - \omega_n^2}$$

$$G(s) = \frac{\omega_n^2}{s^2 + 2\zeta\omega_n s} = \frac{\omega_n^2}{s(s + 2\zeta\omega_n)}$$

Because there is one lonely $s$ in the denominator (a single pole at the origin), **this is a Type 1 system**.

Now we calculate the error constants and their resulting steady-state errors ($e_{ss}$):

**1. Position Error Constant ($K_p$) & Step Input Error**

$$K_p = \lim_{s \to 0} G(s) = \lim_{s \to 0} \frac{\omega_n^2}{s(s + 2\zeta\omega_n)} = \infty$$

- **$e_{ss}$ (Step):**
    
    $$e_{ss} = \frac{1}{1 + K_p} = \frac{1}{\infty} = 0$$
    

**2. Velocity Error Constant ($K_v$) & Ramp Input Error**

$$K_v = \lim_{s \to 0} s G(s) = \lim_{s \to 0} s \left[ \frac{\omega_n^2}{s(s + 2\zeta\omega_n)} \right] = \lim_{s \to 0} \frac{\omega_n^2}{s + 2\zeta\omega_n} = \frac{\omega_n^2}{2\zeta\omega_n} = \frac{\omega_n}{2\zeta}$$

- **$e_{ss}$ (Ramp):**
    
    $$e_{ss} = \frac{1}{K_v} = \frac{2\zeta}{\omega_n}$$
    

**3. Acceleration Error Constant ($K_a$) & Parabolic Input Error**

$$K_a = \lim_{s \to 0} s^2 G(s) = \lim_{s \to 0} s^2 \left[ \frac{\omega_n^2}{s(s + 2\zeta\omega_n)} \right] = \lim_{s \to 0} \frac{s \cdot \omega_n^2}{s + 2\zeta\omega_n} = \frac{0 \cdot \omega_n^2}{2\zeta\omega_n} = 0$$

- **$e_{ss}$ (Parabolic):**
    
    $$e_{ss} = \frac{1}{K_a} = \frac{1}{0} = \infty$$