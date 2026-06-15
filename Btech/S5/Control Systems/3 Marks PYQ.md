Here is the complete list of the 3-mark Part A questions extracted from the provided Control Systems exam papers.

### **December 2023 (2019 Scheme)**

1. Draw the basic block diagram for a closed loop control system. What are the advantages of closed loop control system over open loop control system?
    
2. Define the term "state" in the state variable representation. Write the state equation and output equation for a linear system.
    
3. Write the time domain and Laplace domain expressions of unit step, unit ramp, and unit parabolic test inputs.
    
4. Explain the term determinant of a signal flow graph. Where does it appear in a transfer function?
    
5. Define the BIBO stability. What is the condition on the impulse response for stability?
    
6. Define the angle and magnitude criteria of root locus on the open-loop transfer function of a system.
    
7. Draw the s-plane contour used for mapping, for stability analysis, to the plane of open-loop transfer function $G(s)H(s)=\frac{1}{s(s+1)}$. Explain the choice of the contour.
    
8. Derive and plot the response of a first order unity negative feedback system to unit step input.
    
9. Find the state equation for the system represented by the differential equation $\frac{d^{2}y}{dt^{2}}+20\frac{dy}{dt}+100y=u(t)$ where, $u(t)$ is the input and $y(t)$ is the output. Take zero initial conditions.
    
10. Write the transfer function of a first order phase lead compensator. State the function of a phase lead compensator in a control system.
    

### **December 2022 (2019 Scheme)**

1. Compare open loop and closed loop control systems. Give example.
    
2. Obtain the impulse response of a series RL high pass filter.
    
3. A unity feedback system has the following forward path transfer function $G(s)=\frac{180}{s(s+6)}$ and $r(t)=4t$. Determine the corresponding static error coefficient and the steady state error.
    
4. Compare the features of transient and steady state part of a system response. Give an example for a second order control system with natural frequency of 2 rad/s and damping ratio of 0.5.
    
5. Explain absolute stability and relative stability of control systems.
    
6. Compare PD, PI and PID controllers.
    
7. Obtain the DC gain of a unity feedback control system whose overall transfer function is given by $T(s)=\frac{10}{(s+3)(s+5)}$.
    
8. Starting with the principle of argument, state Nyquist stability criterion.
    
9. Define state transition matrix. Mention any four properties of it.
    
10. Define the terms state variable and state space. Mention any four distinct advantages of state space representation.
    

### **December 2021 (2019 Scheme)**

1. Compare open loop and closed loop control systems. Give one example to both.
    
2. What is the criterion on the roots of the characteristic equation for the stability? How is it connected to the BIBO stability?
    
3. Draw the signal flow graph for the following set of algebraic equations: $x_{1}=ax_{0}+bx_{1}+cx_{2}$, $x_{2}=dx_{1}+ex_{3}$
    
4. State the angle and magnitude criteria that roots of the characteristic equation must be satisfied.
    
5. In a system represented by the state vector differential equation, let $A$ is the coefficient matrix of the state variable vector. Then, if $A=[\begin{matrix}0&1\\ -1&-1\end{matrix}]$ find the characteristic roots of the system.
    
6. Draw the response of an underdamped second order system with complex poles on the left half of s-plane showing the rise time, peak overshoot, and settling time.
    
7. Distinguish between Order of a system and Type of a system.
    
8. Draw the s-plane contour used for mapping, for stability analysis, to the plane of open-loop transfer function $G(s)H(s)=\frac{1}{s(s+1)}$. Explain the choice of the contour.
    
9. Write and explain the transfer function for a first order phase lag compensator. State the function of a phase lag compensator in a control system.
    
10. Give two advantages for using state variable representation of systems.
    

### **Model Question Paper**

1. Draw the signal flow graph for the following set of algebraic equations: $x_{1}=ax_{0}+bx_{1}+cx_{2}$, $x_{2}=dx_{1}+ex_{3}$
    
2. Using block diagram reduction techniques find $C(s)/R(s)$ for the given system _(Requires referring to the specific block diagram in the exam paper)_.
    
