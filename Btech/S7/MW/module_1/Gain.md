---
tags:
  - ECT401
module: 1
---
# Gain
The gain of an antenna is the ***ratio of the power radiated in a particular direction to the power radiated by an isotropic antenna*** (which radiates equally in all directions). It accounts for both directivity and efficiency losses.

**Formula:** $G = \frac{4\pi U(\theta, \phi)}{P_{rad}}$, where $U$ is radiation intensity, $P_{rad}$ is total radiated power.

**Detailed Explanation:**
- **Isotropic Antenna:** A hypothetical antenna that radiates power equally in all directions. It has a gain of 1 (0 dB) and directivity of 1.
- **Radiation Intensity $U(\theta, \phi)$:** Power per unit solid angle in a specific direction. Measured in watts per steradian.
- **Total Radiated Power $P_{rad}$:** Total power radiated by the antenna, excluding losses.
- **Units:** Dimensionless, often expressed in dB (decibels): $G_{dB} = 10 \log_{10} G$.
- **Example:** A dipole antenna has a gain of about 2.15 (3.3 dB) in its maximum direction.
- **Measurement:** Using anechoic chambers or field measurements with reference antennas.
- **Importance:** Higher gain means better signal strength in desired directions, crucial for long-range communication.
