---
tags:
  - wireless_communication
  - important_topics
  - ect402
---

# Important Topics for ECT402 - Wireless Communication

> 📌 Key topics for exams - Quick reference guide

---

## 1. Generations of Wireless Communication Systems

The evolution, features, and performance comparisons of 1G (analog), 2G, 3G, 4G, and 5G technologies.

**Related:** [[1G]], [[2G]], [[3G]], [[4G]], [[5G]], [[6G]]

---

## 2. Wireless LANs (WLAN) and PANs

- The architecture and components of WLANs
- Differences between Infrastructure and Ad-hoc network topologies
- Bluetooth network structures (Piconets and Scatternets)

**Related:** [[WLAN]], [[Bluetooth, PAN, WiMax]]

---

## 3. Cellular Concept and System Design

### 3.1 Frequency Reuse
- Cellular architecture basics
- Frequency reuse distance (D)
- Reuse ratio Q = D/R = √3N

> [!TIP]
> Smaller cluster size N → Higher capacity but more interference

**Related:** [[Cellular System Design Fundamentals#Frequency Reuse]]

### 3.2 Channel Assignment Strategies
| Strategy | Description | Advantages | Disadvantages |
|----------|-------------|------------|---------------|
| **FCA** | Fixed channels per cell | Simple | Wastes resources |
| **DCA** | Dynamic pooling | Efficient | Complex MSC |
| **Hybrid** | Mix of FCA/DCA | Balanced | Moderate complexity |

**Related:** [[Cellular System Design Fundamentals#Channel Assignment Strategies]]

### 3.3 Handoff Strategies
- **Hard Handoff**: Break-before-make
- **Soft Handoff**: Make-before-break
- Handoff threshold (Δ)
- Dwell time considerations

**Related:** [[Cellular System Design Fundamentals#Handoff Strategies]]

---

## 4. Improving Coverage and Capacity

Techniques used when cells become congested:

### Cell Splitting
- Divide cell into smaller cells (microcells)
- Reduce transmit power by 12 dB when radius halved
- Requires new base stations

### Cell Sectoring
- Replace omnidirectional with directional antennas (120° or 60°)
- Reduces co-channel interference
- Increases SIR

### Microcell Zone Concept
- Multiple zone antennas connected to single BS
- No handoffs between zones
- Automatic zone switching

**Related:** [[Cellular System Design Fundamentals#Improving Coverage and Capacity]]

---

## 5. Interference and System Capacity

### 5.1 Types of Interference

| Type | Cause | Solution |
|------|-------|----------|
| **Co-channel** | Same frequency in different cells | Spatial separation (D) |
| **Adjacent Channel** | Frequency leakage | Filtering, power control |
| **Near-Far Problem** | Strong nearby signal blocks weak signal | Strict power control |

### 5.2 Trunking and Grade of Service (GoS)
- **Trunking**: Pool-based channel allocation
- **Erlangs**: Unit of traffic intensity
- **GoS**: Probability of call blocked/delayed during busiest hour
- Example: 2% GoS = 2 calls blocked per 100 attempts

**Related:** [[Interference and System Capacity]]

---

## 6. Propagation Effects

### 6.1 Path Loss & Shadowing (Large-Scale Fading)

$$L_{fs}(dB) = 20\log_{10}(d) + 20\log_{10}(f) - 147.55$$

- Path loss exponent (n): 2 (free space) to 3-5 (obstructed)
- Shadowing: Log-normal distribution (σ = 4-12 dB)

**Related:** [[Path Loss, Shadowing & Doppler Shift]]

### 6.2 Multipath & Doppler (Small-Scale Fading)

| Parameter | Symbol | Description |
|-----------|--------|-------------|
| Delay spread | τ_rms | Time dispersion |
| Coherence bandwidth | B_c | ~1/(5τ_rms) |
| Doppler spread | B_d | 2f_dmax |
| Coherence time | T_c | ~0.423/f_dmax |

### Fading Types
- **Rayleigh**: No direct line-of-sight (NLOS)
- **Rician**: Direct LoS component present

**Related:** [[Multipath Effect & Doppler Shift]]

---

## 7. Diversity Techniques

Combat fading through multiple signal paths:

| Type | Method |
|------|--------|
| **Spatial** | Multiple antennas (MIMO) |
| **Frequency** | FHSS, OFDM subcarriers |
| **Time** | Interleaving, retransmission |
| **Polarization** | Different antenna polarizations |

### Combining Techniques
- Selection Combining
- Maximal Ratio Combining (MRC)
- Equal Gain Combining

**Related:** [[Significance of Diversity in Wireless Communication]]

---

## 8. Multi-Carrier Systems

### 8.1 Need for Multi-Carrier
- Combat frequency-selective fading
- Reduce ISI in wideband channels
- Efficient spectrum utilization

### 8.2 OFDM Basics
- Orthogonal FDM
- N parallel subcarriers
- Cyclic prefix to eliminate ISI

**Related:** [[Need for Multi Carrier Systems]], [[MultiCarrier Modulation]]

---

## 9. Wireless Spectrum & Standards

- Spectrum allocation by regulatory bodies (FCC, TRAI)
- ISM bands (2.4 GHz, 5.8 GHz)
- IEEE 802.11 (Wi-Fi), 802.15 (Bluetooth), 802.16 (WiMAX)

**Related:** [[Wireless Spectrum Allocation]]

---

## 📝 Quick Formula Reference

| Formula | Description |
|---------|-------------|
| $Q = D/R = \sqrt{3N}$ | Frequency reuse ratio |
| $L_{fs} = 20\log d + 20\log f - 147.55$ | Free space path loss |
| $f_d = \frac{v f_c}{c}$ | Maximum Doppler shift |
| $B_c \approx \frac{1}{5\tau_{rms}}$ | Coherence bandwidth |
| $T_c \approx \frac{0.423}{f_{d_{max}}}$ | Coherence time |

---

> 📚 **Complete your study with:** [[Module 1]] for organized topic navigation