3. Derive the expression for peak time of a second order system.
    
4. Determine the parabolic error constant for the unity feedback control system $G(s) =10(s+2)/(s+1)s^{2}$.
    
5. Using Routh Hurwitz criterion, determine the number of roots in the right half of S-plane for the system $S^{4}+2S^{3}+10S^{2}+20S+5=0$.
    
6. Compare PI, PD and PID controllers.
    
7. State and explain Nyquist Stability criteria.
    
8. Briefly describe the design procedure of a lead compensator.
    
9. A dynamic system is represented by the state equation: $X=[\begin{matrix}0&1&0\\ 0&0&1\\ 0&-2&-3\end{matrix}]X+[\begin{matrix}0\\ 0\\ 1\end{matrix}]r$. Check whether the system is completely controllable.
    
10. Obtain the state space representation of the given electrical system _(Requires referring to the specific circuit diagram in the exam paper)_.


Here are the concise, exam-ready answers for all the 3-mark Part A questions from the four provided Control Systems papers.

### **December 2023 (2019 Scheme)**

**1. Basic block diagram for a closed-loop system & its advantages:**

- **Diagram:** An input signal $R(s)$ enters a summing junction, followed by the forward block $G(s)$, yielding the output $C(s)$. A feedback path $H(s)$ connects the output back to the summing junction.
    
- **Advantages:** Higher accuracy, reduced sensitivity to parameter variations, improved disturbance rejection, and better bandwidth compared to open-loop systems.
    

**2. Define "state". Write the state and output equations:**

- **State:** The minimum set of variables whose knowledge at an initial time $t_0$, along with the input for $t \geq t_0$, completely determines the behavior of the system for any time $t > t_0$.
    
- **State Equation:** $\dot{x}(t) = Ax(t) + Bu(t)$
    
- **Output Equation:** $y(t) = Cx(t) + Du(t)$
    

**3. Time domain and Laplace domain expressions of test inputs:**

- **Unit Step:** $r(t) = 1$, $R(s) = \frac{1}{s}$
    
- **Unit Ramp:** $r(t) = t$, $R(s) = \frac{1}{s^2}$
    
- **Unit Parabolic:** $r(t) = \frac{t^2}{2}$, $R(s) = \frac{1}{s^3}$
    

**4. Determinant of a signal flow graph (SFG):**

- The determinant, denoted by $\Delta$, characterizes the overall feedback structure of the graph. It is calculated as $\Delta = 1 - (\text{sum of all individual loop gains}) + (\text{sum of gain products of 2 non-touching loops}) - \dots$
    
- It appears in the denominator of Mason's Gain Formula.
    

**5. BIBO stability and impulse response condition:**

- **BIBO Stability:** A system is Bounded-Input Bounded-Output stable if every bounded input results in a strictly bounded output.
    
- **Condition:** The impulse response $h(t)$ must be absolutely integrable: $\int_0^\infty |h(t)|dt < \infty$.
    

**6. Angle and magnitude criteria of root locus:**

- **Angle Criterion:** A point $s$ is on the root locus if $\angle G(s)H(s) = \pm(2k+1)180^\circ$ (where $k = 0, 1, 2, \dots$).
    
- **Magnitude Criterion:** A point $s$ is on the root locus if $|G(s)H(s)| = 1$.
    

**7. s-plane contour for $G(s)H(s)=\frac{1}{s(s+1)}$:**

- The Nyquist contour maps the entire right-half of the s-plane. It consists of the imaginary axis from $-j\infty$ to $+j\infty$ and an infinite semicircle enclosing the RHP.
    
- Because there is a pole at the origin ($s=0$), the contour must make a small semicircular detour of infinitesimal radius $r \to 0$ into the RHP to avoid passing directly through the pole.
    

**8. Response of a first-order unity negative feedback system to unit step:**

- The closed-loop transfer function is $T(s) = \frac{1}{Ts+1}$.
    
