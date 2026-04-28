---
banner: "https://images.unsplash.com/photo-1583602621722-cbd1130b210b?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
banner_y: 0.116
tags:
  - ect402
  - propagation
  - radio-waves
  - module-5
  - s8
  - spherical-earth
course: ECT402
module: "5"
topic: Spherical Earth Propagation
type: lecture-notes
semester: S8
date: 2026-04-17
alias:
  - Spherical Earth Propagation
  - Earth Curvature Effect
---

# Spherical Earth Propagation

Spherical earth propagation refers to the effect of Earth's curvature on radio wave propagation, particularly for space waves (line-of-sight propagation). Due to the Earth's curvature, the direct line-of-sight distance between transmitting and receiving antennas is limited to the horizon. This phenomenon is also known as the **radio horizon**.

## Frequency Range
- [Frequency_Range:: **> 30 MHz (VHF, UHF, Microwave)**]  
  Space wave propagation (and thus spherical earth effects) dominates at frequencies above 30 MHz, where ionospheric reflection is negligible and ground wave attenuation is high.

## Applications
- [Applications:: **FM Radio Broadcasting**] (88–108 MHz)  
  Limited by line-of-sight; coverage extends to the radio horizon.
- [Applications:: **Television Broadcasting**] (VHF/UHF bands)  
  Requires tall antennas to extend coverage beyond the horizon.
- [Applications:: **Radar Systems**]  
  Line-of-sight range determines maximum detection distance.
- [Applications:: **Microwave Links**] (Point-to-point communication)  
  Antenna height is critical to overcome Earth's curvature.
- [Applications:: **Satellite Communication**]  
  While satellites are above the atmosphere, Earth curvature affects ground station visibility.

## Advantages
- [Advantages:: **Predictable radio horizon**]  
  The line-of-sight distance can be accurately calculated based on antenna heights.
- [Advantages:: **Design guidance for antenna placement**]  
  Helps determine optimal antenna heights for maximum coverage.
- [Advantages:: **Atmospheric refraction extends range**]  
  Natural bending of waves extends the effective communication range beyond geometric LOS.

## Depends On
- [Depends:: **Antenna height**]
  Higher antennas increase line-of-sight distance.
- [Depends:: **Earth's radius**]
  Curvature determines the radio horizon distance.
- [Depends:: **Atmospheric refractive index**]
  Affects signal bending and effective propagation range.
- [Depends:: **Terrain and obstacles**]
  Hills and buildings can block the line-of-sight path.

## Limitations
- [Limitations:: **Limited by line-of-sight distance**]  
  Maximum range is approximately \( d \approx 3.57 (\sqrt{h_t} + \sqrt{h_r}) \) km, where \( h_t \) and \( h_r \) are antenna heights in meters.
- [Limitations:: **Requires elevated antennas for long range**]  
  To increase coverage, antennas must be mounted on towers or high terrain.
- [Limitations:: **Affected by terrain and obstacles**]  
  Hills, buildings, and other obstructions can block the line-of-sight path.
- [Limitations:: **Atmospheric refraction extends effective range**]  
  Standard atmospheric conditions cause slight bending, extending the radio horizon by about 4/3 Earth radius model.

### Related Concepts
- **Radio Horizon**: The distance at which the Earth's curvature blocks direct line-of-sight.
- **Tropospheric Refraction**: Bending of waves in the atmosphere that can slightly increase propagation distance beyond geometric line-of-sight.
- **Diffraction**: Allows signals to propagate over obstacles to a limited extent, but spherical earth effects dominate for smooth Earth.

---
