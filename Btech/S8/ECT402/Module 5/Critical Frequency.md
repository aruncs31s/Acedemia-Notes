---
banner: "https://images.unsplash.com/photo-1583602621722-cbd1130b210b?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
banner_y: 0.116
tags:
  - ect402
  - propagation
  - radio-waves
  - module-5
  - s8
  - critical-frequency
  - files
  - templates
  - templater
course: ECT402
module: "5"
topic: Critical Frequency
type: lecture-notes
semester: S8
date: 2026-04-17
alias:
  - Critical Frequency
  - Critical Freq
id: callout
aliases: []
dg-publish: true
title: callout
---

# Critical Frequency

## Definition

**Critical frequency** is the **maximum frequency** that can be reflected back to Earth when a radio wave is transmitted **vertically upward** into the ionosphere.

> [!info]+ Explanation
> When a signal pulse is sent directly upwards, it reflects back and is picked up by a receiver located at the exact same site as the transmitter
> . However, as the frequency of the transmitted signal is continuously increased, it eventually reaches a point where the wave will no longer reflect back to Earth; instead, it will pass right through the ionospheric layer into the next one or out into outer space
> . The frequency at which this penetration occurs is the critical frequency




## Key Concept

- If the wave frequency is **below the critical frequency**, it will be reflected back to Earth
- If the wave frequency is **above the critical frequency**, it will penetrate through the ionosphere into space

## Mathematical Expression

The critical frequency ($f_c$) is related to the electron density ($N$) of the **ionospheric**[^1] [^2] layer:

$$f_c = 9 \sqrt{N_{max}}$$

Where:
- $f_c$ = critical frequency in Hz
- $N_{max}$ = maximum electron density per m³

## Important Points

- [Depends:: **Electron density of ionospheric layer**]
  Higher electron density = higher critical frequency
- [Depends:: **Time of day**]
  Critical frequency varies with day/night cycles (higher during day)
- [Depends:: **Season**]
  Varies with seasons due to changes in solar radiation

## Relationship with Maximum Usable Frequency (MUF)

- [Relation:: **MUF > Critical frequency**]
  The Maximum Usable Frequency (MUF) is always higher than the critical frequency for a given path
- [Relation:: **MUF = Critical frequency × sec(θ)**]
  Where θ is the angle of incidence

## Practical Significance

- [Applications:: **HF Communication**]
  Must use frequencies below critical frequency for reliable sky wave communication
- [Applications:: **Radio Broadcasting**]
  Determines which frequencies can be used for long-distance communication
- [Limitations:: **Limited usable bandwidth**]
  Frequencies above critical can't be used for ionospheric reflection

## Typical Values

| Layer | Day | Night |
|-------|-----|-------|
| E Layer | 2-4 MHz | 0.5-1 MHz |
| F2 Layer | 5-12 MHz | 2-5 MHz |

---

**Related Concepts:**
- [[Ionospheric propagation|Ionospheric Propagation]]
- Maximum Usable Frequency (MUF)
- Virtual Height
- Electron Density





[^1]: “Ionized” = atoms lose electrons → become charged particles (ions + free electrons
