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

**Fading** is the time variation of received signal power caused by changes in the transmission medium or propagation paths. In wireless systems, fading is broadly categorized into:

1. **Large-Scale Fading**
2. **Small-Scale Fading**

### Multipath Propagation ( Causes of Fading)

```mermaid
graph LR
    TX[TX] -->|Path 1 Direct| RX
    TX -->|Path 2 Building| RX
    TX -->|Path 3 Ground| RX
    TX -->|Path 4 Trees| RX
    
    RX -->|Signal Sum| FADE[Fading]
    
    style FADE fill:#ff6b6b,color:#fff
```

Multiple signal paths arrive at receiver with different delays and phases → constructive/destructive interference → fading.

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

**Shadowing** is the **deviation** of a received electromagnetic signal's power from its expected average value. It is a **large-scale fading** effect caused by large obstacles (buildings, hills, trees) blocking the signal path between transmitter and receiver.

Unlike path loss which is deterministic with distance, shadowing is **random** due to varying obstacle positions.

### Impact on Wireless Channel Performance

| Aspect | Impact |
|--------|--------|
| **Signal Strength Reduction** | Primary form of large-scale fading, significant reduction when blocked by terrain/obstacles |
| **Power Fluctuations** | Large fluctuations depending on position and frequency |
| **Slow Variations** | Lasts seconds/minutes - slower time-scale than multipath |
| **Loss of SNR** | Degrades reliability of communication link |
| **Coverage** | Creates coverage holes in shadowed regions |
| **Handoff** | Can trigger unnecessary handoffs |

### Statistical Modeling

Because the mean envelope level becomes random, channel models must account for it:

$$P_{dB} \sim \mathcal{N}(\mu, \sigma^2)$$

Distribution: **Log-normal** (empirically observed)

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

| Property | Path Loss | Shadowing |
|----------|----------|-----------|
| **Scale** | Deterministic with distance | Random position-dependent |
| **Variations** | Predictable (dⁿ law) | Unpredictable (log-normal) |
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

### Related Questions

- [[May 2024.md#3. Multipath causing small-scale fading (3 Marks)]]
- [[October 2023 PYQ.md#3. How does fading occur? Derive the expression for doppler shift.]]
- [[Module 2/Statistical Multipath Channel Models]]