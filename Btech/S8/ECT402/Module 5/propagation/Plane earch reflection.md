---
banner: "https://images.unsplash.com/photo-1583602621722-cbd1130b210b?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
banner_y: 0.116
tags:
  - ect402
  - propagation
  - radio-waves
  - module-5
  - s8
  - plane-earth-reflection
course: ECT402
module: "5"
topic: Plane Earth Reflection
type: lecture-notes
semester: S8
date: 2026-04-17
alias:
  - Plane Earth Reflection
  - Earth Reflection
f_start: "30000000"
---

### Plane earth reflection

![[Module 5-1.png|3555]]

It occurs when a transmitting and a receiving antenna are both positioned above a flat, plane surface, such as a road.

The key characteristics of this reflection model include:

- **Two Paths of Propagation:** The radio signal reaches the receiving antenna through both a direct ***line-of-sight*** path and a path ***reflected off the ground***.
- **Path Length Convergence:** As the horizontal distance (r) between the antennas becomes very large relative to their vertical heights, the difference in distance between the direct path and the reflected path shrinks, going to zero at a rate of r−1.
- **Signal Cancellation:** At sufficiently large distances, this path length difference becomes very small relative to the signal's wavelength. Because the reflection causes the sign of the electric field to reverse, the direct wave and the reflected wave begin to cancel each other out.
- **Rapid Power Decay:** Due to this destructive interference, the electric wave at the receiver is attenuated proportionally to r−2. As a result, **the overall received power decreases as** r−4. This explains why signal power can decay much faster over distance than the standard r−2 rate expected in unobstructed free space

## Frequency Range
- [Frequency_Range:: **VHF and above (30 MHz - 3 GHz)**]  
  Plane earth reflection is significant at VHF, UHF, and microwave frequencies where wavelength is small enough for ground reflections to cause interference effects, and where antennas are typically mounted above ground level.

## Applications
- [Applications:: **Line-of-sight radio communication**]  
  Affects signal strength in VHF/UHF links over flat terrain (e.g., microwave relay links).
- [Applications:: **Radar systems**]  
  Ground bounce (surface reflection) creates multipath effects that must be considered in radar design and target detection.
- [Applications:: **Broadcasting over flat terrain**]  
  FM and TV signals experience interference patterns due to ground reflection when transmitted over plains or water bodies.
- [Applications:: **Wireless communication systems**]  
  Influences path loss models in cellular and Wi-Fi networks deployed in suburban or rural areas with minimal terrain variation.
- [Applications:: **Navigation and landing systems**]  
  Instrument Landing System (ILS) and other aviation navigation aids must account for ground reflection effects near runways.

## Advantages
- [Advantages:: **Simple mathematical model**]  
  Plane earth reflection provides a straightforward model for analyzing interference patterns in wireless links.
- [Advantages:: **Predictable interference patterns**]  
  The behavior can be calculated using ground reflection theory, aiding in system design.
- [Advantages:: **Useful for antenna height optimization**]  
  Understanding ground reflections helps determine optimal antenna heights for coverage.

## Depends On
- [Depends:: **Antenna height**]
  Both transmitting and receiving antenna heights affect the reflection path and interference.
- [Depends:: **Ground conductivity and permittivity**]
  Different surfaces (soil, water, concrete) have varying reflection coefficients.
- [Depends:: **Distance between antennas**]
  Path length difference determines interference pattern at receiver.
- [Depends:: **Signal frequency/wavelength**]
  Determines the phase relationship between direct and reflected signals.

## Limitations
- [Limitations:: **Signal fading due to interference**]  
  Constructive and destructive interference between direct and reflected signals causes rapid fading with small changes in antenna position or frequency.
- [Limitations:: **Dependent on antenna height and ground characteristics**]  
  Effectiveness varies significantly with antenna elevation and ground conductivity/permittivity (e.g., soil vs. water vs. urban surfaces).
- [Limitations:: **Requires smooth reflecting surface**]  
  Rough or irregular terrain disrupts the coherent reflection needed for the plane earth model to apply.
- [Limitations:: **Polarization sensitivity**]  
  Reflection coefficients differ for vertical and horizontal polarization, with vertical polarization generally preferred for reduced ground loss.
- [Limitations:: **Brewster angle effects**]  
  At specific angles (Brewster angle), reflection for parallel polarization approaches zero, creating polarization-dependent nulls in the reception pattern.

---