- The output is $C(s) = \frac{1}{s(Ts+1)}$. Taking the inverse Laplace transform gives the time response: $c(t) = 1 - e^{-t/T}$.
    
- **Plot:** The graph starts at 0 and rises exponentially, asymptotically approaching 1.
    

**9. State equation for $\frac{d^{2}y}{dt^{2}}+20\frac{dy}{dt}+100y=u(t)$:**

- Let $x_1 = y$ and $x_2 = \dot{y}$.
    
- The first-order differential equations are $\dot{x}_1 = x_2$ and $\dot{x}_2 = -100x_1 - 20x_2 + u$.
    
- **Matrix Form:** $\begin{bmatrix} \dot{x}_1 \\ \dot{x}_2 \end{bmatrix} = \begin{bmatrix} 0 & 1 \\ -100 & -20 \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \end{bmatrix} + \begin{bmatrix} 0 \\ 1 \end{bmatrix} u(t)$
    

**10. Transfer function and function of a phase lead compensator:**

- **Transfer Function:** $G_c(s) = K \frac{1+sT}{1+s\alpha T}$ (where $0 < \alpha < 1$).
    
- **Function:** It acts as a high-pass filter, improving the transient response, increasing the phase margin, and speeding up the system.
    

### **December 2022 (2019 Scheme)**

**1. Compare open-loop and closed-loop systems:**

- **Open-Loop:** No feedback, simpler, less accurate. (Example: Electric Toaster).
    
- **Closed-Loop:** Feedback mechanism present, more accurate, corrects for disturbances. (Example: Air conditioner with a thermostat).
    

**2. Impulse response of a series RL high pass filter:**

- Transfer function: $H(s) = \frac{sL}{R+sL} = \frac{s}{s + (R/L)} = 1 - \frac{R/L}{s + (R/L)}$
    
- Applying the inverse Laplace transform gives the impulse response: $h(t) = \delta(t) - \frac{R}{L}e^{-(R/L)t}u(t)$.
    

**3. Static error coefficient and steady-state error for $G(s)=\frac{180}{s(s+6)}$, $r(t)=4t$:**

- Because $r(t) = 4t$, the input is a ramp, so we need the Velocity Error Constant ($K_v$).
    
- $K_v = \lim_{s \to 0} s G(s) = \lim_{s \to 0} \frac{180}{s+6} = 30$.
    
- Steady-State Error $e_{ss} = \frac{A}{K_v} = \frac{4}{30} = 0.133$.
    

**4. Transient vs Steady state & 2nd order example:**

- **Transient state** is the part of the response that decays to zero as time progresses. **Steady-state** is the part of the response that remains after the transients have died out.
    
- **Example:** For $\omega_n = 2$ and $\zeta = 0.5$, the standard second-order transfer function $T(s) = \frac{\omega_n^2}{s^2 + 2\zeta\omega_n s + \omega_n^2}$ becomes $T(s) = \frac{4}{s^2 + 2s + 4}$.
    

**5. Absolute stability vs Relative stability:**

- **Absolute Stability:** A binary condition indicating whether a system is stable or unstable (all poles must be strictly in the LHP).
    
- **Relative Stability:** A quantitative measure of _how_ stable a system is, usually indicated by how far the roots are from the j$\omega$-axis, Phase Margin, and Gain Margin.
    

**6. Compare PD, PI, and PID controllers:**

- **PI:** Eliminates steady-state error but increases settling time (sluggish response).
    
- **PD:** Improves transient response and damping but amplifies high-frequency noise.
    
- **PID:** Combines both, eliminating steady-state error while maintaining a fast transient response.
    

**7. DC gain of $T(s)=\frac{10}{(s+3)(s+5)}$:**

- DC gain is found by setting $s = 0$ in the transfer function.
    
- $\text{DC Gain} = \frac{10}{(0+3)(0+5)} = \frac{10}{15} = \frac{2}{3}$.
    

**8. Nyquist stability criterion:**

- The criterion states that $Z = N + P$, where $Z$ is the number of closed-loop poles in the RHP, $N$ is the number of clockwise encirclements of the $-1+j0$ point, and $P$ is the number of open-loop poles in the RHP.
    
