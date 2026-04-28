---
banner: "https://images.unsplash.com/photo-1583602621722-cbd1130b210b?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
banner_y: 0.116
tags:
  - ect402
  - propagation
  - radio-waves
  - module-5
  - magnetic-field
course: ECT402
module: "5"
topic: Effects of Earth's Magnetic Field
type: lecture-notes
semester: S8
date: 2026-04-17
alias:
  - Earth's Magnetic Field Effects
  - Ionosphere Magnetic Field
---

# Effects of Earth's Magnetic Field

?hide title of the dataview ? like the filename 

```dataview
TABLE WITHOUT ID
Depends, Effect, Result , file.inlinks as "Used In"
FROM #magnetic-field 
```




The Earth's magnetic field significantly impacts radio wave propagation, primarily by influencing how atmospheric electrons interact with sky waves in the ionosphere.

## Key Effects

### 1. Deflection of Electrons
- [Depends:: **Magnetic force on electrons**]
  The magnetic field exerts a deflecting force on moving electrons in the atmosphere. This force is directed at right angles to both the electron's instantaneous velocity and the perpendicular component of the Earth's magnetic field.

### 2. Change in Polarisation
- [Depends:: **Elliptical path of electrons**]
  When high-frequency radio waves interact with the magnetic field, the vibrating electrons are forced into elliptical paths. Because of this, some of the energy absorbed by the electrons is reradiated with a polarisation that is rotated 90° in space relative to the incident wave, accompanied by a time phase difference.
- [Result:: **Elliptical polarisation**]
  Consequently, an originally plane-polarised radio wave becomes elliptically polarised after traveling through the ionosphere.

### 3. Splitting of the Radio Wave
- [Depends:: **Twisting effect on electron paths**]
  The twisting effect on the electrons' paths reacts back on the incident radio waves, causing the signal to split into two distinct components.
- [Result:: **Two separate waves**]
  These two waves bend by different amounts in the ionosphere, travel along different paths, experience different energy absorption rates and velocities, and rotate in opposite directions.

### 4. Frequency-Dependent Behavior
- [Depends:: **Electron velocity inversely proportional to frequency**]
  The impact on the electrons' paths is frequency-dependent because the average velocity of an electron is inversely proportional to the wave's frequency.
- [Effect:: **Path shape varies with frequency**]
  - At very high frequencies: Elliptical paths are narrow
  - At lower frequencies: Amplitude of vibration increases; minor axis of ellipse becomes proportionately wider

### 5. Gyro Frequency and Maximum Attenuation
- [Depends:: **Gyro frequency**]
  The Earth's magnetic field establishes a gyro frequency, which is the frequency whose period equals the time it takes an electron to revolve in a circular orbit under the influence of the Earth's magnetic flux.
- [Effect:: **Maximum attenuation near gyro frequency**]
  Signal attenuation reaches its maximum near this gyro frequency, meaning these frequencies are generally avoided in propagation work.
- [Behavior:: **Path shape above/below gyro frequency**]
  - For frequencies above the gyro frequency: Electrons follow an elliptical path
  - For frequencies below the gyro frequency: Electrons follow a spiral or loop path
- [Effect:: **Critical frequency shift**]
  The critical frequency of the split "extraordinary" wave component is increased by an amount equal to half the gyro frequency.

### 6. Ground Wave Bending
- [Depends:: **Local ground wave propagation**]
  In local ground wave propagation, the Earth's magnetic field also plays a role by causing the wave to bend and reflect into the receiver, contributing to the overall received signal.

## Summary

- [Advantages:: **Enables long-distance sky wave communication**]
  The magnetic field splitting creates two propagation paths for redundancy.
- [Limitations:: **Signal fading due to multipath**]
  Different path lengths cause signal variations.
- [Limitations:: **Polarization changes**]
  Requires circularly polarized antennas for some applications.
- [Limitations:: **Frequency-dependent effects**]
  Behavior varies significantly with frequency; some frequencies experience high attenuation.

---

**Related Concepts:**
- [[Ionospheric propagation|Ionospheric Propagation]]
- Critical Frequency
- Maximum Usable Frequency
- Virtual Height
- Ordinary and Extraordinary Waves
