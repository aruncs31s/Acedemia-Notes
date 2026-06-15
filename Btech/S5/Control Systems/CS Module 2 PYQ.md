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