- For stability, $Z$ must equal $0$.
    

**9. State transition matrix and properties:**

- The state transition matrix $\phi(t) = e^{At}$ relates the state vector at time $t$ to its initial condition.
    
- **Properties:** 1) $\phi(0) = I$, 2) $\phi^{-1}(t) = \phi(-t)$, 3) $\phi(t_1+t_2) = \phi(t_1)\phi(t_2)$, 4) $[\phi(t)]^k = \phi(kt)$.
    

**10. Define state space and its advantages:**

- **State Space:** The $n$-dimensional Euclidean space formed by the $n$ state variables as coordinate axes.
    
- **Advantages:** Suitable for MIMO (Multi-Input Multi-Output) systems, applies to non-linear and time-varying systems, directly includes initial conditions, and provides information on internal states.
    

### **December 2021 (2019 Scheme)**

**1. Compare open and closed loop systems:**

- (Refer to Dec 2022, Q1).
    

**2. Stability criterion on roots & relation to BIBO:**

- For a system to be stable, all roots of the characteristic equation (closed-loop poles) must lie strictly in the left half of the s-plane. This ensures that the system's impulse response decays exponentially to zero over time, naturally satisfying the BIBO condition $\int_0^\infty |h(t)|dt < \infty$.
    

**3. SFG for $x_{1}=ax_{0}+bx_{1}+cx_{2}$, $x_{2}=dx_{1}+ex_{3}$:**

- Draw four nodes: $x_0, x_1, x_2, x_3$.
    
- Draw forward branches: $x_0 \to x_1$ (gain $a$), $x_1 \to x_2$ (gain $d$), $x_3 \to x_2$ (gain $e$).
    
- Draw feedback branches: $x_1 \to x_1$ (self-loop, gain $b$), $x_2 \to x_1$ (gain $c$).
    

**4. Angle and magnitude criteria:**

- (Refer to Dec 2023, Q6).
    

**5. Characteristic roots of $A = \begin{bmatrix} 0 & 1 \\ -1 & -1 \end{bmatrix}$:**

- Set $\det(sI - A) = 0$.
    
- $\det\left(\begin{bmatrix} s & -1 \\ 1 & s+1 \end{bmatrix}\right) = s(s+1) - (-1)(1) = s^2 + s + 1 = 0$.
    
- Using the quadratic formula: $s = \frac{-1 \pm j\sqrt{3}}{2}$.
    

**6. Sketch underdamped 2nd order response:**

- The plot starts at 0, overshoots the target value of 1, and exhibits decaying sinusoidal oscillations until it settles at 1. Key annotations to include: $t_r$ (Rise Time, first time hitting 1), $t_p$ (Peak Time, time at highest peak), $M_p$ (Maximum Peak Overshoot), and $t_s$ (Settling Time, entering a $\pm 2\%$ or $\pm 5\%$ error band).
    

**7. Order vs. Type of a system:**

- **Order:** The highest power of $s$ in the denominator of the closed-loop transfer function (the characteristic equation).
    
- **Type:** The number of open-loop poles located exactly at the origin ($s=0$).
    

**8. s-plane contour for $G(s)H(s)=\frac{1}{s(s+1)}$:**

- (Refer to Dec 2023, Q7).
    

**9. Phase lag compensator TF & function:**

- **Transfer Function:** $G_c(s) = K \frac{1+sT}{1+s\beta T}$ (where $\beta > 1$).
    
- **Function:** It acts as a low-pass filter, significantly improving the steady-state accuracy and reducing steady-state error without degrading stability.
    

**10. Two advantages of state variable representation:**

- (Refer to Dec 2022, Q10).
    

### **Model Question Paper**

**1. SFG for equations:**

- (Refer to Dec 2021, Q3).
    

**2. Block diagram reduction for $C(s)/R(s)$:**

- First, collapse the inner feedback loop containing $G_1$ and $H_1$: $G_{\text{inner}} = \frac{G_1}{1 + G_1 H_1}$.
    
