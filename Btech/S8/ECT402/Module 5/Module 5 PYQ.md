---
tags:
  - ect402
  - propagation
  - radio-waves
  - module-5
  - s8
  - pyq
  - exam-questions
course: ECT402
module: "5"
topic: Module 5 PYQ
type: exam-questions
semester: S8
date: 2026-04-17
---

# Module 5 - Previous Year Questions

> 📚 Related: [[Ionospheric propagation|Ionospheric Propagation]] | [[Space wave and surface wave|Space Wave]] | [[Ground wave propagation|Ground Wave]] | [[Critical Frequency|Critical Frequency]] | [[Maximum Usable Frequency|MUF]]

---

## Part A

### Q9) Differentiate between ionospheric and space wave propagation.

| Aspect | Space Wave Propagation | Ionospheric (Sky Wave) Propagation |
|--------|----------------------|-----------------------------------|
| **Atmosphere Layer** | Troposphere (~16 km) | Ionosphere (50-400 km) |
| **Frequency Band** | > 30 MHz (VHF, UHF) | 2-30 MHz (HF) |
| **Range** | Limited to optical horizon (~100 km) | Global (thousands of km) |
| **Mechanism** | Direct LOS + ground reflection | Refraction from ionospheric layers |
| **Applications** | FM, TV, Radar | Long-distance radio communication |

---

### Q10) Explain the propagation methods of radio waves around the Earth's surface.

**Ground Wave (Surface Wave) Propagation:**

- **Frequency:** 15 kHz - 2 MHz (VLF, LF, MF)
- **Mechanism:** Waves interact with Earth's semi-conductive surface and follow its curvature
- **Polarization:** Vertically polarized to prevent short-circuiting
- **Limitation:** Continuous energy loss to Earth's surface → regional range only
- **Applications:** AM radio broadcasting

---

## Part B

### Q19 a) Differentiate between tropospheric waves and ionospheric waves?

| Aspect | Tropospheric Waves (Space Waves) | Ionospheric Waves (Sky Waves) |
|--------|----------------------------------|------------------------------|
| **Layer** | Troposphere (lowest atmosphere) | Ionosphere (50-400 km) |
| **Frequency** | > 30 MHz (VHF, UHF, SHF) | 2-30 MHz (HF) |
| **Mechanism** | LOS + ground reflection + refraction | Refraction from electron layers |
| **Range** | Limited by Earth's curvature | Thousands of kilometers |
| **Dependence** | Antenna height, atmospheric conditions | Time of day, season, solar activity |
| **Applications** | Radar, Microwave links, TV | Global radio communication |

---

### Q19 b) Calculate ground distance for ionospheric reflection

> **Given:**
> - Angle of elevation with ground (β) = 60°
> - Round trip time (t) = 2 ms = 2×10⁻³ s
> - Speed of EM waves (c) = 3×10⁸ m/s

**Solution:**

**Step 1: Total distance traveled**
$$d_{wave} = c \times t = (3 \times 10^8) \times (2 \times 10^{-3}) = 6 \times 10^5 \text{ m} = 600 \text{ km}$$

**Step 2: Ground distance (flat earth approximation)**
$$D_{skip} = d_{wave} \times \cos(60°) = 600 \times 0.5 = \boxed{300 \text{ km}}$$

---

### Q20 a) What are the different modes by which radio waves propagate around the earth?

| Mode | Frequency Range | Description |
|------|----------------|-------------|
| **1. Ground Wave** | 15 kHz - 2 MHz | Travels along Earth's surface, follows curvature |
| **2. Sky Wave** | 2 - 30 MHz | Refracted by ionosphere, enables global communication |
| **3. Space Wave** | > 30 MHz | Line-of-sight within troposphere |
| **4. Troposcatter** | > 300 MHz | Forward scattering in troposphere for beyond-LOS |

---

### Q20 b) Calculate MUF from critical frequency

> **Given:**
> - Critical frequency ($f_{cr}$) = 6 MHz
> - Angle of incidence (φᵢ) = 30°

**Solution:**
$$MUF = f_{cr} \times \sec(\phi_i)$$
$$MUF = 6 \times \sec(30°) = 6 \times \frac{1}{\cos(30°)}$$
$$MUF = 6 \times \frac{1}{0.866} = 6 \times 1.155 = \boxed{6.93 \text{ MHz}}$$

---

## From Question Paper 2 (0400ECT402052301)

---

### Part A

### Q9) Deduce expression for critical frequency

