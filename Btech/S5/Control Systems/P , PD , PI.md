
### 1. P Controller (Proportional)

The P controller provides an output directly proportional to the current error: $u(t) = K_p e(t)$.

- **How it works:** It acts like a spring—the further you are from the target, the harder it pushes toward it.
    
- **Pros:** Simple to implement; increases the speed of system response (rise time decreases).
    
- **Cons:** It cannot eliminate "steady-state error" (the system will often settle slightly off the target) and, if the gain ($K_p$) is set too high, it causes the system to overshoot and oscillate.
    

### 2. PI Controller (Proportional-Integral)

The PI controller adds an integral term to address the error that the P controller leaves behind: $u(t) = K_p e(t) + K_i \int e(t) dt$.

- **How it works:** The integral term continuously sums up the accumulated error over time. If the system is still off-target, this "memory" of the error grows, forcing the controller to output more power until the error is zero.
    
- **Pros:** Successfully eliminates steady-state error.
    
- **Cons:** Adding the integral term makes the system more "sluggish" and prone to overshoot because the controller has a "memory" of past errors that it must "unlearn."
    

### 3. PID Controller (Proportional-Integral-Derivative)

The PID controller adds a derivative term to anticipate future error: $u(t) = K_p e(t) + K_i \int e(t) dt + K_d \frac{de(t)}{dt}$.

- **How it works:** The derivative term looks at the _rate of change_ of the error. If the system is approaching the setpoint rapidly, the D-term provides a "braking" effect to prevent overshooting.
    
- **Pros:** Combines the speed of P, the accuracy of PI, and the stability/damping of D. It is the gold standard for industrial control.
    
- **Cons:** More complex to "tune" (finding the right $K_p, K_i, K_d$ values) and the derivative term is sensitive to "noise" in sensor data, which can cause jittery output.
    

### Comparison Summary

| **Feature**            | **P Controller**    | **PI Controller** | **PID Controller** |
| ---------------------- | ------------------- | ----------------- | ------------------ |
| **Steady-State Error** | Present             | Eliminated        | Eliminated         |
| **Speed (Rise Time)**  | Fast                | Moderate          | Fast (controlled)  |
| **Stability**          | Low (if $K_p$ high) | Moderate          | High               |
| **Complexity**         | Very Low            | Moderate          | High               |