- Then, collapse the outer feedback loop containing $G_{\text{inner}}$ and $H_2$: $T(s) = \frac{G_{\text{inner}}}{1 + G_{\text{inner}} H_2}$.
    
- **Final TF:** $\frac{C(s)}{R(s)} = \frac{G_1}{1 + G_1 H_1 + G_1 H_2}$.
    

**3. Expression for peak time of a second-order system:**

- Peak time $t_p$ occurs when the derivative of the step response $c(t)$ is zero for the first time. For an underdamped system, this happens at half the period of damped oscillation.
    
- $t_p = \frac{\pi}{\omega_d} = \frac{\pi}{\omega_n \sqrt{1-\zeta^2}}$.
    

**4. Parabolic error constant for $G(s) =\frac{10(s+2)}{(s+1)s^{2}}$:**

- $K_a = \lim_{s \to 0} s^2 G(s) = \lim_{s \to 0} s^2 \left( \frac{10(s+2)}{s^2(s+1)} \right) = \frac{10(0+2)}{(0+1)} = 20$.
    

**5. Routh-Hurwitz for $S^{4}+2S^{3}+10S^{2}+20S+5=0$:**

- **Row $s^4$:** $1, \quad 10, \quad 5$
    
- **Row $s^3$:** $2, \quad 20, \quad 0$
    
- **Row $s^2$:** $\frac{2(10) - 1(20)}{2} = 0 \to \epsilon, \quad \frac{2(5) - 1(0)}{2} = 5$
    
- **Row $s^1$:** $\frac{\epsilon(20) - 2(5)}{\epsilon} \approx \frac{-10}{\epsilon}$ (which is a large negative number).
    
- **Row $s^0$:** $5$
    
- Since there are two sign changes in the first column ($+$ to $-$ and $-$ to $+$), there are **2 roots** in the right half of the s-plane.
    

**6. Compare PI, PD, and PID controllers:**

- (Refer to Dec 2022, Q6).
    

**7. Nyquist Stability criteria:**

- (Refer to Dec 2022, Q8).
    

**8. Design procedure of a lead compensator:**

1. Determine system gain $K$ to meet steady-state error requirements.
    
2. Draw the Bode plot of the uncompensated system and evaluate Phase Margin.
    
3. Calculate the required additional phase lead ($\phi_m$) to meet the new specifications.
    
4. Compute the attenuation factor $\alpha = \frac{1-\sin\phi_m}{1+\sin\phi_m}$.
    
5. Determine the corner frequencies and construct the compensator.
    

**9. Check Controllability:**

- Compute the controllability matrix $Q_c = \begin{bmatrix} B & AB & A^2B \end{bmatrix}$.
    
- $B = \begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix}$. $AB = \begin{bmatrix} 0 & 1 & 0 \\ 0 & 0 & 1 \\ 0 & -2 & -3 \end{bmatrix} \begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix} = \begin{bmatrix} 0 \\ 1 \\ -3 \end{bmatrix}$. $A^2B = A(AB) = \begin{bmatrix} 1 \\ -3 \\ 7 \end{bmatrix}$.
    
- $Q_c = \begin{bmatrix} 0 & 0 & 1 \\ 0 & 1 & -3 \\ 1 & -3 & 7 \end{bmatrix}$.
    
- The determinant of $Q_c = -1$. Since $\det(Q_c) \neq 0$, the rank is 3 (full rank), meaning the system is **completely controllable**.
    

**10. State-space representation of an electrical system:**

- Assign the current through inductors ($i_L$) and the voltage across capacitors ($v_c$) as the state variables.
    
- Apply Kirchhoff's Voltage Law (KVL) for loops containing inductors to solve for $\frac{di_L}{dt}$.
    
- Apply Kirchhoff's Current Law (KCL) at nodes connecting to capacitors to solve for $\frac{dv_c}{dt}$.
    
- Formulate these differential equations into the standard $\dot{x} = Ax + Bu$ matrix format. 