---
id: Shannon Capacity
tags:
  - academics
  - btech
  - s8
  - ect402
  - module2
dg-publish: true
---

# Shannon Capacity

**Shannon Capacity** = Maximum data rate for reliable communication over a noisy channel.

---

## Formula

$$C = B \log_2(1 + \text{SNR})$$

Where:
- $B$ = Bandwidth (Hz)
- $\text{SNR}$ = Signal-to-noise ratio

**AWGN form:**
$$C = W \log_2\left(1 + \frac{\bar{P}}{N_0 W}\right)$$

Where:
- $W$ = Channel bandwidth
- $\bar{P}$ = Average received power
- $N_0$ = Noise power spectral density

---

## Key Principle

If Data Rate > C → **Errors become unavoidable**

No coding, modulation, or tech can exceed this limit.

---

## Bandwidth vs Power Tradeoff

| Parameter | Relationship |
|-----------|--------------|
| Bandwidth | Capacity grows linearly (doubling B → doubling C) |
| Power | Capacity grows logarithmically (3 dB SNR → +B bits/s at high SNR) |

**Spectral Efficiency:**
$$\eta = \log_2(1 + \text{SNR}) \text{ bits/s/Hz}$$

---

## Practical Example

For B = 1 MHz, SNR = 100 (20 dB):

$$C = 1 \times 10^6 \times \log_2(101) \approx 6.66 \text{ Mbps}$$

---

## Capacity of Flat Fading Channel

### Ergodic Capacity

Average capacity over all fading states:

$$C_{ergodic} = E_{|h|^2}[\log_2(1 + \text{SNR} \cdot |h|^2)]$$

Data is encoded across multiple channel states to average out randomness.

---

## Capacity with Outage

In slow fading, channel stays constant over long bursts. If SNR < threshold → outage.

**Outage probability:**
$$P_{outage} = P(SNR < \rho_{min})$$

**Capacity with outage:**
$$C_{outage} = (1 - P_{outage}) W \log_2(1 + \rho_{min})$$

Rate reliably supported in (1-P_outage)% of time.

---

## Capacity with CSI-R (Receiver Only)

- Receiver knows channel (h), transmitter does not
- Transmitter cannot adapt power/rate
- Uses constant transmission power

$$C = E[\log_2(1 + \text{SNR} \cdot |h|^2)]$$

**Significance:** If transmitter had CSI, could use "waterfilling" — transmit more power when channel is good.

---

## Related Notes

- [[Module 2/Module 2 PYQ]] - PYQs on capacity
- [[Module 2/Path Loss]] - Path loss affects SNR