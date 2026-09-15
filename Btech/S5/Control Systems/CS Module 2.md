---
tags:
  - ect307
---
# Module 2 **Time Domain Analysis of Control Systems**

- **Introduction:** Standard Test signals, Time response specifications.
- **Time response:** First and second-order systems to unit step input and ramp inputs, time domain specifications.
- **Errors:** Steady state error and static error coefficients.
- **Frequency domain analysis:** Frequency domain specifications, correlation between time and frequency responses.


does this explain about rise time , settling time and steady state errors? 

https://youtu.be/KuKGfMm1reE?si=xnC2hySCySCu6eaz




### Time-Domain Specifications

- **Rise time ($t_r$)**
    $$t_r = \frac{\pi - \theta}{\omega_d}$$
    
- **Peak time ($t_p$)**
    
    $$t_p = \frac{\pi}{\omega_d} = \frac{\pi}{\omega_n\sqrt{1-\zeta^2}}$$
    
- **% Peak overshoot ($M_p$)**
    
    $$\% M_p = e^{\frac{-\pi\zeta}{\sqrt{1-\zeta^2}}} \times 100$$
    
- **Settling time ($t_s$)**
    
    $$t_s = \frac{4}{\zeta\omega_n} \quad \text{for 2\% error (Tolerance band)}$$
    
    $$t_s = \frac{3}{\zeta\omega_n} \quad \text{for 5\% error}$$