**Refractive index of ionosphere:**
$$n = 1 - \frac{81N'}{f^2}$$

**For vertical incidence (φᵢ = 0°):**
- Wave reflects when n = sin(0°) = 0
- Setting n = 0:

$$0 = 1 - \frac{81N_{max}}{f_{cr}^2}$$

$$\frac{81N_{max}}{f_{cr}^2} = 1$$

$$\boxed{f_{cr} = 9\sqrt{N_{max}}}$$

---

### Q10) Explain mechanism of wave bending in ionosphere

> 📖 See also: [[Ionosphere Layers|Ionosphere Layers]]

**Process:**
1. Radio wave enters ionosphere with varying electron density (N)
2. Refractive index decreases as electron density increases: $n = 1 - \frac{81N}{f^2}$
3. Wave bends away from normal (toward horizontal) as n decreases
4. Bending continues until angle reaches 90° (horizontal)
5. Wave then reflects and bends back down to Earth

---

### Part B

### Q19 a) Calculate LOS distance and radio horizon

> **Given:**
> - Transmitter height ($h_t$) = 200 m
> - Receiver height ($h_r$) = 20 m

**Formula (accounting for atmospheric refraction, $R_{eff} = \frac{4}{3}R$):**
$$d = 4.12(\sqrt{h_t} + \sqrt{h_r}) \text{ km}$$

**Solution:**

**Radio horizon of transmitter:**
$$d_t = 4.12 \times \sqrt{200} = 4.12 \times 14.142 = \boxed{58.26 \text{ km}}$$

**Radio horizon of receiver:**
$$d_r = 4.12 \times \sqrt{20} = 4.12 \times 4.472 = \boxed{18.42 \text{ km}}$$

**Maximum spacing (total LOS distance):**
$$d_{total} = d_t + d_r = 58.26 + 18.42 = \boxed{76.68 \text{ km}}$$

---

### Q19 b) Derive expressions for critical frequency, MUF, and skip distance

**1. Critical Frequency ($f_{cr}$):**

For vertical incidence, wave returns when n = sin(0) = 0:
$$\boxed{f_{cr} = 9\sqrt{N_{max}}}$$

**2. Maximum Usable Frequency (MUF):**

For oblique incidence (angle φᵢ):
- Reflection condition: n = sin(φᵢ)
- Substituting: $1 - \frac{f_{cr}^2}{MUF^2} = \sin\phi_i$
- Using $\cos^2\phi_i = 1 - \sin^2\phi_i$:

$$\boxed{MUF = f_{cr} \times \sec(\phi_i)}$$

**3. Skip Distance ($D_{skip}$):**

Using geometry: $\tan\phi_i = \frac{2h}{D_{skip}}$

$$\boxed{D_{skip} = 2h \sqrt{\left(\frac{MUF}{f_{cr}}\right)^2 - 1}}$$

---

### Q20 a) List features of various modes of radio wave propagation

| Mode | Frequency | Key Features |
|------|-----------|---------------|
| **Ground/Surface** | 15 kHz - 2 MHz | Follows Earth surface, vertically polarized, regional range |
| **Space/Tropospheric** | > 30 MHz | LOS path, limited by Earth curvature, antenna height |
| **Sky/Ionospheric** | 2 - 30 MHz | Reflected by ionosphere, global range, solar dependent |

---

### Q20 b) Calculate critical frequency from electron density

> **Given:**
> - Maximum electron density $N_{max} = 1.24 \times 10^8$ electrons/cc

**Solution:**

**Convert to per m³:**
$$1 \text{ m}^3 = 10^6 \text{ cm}^3$$
$$N_{max} = 1.24 \times 10^8 \times 10^6 = 1.24 \times 10^{14} \text{ electrons/m}^3$$

**Apply formula:**
$$f_{cr} = 9 \times \sqrt{1.24 \times 10^{14}}$$
$$f_{cr} = 9 \times 1.113 \times 10^7$$
$$f_{cr} \approx 10.02 \times 10^7 \text{ Hz} = \boxed{100.2 \text{ MHz}}$$

---

> 📚 Related Notes:
> - [[Ionospheric propagation|Ionospheric Propagation]]
> - [[Space wave and surface wave|Space Wave]]
> - [[Ground wave propagation|Ground Wave]]
> - [[Critical Frequency|Critical Frequency]]
> - [[Maximum Usable Frequency|MUF]]
> - [[Virtual Height|Virtual Height]]
> - [[Ionosphere Layers|Ionosphere Layers]]