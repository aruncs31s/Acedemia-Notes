---
id: Module 2 PYQ
aliases: []
tags:
  - academics
  - btech
  - s8
  - ect402
dg-publish: true
---

# Module 2 PYQ

---

## Important Equations Quick Reference

| # | Topic | Formula |
|---|-------|---------|
| **PATH LOSS** |||
| 1 | Free Space Path Loss (dB) | $PL_{dB} = 20\log_{10}\left(\frac{4\pi d}{\lambda}\right)$ |
| 2 | Friis Equation | $P_r = P_t G_t G_r \left(\frac{\lambda}{4\pi d}\right)^2$ |
| 3 | Two-Ray (far) | $P_r \propto 1/d^4$ |
| **DOPPLER** |||
| 4 | Doppler Shift | $f_d = \frac{v}{\lambda}\cos\theta = f_m\cos\theta$ |
| 5 | Max Doppler | $f_m = \frac{v}{\lambda} = \frac{v f_c}{c}$ |
| 6 | Coherence Time | $T_c \approx \frac{0.423}{f_m}$ |
| **FADING** |||
| 7 | Coherence Bandwidth | $B_c \approx \frac{1}{5\sigma_\tau}$ |
| 8 | Flat Fading Condition | $B_s < B_c$ |
| 9 | Freq-Selective Condition | $B_s > B_c$ |
| 10 | Slow Fading Condition | $T_s < T_c$ |
| 11 | Fast Fading Condition | $T_s > T_c$ |
| 12 | Rayleigh PDF | $f_R(r) = \frac{r}{\sigma^2}e^{-r^2/2\sigma^2}$ |
| **CAPACITY** |||
| 13 | AWGN Capacity | $C = B\log_2(1+SNR)$ |
| 14 | Ergodic (fading) | $C = E[\log_2(1+SNR\cdot|h|^2)]$ |
| 15 | Outage Prob | $P_{outage} = P(SNR < \rho_{min})$ |
| 16 | Capacity w/ Outage | $C_{outage} = (1-P_{outage})B\log_2(1+\rho_{min})$ |
| **CHANNEL MODEL** |||
| 17 | CIR (continuous) | $h(\tau,t) = \sum_n \alpha_n(t)e^{j\phi_n(t)}\delta(\tau-\tau_n)$ |
| 18 | CIR (discrete) | $y[m] = \sum_l h_l[m]x[m-l] + w[m]$ |

---

## Table of Contents

