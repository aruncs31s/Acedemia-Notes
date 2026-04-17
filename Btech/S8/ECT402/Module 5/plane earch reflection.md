---
tags:
  - wireless_communication
  - propagation
  - earth
status: true
---

### Plane earth reflection

![[Module 5-1.png|3555]]

It occurs when a transmitting and a receiving antenna are both positioned above a flat, plane surface, such as a road.

The key characteristics of this reflection model include:

- **Two Paths of Propagation:** The radio signal reaches the receiving antenna through both a direct ***line-of-sight*** path and a path ***reflected off the ground***.
- **Path Length Convergence:** As the horizontal distance (r) between the antennas becomes very large relative to their vertical heights, the difference in distance between the direct path and the reflected path shrinks, going to zero at a rate of r−1.
- **Signal Cancellation:** At sufficiently large distances, this path length difference becomes very small relative to the signal's wavelength. Because the reflection causes the sign of the electric field to reverse, the direct wave and the reflected wave begin to cancel each other out.
- **Rapid Power Decay:** Due to this destructive interference, the electric wave at the receiver is attenuated proportionally to r−2. As a result, **the overall received power decreases as** r−4. This explains why signal power can decay much faster over distance than the standard r−2 rate expected in unobstructed free space