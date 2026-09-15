

### **Expansions for Core Concepts**

**1 & 2. Open vs. Closed Loop Systems**

- **Addition:** Mention the primary drawback of closed-loop systems. While they improve accuracy and handle disturbances, the addition of feedback can cause a system that is originally stable to become **unstable** if the feedback gain is not carefully tuned.
    

**3 & 4. State Space Representation**

- **Addition:** One of the most significant advantages of state-space over traditional transfer functions is that it can easily handle **Non-Linear** and **Time-Varying** systems, whereas standard Laplace transfer functions are strictly limited to Linear Time-Invariant (LTI) systems.
    

**11. Order and Type of System**

- **Addition:** Connect these to real-world behavior.
    
    - **Order:** Determines the physical number of energy-storing elements in the system (like capacitors/inductors in circuits, or masses/springs in mechanical systems) and dictates the number of state variables.
        
    - **Type:** Determines the system's steady-state error performance. A higher "Type" number means the system can track more complex inputs (step, ramp, parabolic) with zero steady-state error.
        

**12 & 13. Nyquist and Argument Principle**

- **Clarification:** Be very careful with the sign convention for $N$. In the standard textbook definition (like Ogata or Nise):
    
    $$Z = N + P$$
    
    Where $N$ is the number of **clockwise** encirclements of the $-1+j0$ point. If the contour encircles the point counter-clockwise, $N$ is taken as negative.
    

**14 & 15. Gain Margin & Phase Margin**

- **Addition:** Define the specific frequencies involved.
    
    - **Phase Crossover Frequency ($\omega_{pc}$):** The frequency at which the phase angle is exactly $-180^\circ$. This is used to find Gain Margin.
        
    - **Gain Crossover Frequency ($\omega_{gc}$):** The frequency at which the magnitude $|G(j\omega)H(j\omega)| = 1$ (or 0 dB). This is used to find Phase Margin.
        

### **Expanded Controller & Compensator Comparisons**

Your points on compensators and controllers are good, but adding their frequency response characteristics and potential drawbacks will make your answers bulletproof.

**16 & 17. Lead and Lag Compensators**

- **Phase Lead:** Acts essentially as a **High-Pass Filter**. While it improves transient response and phase margin, it also amplifies high-frequency noise.
    
- **Phase Lag:** Acts essentially as a **Low-Pass Filter**. It improves steady-state error by adding gain at low frequencies but inherently slows down the system's transient response.
    

**18. P, PI, and PID Controllers**

Here is a more comprehensive table for your notes that includes the negative side-effects of each control action:

|**Controller**|**Primary Advantage**|**Primary Disadvantage**|
|---|---|---|
|**P**|Decreases rise time.|Leaves a steady-state error (offset).|
|**PI**|Eliminates steady-state error.|Adds a pole at the origin, which decreases relative stability and slows down the response.|
|**PD**|Improves damping and transient response.|Amplifies high-frequency noise (since the derivative of a noisy signal is very large).|
|**PID**|Optimizes both transient and steady-state responses.|Complex to tune and retains the noise amplification issue from the D-term.|

### **Additional Properties for State Variables**

**19. State Transition Matrix**

- **Addition:** Add the semi-group property to your list of properties. It frequently appears in multiple-choice or short-answer questions:
    
    $$\phi(t_1 + t_2) = \phi(t_1)\phi(t_2)$$
    

**20 & 21. Controllability & Observability**

- **Addition:** If a system is represented in the diagonal (canonical) form, controllability and observability can be determined simply by looking at the matrices. If any row of the $B$ matrix is entirely zero, the corresponding mode is uncontrollable. If any column of the $C$ matrix is entirely zero, the corresponding mode is unobservable.