---
tags:
  - ect402
  - propagation
  - radio-waves
  - module-5
  - s8
  - ionosphere
  - layers
course: ECT402
module: "5"
topic: Ionosphere Layers
type: lecture-notes
semester: S8
date: 2026-04-17
alias: [Ionosphere Layers, Ionosphere Regions, D Layer, E Layer, F Layer]
---

# Ionosphere Layers

The **ionosphere** is a region of charged particles (ions and free electrons) in the Earth's upper atmosphere, approximately **60-1000 km** above the Earth's surface. It is divided into several layers based on electron density.

- reflect HF radio waves (3–30 MHz)
- 

## Overview of Layers

| Layer | Height | Day | Night | Reflects |
|-------|--------|-----|-------|----------|
| D | 60-90 km | Yes | No | No (absorbs) |
| E | 90-150 km | Yes | Weak | Medium freq (MF) |
| F1 | 150-200 km | Yes | No | High freq (HF) |
| F2 | 200-500+ km | Yes | Yes | HF (best) |

---

## D Layer (60-90 km)

### Characteristics
- [Depends:: **Solar radiation**]
  Only exists during **daylight hours**
- [Characteristic:: **Low electron density**]
  Weakest layer
- [Characteristic:: **Absorbs radio waves**]
  Does not reflect; absorbs signals

### Effect on Radio Waves
- [Effect:: **Absorbs low frequencies**]
  AM radio (540-1600 kHz) significantly absorbed during day
- [Effect:: **Disappears at night**]
  Allows AM signals to propagate farther at night

### Frequency Range
- [Frequency_Range:: **Below 2 MHz**]
  Primarily affects MF and lower frequencies

---

## E Layer (90-150 km)

### Characteristics
- [Depends:: **Solar radiation**]
  Also known as **Kennelly-Heaviside layer**
- [Characteristic:: **Moderate electron density**]
  Stronger than D layer
- [Characteristic:: **Exists day and night**]
  But much weaker at night

### Effect on Radio Waves
- [Effect:: **Reflects medium frequencies**]
  Reliable for MF (AM radio range) during day
- [Effect:: **Sporadic E layer**]
  Can cause unexpected long-distance communication at VHF frequencies

### Frequency Range
- [Frequency_Range:: **100 kHz - 10 MHz**]
  Reflects MF and lower HF bands

---

## F Layer (150-500+ km)

### Characteristics
- [Depends:: **Solar radiation**]
  Most important layer for long-distance communication
- [Characteristic:: **Highest electron density**]
  Contains the most free electrons
- [Characteristic:: **Splits into F1 and F2 during day**]
  F1 disappears at night; F2 remains

### F1 Sub-layer (150-200 km)
- Exists only during **daytime**
- [Characteristic:: **Lower density than F2**]
- [Effect:: **Helps reflect HF waves during day**]

### F2 Sub-layer (200-500+ km)
- Exists **day and night**
- [Characteristic:: **Highest electron density**]
- [Characteristic:: **Most important for long-distance HF communication**]
- [Characteristic:: **Variable - affected by season and solar activity**]

### Frequency Range
- [Frequency_Range:: **3-30 MHz (HF Band)**]
  Primary layer for international broadcasting and long-distance communication

---

## Summary Table

| Layer | Height (km) | Critical Freq (Day) | Critical Freq (Night) | Main Use |
|-------|-------------|---------------------|----------------------|-----------|
| D | 60-90 | - | N/A | Absorption |
| E | 90-150 | 2-4 MHz | 0.5-1 MHz | Medium-distance |
| F1 | 150-200 | 4-6 MHz | N/A | Daytime HF |
| F2 | 200-500+ | 5-12 MHz | 2-5 MHz | Long-distance |

---

## Key Relationships

- [Relation:: **Higher layer = Higher critical frequency**]
  F2 has highest critical frequency
- [Relation:: **Daytime = Higher electron density**]
  More solar radiation = more ionization
- [Relation:: **Higher frequency = Requires higher critical frequency**]
  To reflect high freq, need dense electron layer

---

**Related Concepts:**
- [[Ionospheric propagation|Ionospheric Propagation]]
- [[Critical Frequency|Critical Frequency]]
- Maximum Usable Frequency (MUF)
- Virtual Height
- Electron Density