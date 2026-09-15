---
banner: "https://images.unsplash.com/photo-1583602621722-cbd1130b210b?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
banner_y: 0.116
tags:
  - ect402
  - propagation
  - radio-waves
  - module-5
  - s8
  - ground-wave
  - files
  - templates
  - templater
course: ECT402
module: "5"
topic: Ground Wave Propagation
type: lecture-notes
semester: S8
date: 2026-04-17
alias:
  - Ground Wave Propagation
  - Surface Wave Propagation
f_start: "15000"
id: callout
aliases: []
dg-publish: true
title: callout
---

### What is ground wave propagation

**Ground wave propagation**, also known as surface wave propagation, is a transmission method where **radio waves travel along the Earth’s surface to a receiving antenna by following the curvature of the Earth**. 
- In this mode, the radio waves interact with the semi-conductive surface of the Earth, allowing the ***signal to cling to the surface and follow its contours***(curvature).
> [!note]- Note
> 
> It actually bends slightly, allowing it to follow the curvature of the Earth over long distances (beyond the visible horizon). However, as the wave travels, it loses energy due to absorption by the ground, which limits its effective range.
> 


#### **Key characteristics of ground wave propagation include:**

- **Frequency Range:** This mode is highly dependent on the frequency of the signal. It is **most effective for Very Low Frequency (VLF), Low Frequency (LF), and Medium Frequency (MF) bands**, which typically span from [Frequency_Range::**15 kHz to 2 MHz**].
- **Vertical Polarization:** Ground waves are transmitted using vertical polarization. This orientation is specifically used to prevent the electric field of the wave from short-circuiting into the Earth's conductive surface.
- **Rapid Attenuation:** Because the Earth is not a perfect electrical conductor, it absorbs energy from the waves as they travel, causing the signal to become weaker over distance. **This attenuation increases proportionally with the frequency of the wave**, which is why ground wave propagation is ineffective for high-frequency transmissions and is restricted to low-bandwidth signals.
- **Antenna Requirements:** To radiate these low-frequency signals efficiently, the transmitting antennas must be quite large (at least equal to one-quarter of the signal's wavelength), meaning that tall, ground-based vertical towers are generally required.

**Advantages and Limitations:** The primary advantage of ground wave propagation is that [Advantages::**it is relatively unaffected by changing atmospheric conditions**]], [Advantages::providing reliable], [Advantages::continuous coverage for specific regions]. However, due to the severe attenuation caused by the Earth's surface, [Limitations::its maximum transmission range is limited to short or regional distances], usually on the order of a few hundred kilometers.


#### **Common Applications:**

- [Applications::**AM Radio Broadcasting**]: Ground waves are widely used to provide local and regional coverage for standard Amplitude Modulation (AM) radio broadcasts (typically between [Frequency_Range::540 kHz and 1650 kHz].
- [Applications::**Submarine Communication**]: Because VLF ground waves can penetrate seawater to significant depths, the military utilizes this propagation mode for one-way communication with submerged submarines.
- [Applications::**Navigation**]: VLF and LF ground waves are utilized for long-range radio navigation, radio beacons, and locators.

## Depends On
- [Depends:: **Ground conductivity**]
  The Earth's surface conductivity affects signal attenuation and propagation distance.
- [Depends:: **Frequency**]
  Lower frequencies (VLF, LF, MF) propagate more efficiently over ground waves.
- [Depends:: **Vertical polarization**]
  Required to prevent electric field short-circuiting into the ground.

---