1. [Differentiate between flat fading and frequency selective fading](#differentiate-between-flat-fading-and-frequency-selective-fading-1)
2. [Explain how Doppler spread affects wireless communication performance parameters](#explain-how-doppler-spread-affects-wireless-communication-performance-parameters)
3. [Describe the different types of fading in a wireless system. How do they impact signal reception?](#describe-the-different-types-of-fading-in-a-wireless-system-how-do-they-impact-signal-reception)
   - [What is Fading?](#what-is-fading)
   - [Classification of Fading Types](#classification-of-fading-types)
   - [1. Large-Scale Fading](#1-large-scale-fading)
   - [2. Small-Scale Fading](#2-small-scale-fading)
     - [A. Based on Multipath Time Delay Spread (Frequency Domain Effects)](#a-based-on-multipath-time-delay-spread-frequency-domain-effects)
     - [B. Based on Doppler Spread (Time Domain Effects)](#b-based-on-doppler-spread-time-domain-effects)
     - [Impact Summary](#impact-summary)
     - [Classification Matrix](#classification-matrix)
4. [What is diversity and how does it reduce fading?](#what-is-diversity-and-how-does-it-reduce-fading) → [[Module 4/4.1 Diversity|Diversity]]
5. [Compare selection combining and maximal ratio combining techniques.](#compare-selection-combining-and-maximal-ratio-combining-techniques) → [[Module 4/4.1 Diversity|SC/MRC]]
6. [Discuss the impact of shadowing on wireless channel performance. (7 Marks)](#discuss-the-impact-of-shadowing-on-wireless-channel-performance-7-marks) → [[Module 2/Path Loss|Shadowing]]
7. [A wireless signal has a Doppler shift of 150 Hz when moving at 60 km/h. Determine the original frequency of the signal. (7 Marks)](#a-wireless-signal-has-a-doppler-shift-of-150-hz-when-moving-at-60-kmh-determine-the-original-frequency-of-the-signal-7-marks) → [[Module 2/Doppler Shift|Doppler Calc]]
8. [Define the Shannon capacity theorem in the context of wireless communication. How does it set the upper limit for data transmission in a given channel? (7 Marks)](#define-the-shannon-capacity-theorem-in-the-context-of-wireless-communication-how-does-it-set-the-upper-limit-for-data-transmission-in-a-given-channel-7-marks) → [[Module 2/Shannon Capacity| capacity]]
10. [How is the outage probability computed for a wireless channel?](#how-is-the-outage-probability-computed-for-a-wireless-channel) → [[Module 2/Outage Probability|Outage]]
11. [Capacity with custom path loss model](#capacity-with-custom-path-loss-model-7-marks)
12. [Derive the expression for the impulse response model of a multipath channel. (7 Marks)](#derive-the-expression-for-the-impulse-response-model-of-a-multipath-channel-07-marks)

---
### Additional Questions

- [Define outage probability]
- [Explain 2-ray model (7 Marks)](#explain-the-effect-of-multipath-propagation-using-2-ray-model-07-marks)
- [Narrowband fading: I/Q components (7 Marks)](#narrowband-fading-statistical-characterisation-of-in-phase-and-quadrature-components-of-a-received-signal-when-an-unmodulated-carrier-is-transmitted-07-marks)
- [Time-varying impulse response (7 Marks)](#derive-time-varying-impulse-response-of-multipath-wireless-channel-07-marks)
- [Q14: Free space path loss (7 Marks)](#q14-a-free-space-path-loss--received-power-in-dbm-07-marks)
- [AWGN capacity inference (4 Marks)](#what-is-inferred-by-the-channel-capacity-of-awgn-channel-04-marks)
- [Time selective fading (4 Marks)](#what-is-meant-by-time-selective-fading-4-marks)
- [Delay spread & coherence bandwidth (6 Marks)](#explain-delay-spread-and-coherence-bandwidth-6-marks)
- [Capacity with CSIR (6 Marks)](#capacity-of-flat-fading-awgn-channel-with-csir-6-marks)
9. [How does fading occur? Derive the expression for Doppler shift.](#how-does-fading-occur-derive-the-expression-for-doppler-shift)
   - [Multipath Propagation](#multipath-propagation-1)
   - [Derivation of the Doppler Shift Expression](#derivation-of-the-doppler-shift-expression)

---

## Differentiate between flat fading and frequency selective fading

**Answer:** [[May 2024.md#13. (a) Small scale fading: definition, types, flat vs frequency-selective (6 Marks)]]

### Quick Summary

| Aspect | Flat Fading | Frequency-Selective Fading |
|--------|-------------|----------------------------|
| **Condition** | $B_s \ll B_c$ | $B_s > B_c$ |
| **Delay Spread** | Small relative to symbol period | Significant; multiple resolvable paths |
| **Channel Model** | Single complex gain per symbol | FIR filter with multiple taps |
| **ISI** | Absent (negligible) | Present unless equalized/CP used |
| **Equalization** | One-tap (per subcarrier) | Multi-tap equalizer or OFDM needed |
| **Spectrum Distortion** | Uniform scaling | Frequency-dependent amplitude/phase |

### Key Points

- **Coherence Bandwidth ($B_c$):** $B_c \approx \frac{1}{5\tau_{rms}}$ to $\frac{1}{50\tau_{rms}}$
- If $B_s < B_c$ → Flat fading (all frequencies affected equally)
- If $B_s > B_c$ → Frequency-selective fading (different gains at different frequencies)

---

## Explain how Doppler spread affects wireless communication performance parameters

**Answer:** [[October 2023 PYQ.md#14. (c) Time selective fading]] | [[Module 2/Fading Theory]]

### Effect on Performance Parameters

Doppler spread $B_D$ (or maximum Doppler frequency $f_m$) directly impacts wireless communication in the following ways:

| Parameter | Effect of Doppler | Formula |
|-----------|-------------------|---------|
| **Coherence Time ($T_c$)** | Inverse relationship - higher Doppler → smaller $T_c$ | $T_c \approx \frac{0.423}{f_m} = \frac{0.423\lambda}{v}$ |
| **Channel Variability** | Faster fading with increased mobility | Rapid changes in amplitude/phase |
| **Symbol Error Rate** | Degrades performance if channel varies within symbol | Requires faster tracking |
| **Channel Estimation** | Needs more frequent estimation updates | Estimation overhead increases |
| **Equalization** | Time-varying channel causes residual ISI | Adaptive equalizers needed |
| **Interleaving Depth** | Requires longer interleaving for diversity | Trade-off with latency |
| **Modulation** | Lower-order modulations more robust | High Doppler limits adaptive modulation |

### Key Relationships

1. **Fast Fading Condition:** $T_s > T_c$
   - Symbol duration exceeds coherence time
   - Channel changes during symbol transmission
   - Causes inter-symbol interference and detection errors

2. **Slow Fading Condition:** $T_s < T_c$
   - Channel appears constant during symbol
   - Easier to equalize and demodulate

### Practical Examples

| Scenario | Velocity | $f_m$ @ 2 GHz | $T_c$ | Effect |
|----------|----------|---------------|-------|--------|
| Pedestrian | 3 km/h | 5.5 Hz | 77 ms | Slow fading |
| Vehicle | 60 km/h | 111 Hz | 3.8 ms | Moderate |
| High-speed train | 300 km/h | 556 Hz | 0.76 ms | Fast fading |

### Mitigation Techniques

- **Diversity:** Time diversity via interleaving and coding
- **Adaptive equalization:** Track time-varying channels
- **Pilot symbols:** Frequent channel estimation
- **Lower symbol rates:** Increase $T_s$ relative to $T_c$

---

## Describe the different types of fading in a wireless system. How do they impact signal reception?

**Answer:** [[May 2024.md#13. (a) Small scale fading: definition, types, flat vs frequency-selective (6 Marks)]]

### What is Fading?

See: [[Fading Theory]]

**Fading** is the time variation of received signal power caused by changes in the transmission medium or propagation paths. In wireless systems, fading is broadly categorized into:

1. **Large-Scale Fading**
2. **Small-Scale Fading**

### Multipath Propagation ( Causes of Fading)

See: [[Multipath Propagation]]

### Classification of Fading Types

```mermaid
graph TD
    FADING[Fading] --> LS[Large-Scale]
    FADING --> SS[Small-Scale]
    
    LS --> PL[Path Loss]
    LS --> SH[Shadowing]
    
    SS --> FREQ[Frequency Domain]
    SS --> TIME[Time Domain]
    
    FREQ --> FF[Flat Fading]
    FREQ --> FSF[Frequency-Selective]
    
    TIME --> SF[Slow Fading]
    TIME --> FASTF[Fast Fading]
    
    style LS fill:#4ecdc4,color:#fff
    style SS fill:#ff6b6b,color:#fff
```

---

### 1. Large-Scale Fading

Represents the variation of signal strength over **large distances** (typically on the order of a cell size) and is generally frequency-independent.

| Type | Cause | Impact |
|------|-------|--------|
| **Path Loss** | Signal spreads over larger area with distance | Continuous, predictable drop in average received power |

See: [[Path Loss]]

| **Shadowing Effect** | Obstructed by buildings, hills, mountains | Long-term fluctuations depending on position |

**Distribution:** Log-normal

**Impact:** Determines cell coverage and range planning. Requires link budget margin.

### Large-Scale Fading (Visual)

```mermaid
graph LR
    subgraph "Distance"
    A[Near TX] --> B[100m] --> C[500m] --> D[1km] --> E[2km]
    end
    
    A -->|"Strong"| A1[Signal]
    B -->|"Medium"| B1[Signal]
    C -->|"Weak"| C1[Signal]
    D -->|"Very Weak"| D1[Signal]
    E -->|"Barely"| E1[Signal]
    
    style A1 fill:#4ecdc4
    style B1 fill:#4ecdc4
    style C1 fill:#f9ca24
    style D1 fill:#f0932b
    style E1 fill:#eb4d4b
```

---

### 2. Small-Scale Fading

Involves rapid fluctuations in received signal strength over **very short distances** (on the order of carrier wavelength) and short time periods. Primarily driven by **multipath interference**.

### Small-Scale Fading (Multipath)

```mermaid
graph LR
    TX[TX] --> P1[Path 1<br/>Direct]
    TX --> P2[Path 2<br/>Bounce]
    TX --> P3[Path 3<br/>Ground]
    
    P1 -->|"τ₁"| ADD1[Σ]
    P2 -->|"τ₂"| ADD1
    P3 -->|"τ₃"| ADD1
    
    ADD1 --> R[RX]<-->|Interference| FADE[Fading]
    
    style FADE fill:#ff6b6b,color:#fff
```

#### A. Based on Multipath Time Delay Spread (Frequency Domain Effects)

| Type | Condition | Impact |
|------|----------|--------|
| **Flat Fading** | $B_s < B_c$ | All frequency components fluctuate simultaneously. Preserves spectral characteristics but causes SNR drop. |
| **Frequency-Selective Fading** | $B_s > B_c$ | Different spectral components affected by different amplitudes. Causes **ISI** (Inter-Symbol Interference). Much more difficult to decode. |

- **Flat Fading**: Channel has constant gain over signal bandwidth. Signal strength drops but shape preserved.
- **Frequency-Selective**: Multipath delay spread > symbol period. Multiple delayed versions cause time dispersion and ISI.

### Flat vs Frequency-Selective

```mermaid
graph TD
    subgraph "Signal Bandwidth vs Coherence Bandwidth"
    Bc[Bc = Coherence<br/>Bandwidth]
    Bs[Bs = Signal<br/>Bandwidth]
    end
    
    Bs -->|Bs < Bc| FLAT[Flat Fading]
    Bs -->|Bs > Bc| FSF[Frequency<br/>Selective]
    
    FLAT -->|"Effect"| EQ1[All freq.<br/>affected equally]
    FSF -->|"Effect"| EQ2[Different freq.<br/>different gains]
    
    style FLAT fill:#4ecdc4,color:#fff
    style FSF fill:#f0932b,color:#fff
```

#### B. Based on Doppler Spread (Time Domain Effects)

| Type | Condition | Impact |
|------|----------|--------|
| **Fast Fading** | $T_s > T_c$ | Channel impulse response changes rapidly within symbol. Creates ISI. Destructive interference from reflected signals. |
| **Slow Fading** | $T_s < T_c$ | Channel variations slower than modulation. Attenuation constant over symbol. Results in SNR loss overcome by error correction or diversity. |

- **Fast Fading**: High Doppler spread → rapid channel variations → linear distortion of baseband pulse
- **Slow Fading**: Low Doppler spread → channel nearly constant during symbol

### Slow vs Fast Fading

```mermaid
graph TD
    subgraph "Symbol Duration vs Coherence Time"
    Tc[Tc = Coherence<br/>Time]
    Ts[Ts = Symbol<br/>Duration]
    end
    
    Ts -->|Ts < Tc| SLOW[Slow Fading]
    Ts -->|Ts > Tc| FAST[Fast Fading]
    
    SLOW -->|"Effect"| E1[Channel<br/>constant]
    FAST -->|"Effect"| E2[Channel<br/>varies]
    
    style SLOW fill:#4ecdc4,color:#fff
    style FAST fill:#f0932b,color:#fff
```

---

### Impact Summary

| Fading Type | Effect | Solution |
|------------|--------|------------|
| Large-Scale | Coverage/range planning | Link budget margin |
| Flat Fading | SNR drop | Fade margin, diversity |
| Freq-Selective | ISI | OFDM, equalization |
| Fast Fading | ISI, phase errors | Diversity, tracking |
| Slow Fading | SNR loss | Error correction coding |

---

### Classification Matrix

| | Flat Fading | Frequency-Selective |
|---|-------------|---------------------|
| **Slow** | Slow + Flat | Slow + Freq-Selective |
| **Fast** | Fast + Flat | Fast + Freq-Selective |

**Best Case**: Slow + Flat | **Worst Case**: Fast + Frequency-Selective

---

## What is diversity and how does it reduce fading?

**Diversity** is a technique that transmits the same information over **multiple independent channels** (in time, frequency, or space) to combat fading.

### How It Reduces Fading

```mermaid
graph LR
    subgraph "Without Diversity"
    TX1[TX] -->|Path 1| R1[RX]
    R1 -->|Signal| OUT1[Output]
    end
    
    subgraph "With Diversity"
    TX2[TX] -->|Path 1| D1[Branch 1]
    TX2 -->|Path 2| D2[Branch 2]
    TX2 -->|Path 3| D3[Branch 3]
    D1 --> COMB[Combine]
    D2 --> COMB
    D3 --> COMB
    COMB --> OUT2[Output]
    end
    
    style OUT1 fill:#eb4d4b,color:#fff
    style OUT2 fill:#4ecdc4,color:#fff
```

- If one path is in fade, another may have good signal
- Statistical averaging reduces overall outage probability
- Provides **diversity gain** without increasing power

### Types of Diversity

```mermaid
graph TD
    DIV[Diversity] --> TD[Time Diversity]
    DIV --> FD[Frequency Diversity]
    DIV --> SD[Space Diversity]
    DIV --> PD[Polarization]
    
    TD -->|"Interleaving"| C1[Coding]
    FD -->|"Multiple"| C2[Carriers]
    SD -->|"MIMO"| C3[Antennas]
    PD -->|"Dual Pol"| C4[Polarizations]
    
    style TD fill:#4ecdc4,color:#fff
    style FD fill:#4ecdc4,color:#fff
    style SD fill:#4ecdc4,color:#fff
    style PD fill:#4ecdc4,color:#fff
```

| Type | Description |
|------|-------------|
| **Time Diversity** | Interleaving + coding across time slots |
| **Frequency Diversity** | Multiple carriers, spread spectrum |
| **Space Diversity** | Multiple antennas (MIMO) |
| **Polarization Diversity** | Different antenna polarizations |

---

## Compare selection combining and maximal ratio combining techniques.

### Selection Combining (SC)

```mermaid
graph TD
    A[Signal] --> B[Branch 1<br/>SNR=10dB]
    A --> C[Branch 2<br/>SNR=5dB]
    A --> D[Branch 3<br/>SNR=15dB]
    
    B --> E[Selector]
    C --> E
    D --> E
    
    E -->|"Select Best"| F[Output<br/>15dB]
    
    style E fill:#f0932b,color:#fff
```

- Selects the antenna branch with **highest instantaneous SNR**
- Uses only one branch for detection
- **Simple, low cost**, but **suboptimal** (discard other branch energy)

### Maximal Ratio Combining (MRC)

```mermaid
graph TD
    A[Signal] --> B[Branch 1<br/>g₁]
    A --> C[Branch 2<br/>g₂]
    A --> D[Branch 3<br/>g₃]
    
    B -->|"×g₁"| W1[Weight]
    C -->|"×g₂"| W2[Weight]
    D -->|"×g₃"| W3[Weight]
    
    W1 --> SUM[Sum]
    W2 --> SUM
    W3 --> SUM
    
    SUM --> F[Output<br/>Combined]
    
    style SUM fill:#4ecdc4,color:#fff
```

- Weights each branch by its channel gain
- **Combines all branches** constructively
- **Optimal performance** but **higher complexity**
- Provides maximum diversity gain

| Aspect | Selection Combining (SC) | Maximal Ratio Combining (MRC) |
|--------|---------------------------|-------------------------------|
| **Principle** | Pick the highest SNR | Weight and combine all |
| **Complexity** | Low (one RF chain) | High (all branches) |
| **Performance** | Moderate | Optimal |
| **SNR Output** | $\gamma = \max(\gamma_1, \gamma_2, ...)$ | $\gamma = \sum \gamma_i$ |
| **Gain** | Lower diversity gain | Highest diversity gain |

### Comparison Table

| Feature | SC | MRC |
|---------|-----|------|
| SNR Improvement | Moderate | Maximum |
| Complexity | Lowest | Highest |
| RF Chains | 1 (switched) | All active |
| Diversity Order | N (suboptimal) | N (optimal) |
| Use Case | Simple receivers | Advanced systems |

---

## Discuss the impact of shadowing on wireless channel performance. (7 Marks)

### Definition

**Shadowing** is the **deviation** of a received electromagnetic signal's power from its expected average value. It is a form of **large-scale fading** that occurs when large terrain features or obstacles—such as buildings, hills, mountains, or trees—block or obstruct the direct propagation path between the transmitter and the receiver.

Unlike path loss which varies **predictably** with distance (following a dⁿ law), shadowing is **random** and depends on the specific obstacles in the environment.

---

### Detailed Impact on Wireless Channel Performance

#### 1. Signal Strength Reduction
- Acts as a primary form of **large-scale fading**
- Causes significant reduction in overall signal strength when the direct path is blocked
- Additional attenuation beyond what path loss models predict
- Can cause 10-20+ dB of signal loss

#### 2. Power Fluctuations
- Received signal power experiences **large fluctuations** depending on:
  - Geographical position of the receiver
  - Radio frequency being used
  - Size and density of obstructing obstacles
- These fluctuations are experienced on **local-mean powers** (short-term averages used to separate shadowing from rapid multipath fading)

#### 3. Slow Fading
- Shadowing is the direct cause of **slow fading**
- Unlike multipath fading which happens rapidly (fractions of a second), shadow fading **lasts for multiple seconds or minutes**
- This is a much **slower time-scale phenomenon**

#### 4. Loss of Signal-to-Noise Ratio (SNR)
- The ultimate performance impact of slow fading induced by shadowing is a **loss of SNR**
- This **degrades the reliability** of the communication link
- Can lead to call drops, data errors, or connection loss

#### 5. Coverage Issues
- Creates **coverage holes** or dead zones in shadowed regions
- Cell edges become unpredictable
- Harder to plan cell boundaries

#### 6. Impact on System Design
- Must design **link budget margins** to combat shadowing (typically 10-20 dB)
- Affects handoff decisions - may trigger unnecessary handoffs
- Reduces effective cell capacity in shadowed areas

---

### Statistical Modeling

Because the mean envelope level of the signal becomes a **random variable** due to these shadow variations, channel performance models must account for it:

$$P_{dB} \sim \mathcal{N}(\mu, \sigma^2)$$

Where:
- $\mu$ = mean path loss (dB)
- $\sigma$ = standard deviation (typically 4-12 dB for urban environments)

**Distribution**: Log-normal (based on empirical observations)

### Visual Representation

```mermaid
graph LR
    TX[TX] --> A[Direct Path]
    TX -.->|Blocked| OB[Obstacle<br/>Building/Hill]
    OB -.->|Shadowed| RX[RX]
    
    A -->|"Good Signal"| S1[Signal]
    RX -->|"Weak Signal"| S2[Signal]
    
    style OB fill:#f0932b,color:#fff
    style S2 fill:#f0932b,color:#fff
```

### Mitigation Techniques

| Technique | How it Helps |
|-----------|-------------|
| **Link Budget Margin** | Extra power to overcome shadow fades |
| **Diversity** | Multiple antennas/paths average out effects |
| **Power Control** | Increase power in shadowed areas |
| **Microcells** | Smaller cells reduce blockage probability |

### Comparison: Path Loss vs Shadowing

See: [[Path Loss]]

| Property | Path Loss | Shadowing |
|----------|----------|-----------|
| **Scale** | Deterministic with distance | Random position-dependent |
| **Variations** | Predictable (d^n law) | Unpredictable (log-normal) |
| **Rate** | Slow, gradual | Rapid position changes |
| **Solution** | Cell planning | Margin + diversity |

### Key Takeaways

1. Shadowing causes **random fluctuations** around path loss mean
2. Creates **coverage holes** in shadowed regions
3. Requires **link budget margin** (typically 10-20 dB) for reliable coverage
4. Mitigated through **diversity** and **power control**
5. Combined with path loss → determines overall cell coverage

---

## A wireless signal has a Doppler shift of 150 Hz when moving at 60 km/h. Determine the original frequency of the signal. (7 Marks)

### Given

- Doppler shift: $f_d = 150$ Hz
- Velocity: $v = 60$ km/h

### Formula

Doppler shift:
  $$f_d = \frac{v}{\lambda} \cos\theta = f_m \cos\theta$$
For maximum Doppler (θ = 0°):
  $$f_d = f_m = \frac{v}{\lambda} = \frac{vf_c}{c}$$

$$\boxed{f_c = \frac{f_d \cdot c}{v}}$$

Where:
- $c = 3 \times 10^8$ m/s (speed of light)
- $v = 60$ km/h = $16.67$ m/s

### Calculation

$$f_c = \frac{150 \times 3 \times 10^8}{16.67}$$

$$f_c = \frac{150 \times 3\times 10^8}{16.67} = \frac{4.5 \times 10^{10}}{16.67}$$

$$f_c = 2.7 \times 10^9 \text{ Hz} = 2.7 \text{ GHz}$$

### Answer

The original carrier frequency is **2.7 GHz**.

---

## Compute received power using Friis equation (5 Marks)

***Assume a receiver is located 10km away from a 50W transmitter. Given f = 900 MHz, Gt = 1 and Gr = 2. Find the power at receiver and RMS voltage at receiver antenna matched with 50 Ω resistor***

### Given

- $P_t = 50$ W (transmit power)
- $d = 10$ km = 10,000 m (distance)
- $f = 900$ MHz (frequency)
- $G_t = 1$ (transmit antenna gain)
- $G_r = 2$ (receive antenna gain)
- $R = 50\ \Omega$ (load resistance)

### Step 1: Calculate Wavelength

$$\lambda = \frac{c}{f} = \frac{3 \times 10^8}{900 \times 10^6} = 0.333 \text{ m}$$

### Step 2: Friis Equation

$$P_r = P_t G_t G_r \left(\frac{\lambda}{4\pi d}\right)^2$$

Calculate factor:

$$\frac{\lambda}{4\pi d} = \frac{0.333}{4\pi \times 10000} = \frac{0.333}{125663.7} = 2.65 \times 10^{-6}$$

$$\left(\frac{\lambda}{4\pi d}\right)^2 = (2.65 \times 10^{-6})^2 = 7.02 \times 10^{-12}$$

### Step 3: Calculate Received Power

$$P_r = 50 \times 1 \times 2 \times 7.02 \times 10^{-12}$$

$$P_r = 100 \times 7.02 \times 10^{-12} = 7.02 \times 10^{-10} \text{ W}$$

$$\boxed{P_r = 0.702 \text{ nW}}$$

### Step 4: In dBm

$$P_r(dBm) = 10 \log_{10}\left(\frac{7.02 \times 10^{-10}}{1 \times 10^{-3}}\right)$$

$$P_r(dBm) = 10 \log_{10}(7.02 \times 10^{-7}) = 10(-6.154) = \boxed{-61.54 \text{ dBm}}$$

### Step 5: RMS Voltage

$$P = \frac{V_{rms}^2}{R}$$

$$V_{rms} = \sqrt{P_r \times R} = \sqrt{7.02 \times 10^{-10} \times 50}$$

$$V_{rms} = \sqrt{3.51 \times 10^{-8}}$$

$$\boxed{V_{rms} = 5.93 \times 10^{-4} \text{ V} = 0.593 \text{ mV}}$$

---

### Summary

| Parameter | Value |
|-----------|-------|
| Received Power | 0.702 nW |
| Received Power (dBm) | -61.54 dBm |
| RMS Voltage | 0.593 mV |

---

## Define the Shannon capacity theorem in the context of wireless communication. How does it set the upper limit for data transmission in a given channel? (7 Marks)

See: [[Module 2/Shannon Capacity|Shannon Capacity Note]]

**Answer:** [[October 2023 PYQ.md#14. (b) Inference of AWGN channel capacity]]

### Definition

**Shannon's capacity theorem** characterizes the **fundamental limits** of reliable communication over a noisy channel.

**Historical Context:** Before Shannon formulated information theory in 1948, it was widely believed that the only way to achieve reliable communication (making error probability as small as desired) was to drastically reduce data rate (e.g., repeating the same message over and over). **Shannon proved this incorrect** - through intelligent coding, a system can communicate at a strictly positive data rate while maintaining an arbitrarily small error probability.

### The Channel Capacity Limit

The theorem establishes a **maximal rate**, known as the **channel capacity (C)**, at which highly reliable communication can occur:

$$\boxed{C = B \log_2(1 + \text{SNR})}$$

**Key Principle:** If a system attempts to transmit data at a rate **exceeding** channel capacity, it becomes **fundamentally impossible** to drive error probability to zero. The channel capacity serves as the **absolute upper limit** for reliable data transmission.

### Relationship to Bandwidth and Power

For a standard **Additive White Gaussian Noise (AWGN)** wireless channel:

$$C = W \log_2\left(1 + \frac{\bar{P}}{N_0 W}\right)$$

Where:
- $W$ = Channel bandwidth (Hz)
- $\bar{P}$ = Average received power
- $N_0$ = Noise power spectral density

| Parameter | Physical Meaning |
|-----------|--------------|
| $W$ or $B$ | Available spectrum |
| $\bar{P}$ | Signal power |
| $N_0$ | Noise floor |
| $C$ | Maximum achievable data rate |

### Spectral Efficiency

The limit can be expressed as **maximum achievable spectral efficiency** based on SNR:

$$\eta = \log_2(1 + \text{SNR}) \text{ bits/s/Hz}$$

### Key Implications

1. **Bandwidth Tradeoff**
   - Doubling bandwidth roughly doubles capacity (linear relationship with B)
   - Each additional 3 dB SNR adds approximately $B$ bits/s at high SNR

2. **Power Tradeoff**
   - Capacity grows logarithmically with power (diminishing returns)
   - At high SNR: need 3 dB more power to increase capacity by $B$ bits/s
   - At low SNR: $C \approx \frac{B}{\ln 2}\text{SNR}$ (nearly linear!)

3. **Fundamental Limit**
   - $C$ is the absolute theoretical limit
   - No practical system can exceed this without errors
   - Guides modulation/coding design

### Visual Representation

```mermaid
graph LR
    subgraph "Shannon Capacity"
    B[Bandwidth<br/>W] -->|"Input"| CAP[Capacity Formula]
    SNR[SNR] --> CAP
    CAP -->|"Output"| C[Max Data Rate<br/>C bits/s]
    end
    
    style CAP fill:#4ecdc4,color:#fff
```

### Practical Example

For a channel with $B = 1$ MHz and $\text{SNR} = 100$ (20 dB):

$$C = 1 \times 10^6 \times \log_2(1 + 100)$$
$$C = 1 \times 10^6 \times \log_2(101)$$
$$C = 1 \times 10^6 \times 6.658$$
$$C \approx 6.66 \text{ Mbps}$$

### Limitations

Shannon capacity assumes:
- Perfect channel coding (optimal codes)
- AWGN (only white Gaussian noise)
- Perfect knowledge of channel at transmitter/receiver

In practice, real systems operate **below** this limit due to:
- Practical coding limitations
- Implementation complexity
- Other interference

### Key Takeaways

1. **Fundamental limit** - no system can exceed without errors
2. **Bandwidth-limited**: Capacity grows linearly with B
3. **Power-limited**: Capacity grows logarithmically with SNR
4. **Guides design**: Determines tradeoff between B, power, and rate
5. **Practical goal**: Get as close as possible to Shannon limit
6. **Coding enables** reliable communication at rates approaching limit

---

---

## How does fading occur? Derive the expression for Doppler shift.

**Fading** is the random variation in a signal's amplitude, phase, or angle of arrival as it travels through a wireless communication channel.

It occurs primarily due to two physical phenomena:

### 1. Multipath Propagation

See: [[Multipath Propagation]]

### 2. Relative Motion and Environmental Changes

When the transmitter, receiver, or surrounding objects are in motion, the relative phases of the arriving multipath components change constantly. This continuous shifting causes the received signal's amplitude to fluctuate rapidly over short distances or time periods — **small-scale fading**. Large terrain features can physically block radio waves, causing slower fluctuations known as **shadowing** or **large-scale fading**.

```mermaid
graph LR
    TX[TX] -->|"Signal"| A
    A -->|"r(t) = r0 + vt"| RX[RX<br/>Moving]
    RX -->|"Phase shifts"| P[Signal<br/>Amplitude<br/>Fluctuates]
    
    P -->|"Rapid"| F[Fading]
    P -->|"Slow"| S[Shadowing]
    
    style TX fill:#4ecdc4,color:#fff
    style RX fill:#f0932b,color:#fff
    style F fill:#eb4d4b,color:#fff
    style S fill:#f9ca24,color:#fff
```

```mermaid
graph TD
    A1["x(t) = cos(2πft)"] -->|"r(t) = r0 + vt"| A2["y(t) ~ cos(2πf(t - r/c))"]
    A2 -->|"Expand"| A3["y(t) ~ cos(2πf(1 - v/c)t)"]
    A3 -->|"Frequency shift"| A4["fd = -f(v/c)"]
    A4 -->|"Using c = fλ"| A5["fd = v/λ"]
    A5 -->|"Angle θ"| A6["fd = fmax cosθ"]
    
    style A1 fill:#4ecdc4,color:#fff
    style A4 fill:#f0932b,color:#fff
    style A6 fill:#4ecdc4,color:#fff
```

---

### Derivation of the Doppler Shift Expression

See: [[Doppler Shift]]

The Doppler shift arises because the relative motion between the transmitter and receiver changes the apparent frequency of the signal over time.

**Step 1:** Assume a fixed transmit antenna sends a sinusoidal signal with frequency $f$:
$$x(t) = \cos(2\pi ft)$$

**Step 2:** A receive antenna moves away from the transmitter at velocity $v$. The distance is $r(t) = r_0 + vt$.

**Step 3:** The signal experiences time-varying propagation delay $r(t)/c$:
$$y(t) \propto \cos\left(2\pi f\left(t - \frac{r_0 + vt}{c}\right)\right)$$

> [!callout] **Step 3→4 Expansion Explained**
> $$= \cos\left(2\pi f t - \frac{2\pi f r_0}{c} - \frac{2\pi f v t}{c}\right)$$
> $$= \cos\left(2\pi f \left(1 - \frac{v}{c}\right)t - \frac{2\pi f r_0}{c}\right)$$
>
> | Term | Meaning |
> |-----|---------|
> | $2\pi f t$ | Original signal component |
> | $2\pi f r_0/c$ | Fixed phase offset (initial distance) |
> | $2\pi f (v/c)t$ | **New term** from relative motion |
> | $(1 - v/c)$ | Frequency scaling factor |

**Step 4:** Expand:
$$y(t) \propto \cos\left(2\pi f\left(1 - \frac{v}{c}\right)t - \frac{2\pi fr_0}{c}\right)$$

The new apparent frequency is $f\left(1 - \frac{v}{c}\right)$.

**Step 5:** The Doppler shift is:
$$f_d = -f\frac{v}{c}$$

> [!callout] **What is f? Where did -ve sign go?**
> **f** = original transmit frequency (carrier f_c)
>
> **-ve sign** indicates direction:
> - **Negative** = moving **away** (frequency decreases)
> - **Positive** = moving **toward** (frequency increases)
>
> **f_m = v/λ** is the **magnitude** (always positive) — we drop the sign to get max value.

Using $c = f\lambda$:
$$\boxed{f_m = \frac{v}{\lambda}}$$

**Step 6:** For a signal path at angle $\theta$ relative to direction of motion:
$$\boxed{f_d = \frac{v}{\lambda}\cos\theta = f_m\cos\theta}$$

Where:
- $v$ = velocity (m/s)
- $\lambda$ = **wavelength** (m)
- $f_c$ = carrier frequency
- $c$ = speed of light (3×10⁸ m/s)
- $f_m$ = maximum Doppler shift

> [!callout] **What is λ (Lambda)?**
> **Wavelength** = distance traveled by wave in one cycle.
> $$\lambda = \frac{c}{f_c}$$
>
> Where **f_c** = **carrier frequency** of the transmitted signal (WiFi, 4G, 5G, etc.)
>
> | Application | f_c (carrier) | λ |
> |-------------|--------------|-----|
> | WiFi | 2.4 GHz | 12.5 cm |
> | 4G LTE | 1.8 GHz | 16.7 cm |
> | 5G | 3.5 GHz | 8.6 cm |
> | FM Radio | 100 MHz | 3 m |
>
> **Key:** Higher carrier frequency → shorter λ → larger Doppler shift for same velocity.

---

### Related Questions

- [[May 2024.md#3. Multipath causing small-scale fading (3 Marks)]]
- [[October 2023 PYQ.md#3. How does fading occur? Derive the expression for doppler shift.]]
- [[Module 2/Statistical Multipath Channel Models]]

---

## How is the outage probability computed for a wireless channel?

See: [[Module 2/Outage Probability|Outage Probability Note]]

**Outage** = Event when channel quality drops below threshold ($\rho_{min}$), making reliable communication impossible.

$$P_{outage} = P(SNR < \rho_{min})$$

### For Rayleigh Fading

$$P_{outage} = 1 - \exp\left(-\frac{\rho_{min}}{\bar{\rho}}\right)$$

### For Rician Fading

$$P_{outage} = 1 - Q_1\left(\frac{A}{\sigma}, \sqrt{\frac{2\rho_{min}}{1+K}}\right)$$

### Capacity with Outage

$$C_{outage} = (1 - P_{outage}) W \log_2(1 + \rho_{min})$$

Rate reliably supported in $(1-P_{outage})$% of time.

### Example

Given: ${\bar{\rho}} = 10$, $\rho_{min} = 1$ (Rayleigh)

$$P_{outage} = 1 - \exp(-1/10) = 1 - 0.905 = \boxed{9.5\%}$$

---

## Capacity with Custom Path Loss Model (7 Marks)

### Given

- Path loss: $P(d) = P_t (d_0/d)^3$ where $d_0 = 50$ m
- Bandwidth: $B = 50$ kHz = 50,000 Hz
- Noise PSD: $N_0/2$, where $N_0 = 10^{-9}$ W/Hz
- Transmit power: $P_t = 2$ W
- Distances: $d_1 = 200$ m, $d_2 = 1$ km = 1000 m

### Step 1: Calculate Noise Power

$$N = N_0 \times B = 10^{-9} \times 50000 = 5 \times 10^{-5} \text{ W}$$

### Step 2: Calculate Received Power at d = 200 m

$$P(d) = P_t \left(\frac{d_0}{d}\right)^3 = 2 \times \left(\frac{50}{200}\right)^3 = 2 \times (0.25)^3 = 2 \times 0.015625$$

$$P_r = \boxed{0.03125 \text{ W}}$$

### Step 3: Calculate SNR at 200 m

$$SNR = \frac{P_r}{N} = \frac{0.03125}{5 \times 10^{-5}} = 625$$

### Step 4: Calculate Capacity at 200 m

$$C = B \log_2(1 + SNR) = 50000 \times \log_2(626)$$

$$\log_2(626) = \frac{\ln(626)}{\ln(2)} = \frac{6.438}{0.693} = 9.29$$

$$C = 50000 \times 9.29 = \boxed{464,500 \text{ bits/s}}$$

### Step 5: Calculate Received Power at d = 1000 m

$$P(d) = 2 \times \left(\frac{50}{1000}\right)^3 = 2 \times (0.05)^3 = 2 \times 0.000125$$

$$P_r = \boxed{0.00025 \text{ W}} = 0.25 \text{ mW}$$

### Step 6: Calculate SNR at 1000 m

$$SNR = \frac{0.00025}{5 \times 10^{-5}} = 5$$

### Step 7: Calculate Capacity at 1000 m

$$C = 50000 \times \log_2(6)$$

$$\log_2(6) = \frac{\ln(6)}{\ln(2)} = \frac{1.792}{0.693} = 2.59$$

$$C = 50000 \times 2.59 = \boxed{129,500 \text{ bits/s}}$$

---

### Summary

| Distance | Received Power | SNR | Capacity |
|----------|---------------|-----|----------|
| 200 m | 31.25 mW | 625 | 464.5 kbps |
| 1000 m | 0.25 mW | 5 | 129.5 kbps |

### Conclusion

- Capacity decreases **significantly** with distance: ~72% drop from 200m to 1km
- The cubic path loss ($d^3$) causes faster attenuation than free space ($d^2$)
- At 1km, channel can still support ~130 kbps reliably
- Adaptive techniques needed to maintain QoS over distance

---

## Derive the expression for the impulse response model of a multipath channel. (7 Marks)

### Concept

A multipath channel can be modeled as a **linear time-varying filter**. The impulse response $h(t, \tau)$ describes how the channel spreads an impulse in time.

### Derivation

**Step 1: Received Signal from Multiple Paths**

The transmitted signal $x(t)$ arrives via $N$ paths, each with:
- Delay $\tau_n$ (time of arrival)
- Amplitude $\alpha_n$ (attenuation)
- Phase $\phi_n$ (phase shift)

$$y(t) = \sum_{n=0}^{N-1} \alpha_n e^{j\phi_n} x(t - \tau_n)$$

**Step 2: Convolution Form**

This is equivalent to convolution with channel impulse response:

$$y(t) = x(t) * h(t)$$

Where $h(t)$ is the time-varying channel impulse response.

**Step 3: Continuous-Time Impulse Response**

$$h(\tau, t) = \sum_{n=0}^{N-1} \alpha_n(t) e^{j\phi_n(t)} \delta(\tau - \tau_n(t))$$

Where:
- $\alpha_n(t)$ = time-varying amplitude of n-th path
- $\phi_n(t)$ = time-varying phase of n-th path
- $\tau_n(t)$ = time-varying delay of n-th path
- $\delta()$ = Dirac delta function

**Step 4: Discrete-Time Model**

For practical digital systems, sample at bandwidth $W$:

$$y[m] = \sum_l h_l[m] \cdot x[m-l] + w[m]$$

Where:
- $h_l[m]$ = $l$-th tap of discrete-time channel
- $x[m]$ = transmitted symbol
- $y[m]$ = received symbol
- $w[m]$ = noise sample

### Physical Interpretation

```mermaid
graph LR
    TX[TX] -->|"Path 0<br/>τ₀, α₀"| P0[ ]
    TX -->|"Path 1<br/>τ₁, α₁"| P1[ ]
    TX -->|"Path N-1<br/>τₙ₋₁, αₙ₋₁"| PN[ ]
    
    P0 -.->|"Add"| SUM[Σ]
    P1 -.->|"Add"| SUM
    PN -.->|"Add"| SUM
    
    SUM --> RX[RX]
    
    style TX fill:#4ecdc4,color:#fff
    style SUM fill:#ff6b6b,color:#fff
    style RX fill:#4ecdc4,color:#fff
```

### Summary

| Model | Formula | Description |
|------|---------|-------------|
| Continuous | $h(\tau, t) = \sum_n \alpha_n(t) e^{j\phi_n(t)} \delta(\tau - \tau_n(t))$ | Time-varying multipath |
| Discrete | $y[m] = \sum_l h_l[m] x[m-l] + w[m]$ | Tapped-delay-line |
| Frequency | $Y(f) = H(f, t) X(f)$ | Convolution in freq domain |

**Key:** Multipath causes time dispersion → channel acts as filter with multiple taps.

---

## Q14 a) Free Space Path Loss & Received Power (7 Marks)

### Given

- Transmit power: $P_t = 1$ W
- Carrier frequency: $f_c = 2.4$ GHz
- Distance: $d = 1.6$ km = 1600 m

### Step 1: Calculate Wavelength

$$\lambda = \frac{c}{f_c} = \frac{3 \times 10^8}{2.4 \times 10^9} = 0.125 \text{ m}$$

### Step 2: Free Space Path Loss (dB)

$$PL_{dB} = 20\log_{10}\left(\frac{4\pi d}{\lambda}\right) = 20\log_{10}\left(\frac{4\pi \times 1600}{0.125}\right)$$

$$\frac{4\pi \times 1600}{0.125} = 4\pi \times 12800 = 160850$$

$$PL_{dB} = 20\log_{10}(160850) = 20 \times 5.206 = \boxed{104.12 \text{ dB}}$$

### Step 3: Received Power (dBm)

$$P_r(dBm) = P_t(dBm) - PL_{dB}$$

$$P_t(dBm) = 10\log_{10}(1/0.001) = 30 \text{ dBm}$$

$$P_r = 30 - 104.12 = \boxed{-74.12 \text{ dBm}}$$

---

## What is inferred by the channel capacity of AWGN channel? (4 Marks)

**Answer:** [[October 2023 PYQ.md#14. (b) Inference of AWGN channel capacity]]

The AWGN channel capacity $C = B \log_2(1 + SNR)$ infers:

1. **Maximum reliable data rate** — above this rate, errors become unavoidable
2. **Bandwidth-SNR tradeoff** — can increase capacity by increasing either
3. **Fundamental limit** — no practical system can exceed without errors
4. **Spectral efficiency** — $\eta = \log_2(1+SNR)$ bits/s/Hz

In simple terms: It tells us the **maximum bits per second** we can transmit **reliably** given our bandwidth and signal strength.

---

## What is meant by time selective fading? (4 Marks)

**Time selective fading** = When channel changes **within** a symbol duration.

- Occurs when: $T_s > T_c$ (symbol period > coherence time)
- Caused by: Doppler spread (relative motion)
- Effect: Channel gain varies during transmission → causes ISI
- Also called: **Fast fading**

See: [[Module 2/Fading#classification-matrix|Fading Types]]

---

## Explain delay spread and coherence bandwidth. (6 Marks)

### Delay Spread

**Delay spread** ($\tau_{rms}$) = Measure of time dispersion caused by multipath.

- RMS delay spread: $$\sigma_\tau = \sqrt{\bar{\tau^2} - \bar{\tau}^2}$$
- Mean excess delay: $$\bar{\tau} = \frac{\sum P(\tau_i)\tau_i}{\sum P(\tau_i)}$$

### Coherence Bandwidth

**Coherence bandwidth** ($B_c$) = Frequency range where channel is "flat" (correlated).

- $$B_c \approx \frac{1}{5\sigma_\tau}$$ (varies: 1/5 to 1/50)

| Relationship | Meaning |
|--------------|---------|
| $B_s < B_c$ | Flat fading — all frequencies affected equally |
| $B_s > B_c$ | Frequency-selective — different gains at different frequencies |

See: [[Module 2/Coherence|Delay Spread & Coherence BW]]

---

## Capacity of flat fading AWGN channel with CSIR (6 Marks)

### Given

Channel State Information at Receiver (CSIR) only — transmitter doesn't know channel.

### Expression

$$C_{CSIR} = E_{|h|^2}[\log_2(1 + SNR \cdot |h|^2)]$$

### Derivation (from AWGN)

1. **AWGN capacity:** $C = B \log_2(1 + \rho)$ where $\rho$ = SNR

2. **For fading channel:** SNR becomes random: $\rho_{fading} = SNR \cdot |h|^2$

3. **With CSIR only:** Average over fading distribution:
$$C_{CSIR} = \int_0^\infty \log_2(1 + SNR \cdot \rho) f_{\rho}(\rho) d\rho$$

4. **For Rayleigh fading:**
$$C_{CSIR} = \frac{1}{\bar{\rho}} e^{1/\bar{\rho}} E_1\left(\frac{1}{\bar{\rho}}\right) \cdot B$$
where $E_1$ = exponential integral

### Physical Meaning

- Receiver knows channel gain $h$, transmitter doesn't
- Cannot adapt power/rate (waterfilling not possible)
- Capacity is the **average** across all channel states
- Lower than perfect CSI (transmitter knows channel)

---

## Define outage probability

**Outage probability** = Probability that the channel quality falls below a threshold, making reliable communication impossible.

$$P_{outage} = P(SNR < \rho_{min})$$

Where $\rho_{min}$ is the minimum SNR required for reliable communication.

See: [[Module 2/Outage Probability]] for detailed formulas (Rayleigh, Rician).

---

## Explain the effect of multipath propagation using 2-ray model. (7 Marks)

### 2-Ray Model

The 2-ray model considers **two paths**:
1. Direct LOS path
2. Ground-reflected path

### Received Power

$$P_r = P_t G_t G_r \frac{h_t^2 h_r^2}{d^4}$$

Where:
- $h_t, h_r$ = antenna heights
- $d$ = distance

### Path Loss Exponent

| Region | Formula | Exponent |
|--------|---------|----------|
| Free space (d < d_bp) | $P_r \propto 1/d^2$ | 2 |
| Two-ray (d > d_bp) | $P_r \propto 1/d^4$ | 4 |

### Breakpoint Distance

$$d_{bp} = \frac{4h_t h_r}{\lambda}$$

### Effect Summary

- **Near distance (d < d_bp):** Constructive/destructive interference → ripples
- **Far distance (d > d_bp):** Fast power falloff (d⁴) — worse than free space
- The ground reflection causes additional phase cancellation

See: [[Module 2/Path Loss#two-ray-model|Two-Ray Model]]

---

## Narrowband fading: Statistical characterisation of in-phase and quadrature components (7 Marks)

### Narrowband Signal Model

For narrowband fading, the received signal envelope follows **Rayleigh distribution**.

If transmitted is an unmodulated carrier $A\cos(2\pi f_c t)$:

### Received Signal

$$r(t) = I(t)\cos(2\pi f_c t) - Q(t)\sin(2\pi f_c t)$$

Where:
- $I(t)$ = **In-phase component**
- $Q(t)$ = **Quadrature component**

### Statistical Properties (Rayleigh)

Assuming NLOS (no dominant LOS):

1. **$I$ and $Q$ are independent Gaussian random variables**

2. **Mean:** $E[I] = E[Q] = 0$

3. **Variance:** $\sigma^2 = \frac{E[|r|^2]}{2}$

$$f_I(i) = \frac{1}{\sqrt{2\pi\sigma^2}} e^{-i^2/2\sigma^2}$$

$$f_Q(q) = \frac{1}{\sqrt{2\pi\sigma^2}} e^{-q^2/2\sigma^2}$$

### Envelope Distribution

The envelope $R = \sqrt{I^2 + Q^2}$ follows **Rayleigh distribution**:

$$f_R(r) = \frac{r}{\sigma^2} e^{-r^2/2\sigma^2}, \quad r \geq 0$$

### With LOS (Rician)

If dominant LOS exists: envelope follows **Rician distribution** with parameter $K$ (ratio of LOS to scatter power).

See: [[Module 2/Fading#statistical-models|Rayleigh/Rician]]

---

## Derive time-varying impulse response of multipath wireless channel. (7 Marks)

### Time-Varying Multipath Channel

The channel impulse response $h(\tau, t)$ varies with time due to relative motion.

### Derivation

**Step 1: Baseband representation**

$$h(\tau, t) = \sum_{n=0}^{N-1} \alpha_n(t) e^{j\phi_n(t)} \delta(\tau - \tau_n(t))$$

Where:
- $\alpha_n(t)$ = time-varying amplitude of n-th path
- $\phi_n(t)$ = time-varying phase of n-th path
- $\tau_n(t)$ = time-varying delay of n-th path

**Step 2: With Doppler**

For path $n$ with Doppler shift $f_n$:

$$\phi_n(t) = 2\pi f_n t + \phi_0$$

$$\alpha_n(t) = \alpha_n e^{-j(2\pi f_n t)}$$

**Step 3: Expanded form**

$$h(\tau, t) = \sum_n \alpha_n e^{j(\omega_n t + \phi_{n0})} \delta(\tau - \tau_n(t))$$

**Step 4: Discrete-time model**

For digital systems sampled at $T_s$:

$$h[m] = \sum_n \alpha_n[m] e^{j\phi_n[m]} \delta[l-n]$$

### Key Parameters

- **Coherence time** $T_c$: Time channel appears constant
- **Doppler spread** $B_D$: Spread in Doppler frequencies
- Relationship: $T_c \approx \frac{0.423}{f_m}$

See: [[Module 2/Statistical Multipath Channel Models#time-varying|Time-Varying Channel]]
