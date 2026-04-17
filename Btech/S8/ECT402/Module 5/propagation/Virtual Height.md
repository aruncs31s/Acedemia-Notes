---
tags:
  - ect402
  - propagation
  - radio-waves
  - module-5
  - s8
  - virtual-height
course: ECT402
module: "5"
topic: Virtual Height
type: lecture-notes
semester: S8
date: 2026-04-17
alias: [Virtual Height, Virtual Height of Ionosphere]
---

# Virtual Height

## Definition

**Virtual height** is the apparent height a radio wave reaches in the ionosphere, defined as **the height that would be reached by a short pulse of energy if it traveled at the speed of light and experienced the exact same time delay as the actual reflected pulse**.

## Key Points

- [Effect:: **Always greater than true height**]
  The virtual height is **always greater than the true height of reflection**.
- [Depends:: **Electron interaction**]
  This discrepancy occurs because the wave's velocity of propagation is slowed down by the interchange of energy between the wave and the electrons in the ionosphere.
- [Effect:: **Variability**]
  While the difference between virtual and true height is usually small, it depends on the electron distributions in the regions below the reflection level and can occasionally be as large as **100 km**.
- [Advantages:: **Highly useful**]
  Virtual height is easily measured and is highly useful for calculating transmission path distances.

## How It's Measured

- [Method:: **Ionogram**]
  An ionosonde sends vertically directed radio pulses and records the time taken for the signal to return
- [Result:: **Apparent reflection point**]
  The time delay converts to a "height" - this is the virtual height
- [Physical height:: **Actual layer location**]
  The physical ionospheric layer (e.g., F2 layer at ~250-400 km)

## Mathematical Relationship

For a wave reflecting at virtual height $h_v$:

$$h_v = \int_0^{h_m} \frac{c \cdot dh}{v_p(h)}$$

Where:
- $c$ = speed of light
- $v_p(h)$ = phase velocity at height $h$
- $h_m$ = maximum height reached by the wave

## Types of Height

| Type | Description |
|------|-------------|
| **Physical Height** | Actual location of maximum electron density |
| **Virtual Height** | Apparent reflection height from ionogram (always higher) |
| **True Height** | Computed from virtual height using inversion |

### Example:
- F2 physical height: ~300 km
- Virtual height: ~350-400 km
- The difference is due to the wave slowing down as it penetrates the layer

## Typical Virtual Heights

| Layer | Day Virtual Height | Night Virtual Height |
|-------|-------------------|---------------------|
| E | 100-120 km | 90-100 km |
| F1 | 160-200 km | N/A (merged with F2) |
| F2 | 200-400 km | 150-300 km |

## Importance

- [Depends:: **Critical frequency calculation**]
  Virtual height is used to determine the true electron density profile
- [Depends:: **MUF calculation**]
  Path length calculations require virtual height data
- [Depends:: **Ionospheric modeling**]
  Essential for predicting radio wave behavior
- [Applications:: **Transmission path distances**]
  Highly useful for calculating how far signals will travel

## Factors Affecting Virtual Height

- [Depends:: **Electron density gradient**]
  Steeper gradients cause more bending
- [Depends:: **Wave frequency**]
  Higher frequencies penetrate deeper before reflecting
- [Depends:: **Time of day**]
  Height varies with ionospheric changes
- [Depends:: **Solar activity**]
  Higher during periods of increased solar radiation
- [Depends:: **Electron distribution below reflection level**]
  Can cause differences up to 100 km

---

## Quick Summary

- **Virtual height** = "apparent" reflection height
- Always **greater than true height** due to slowed wave velocity
- Measured via **ionosonde/ionogram**
- Difference can be as large as **100 km**
- Used for **MUF calculations** and **path distance** determination

---

**Related Concepts:**
- [[Ionospheric propagation|Ionospheric Propagation]]
- [[Critical Frequency|Critical Frequency]]
- [[Maximum Usable Frequency|Maximum Usable Frequency]]
- [[Ionosphere Layers|Ionosphere Layers]]
- Skip Distance