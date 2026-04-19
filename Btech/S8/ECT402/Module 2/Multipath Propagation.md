---
id: Multipath Propagation
tags:
  - academics
  - btech
  - s8
  - ect402
  - module2
dg-publish: true
---

# Multipath Propagation

Unlike signals in a wired channel, wireless signals bounce off various obstacles such as buildings, trees, and the ground. This scattering creates multiple "copies" of the transmitted signal that reach the receiver via different paths, each with a different length, time delay, and phase. When these multiple copies arrive at the receiver, their electromagnetic waves interact:

| Condition | Result |
|-----------|--------|
| In-phase (constructive) | Signal strength boosted |
| Out-of-phase (destructive) | Signal fades |

```mermaid
graph LR
    TX[TX] -->|"Path 1<br/>Direct"| P1
    TX -->|"Path 2<br/>Building"| P2
    TX -->|"Path 3<br/>Ground"| P3
    
    P1 -.->|"τ1"| S[Sum]
    P2 -.->|"τ2"| S
    S -.->|"Signal"| RX[RX]
    
    P3 -.->|"τ3"| S
    
    RX -->|"Constructive"| V1[Strong]
    RX -->|"Destructive"| V2[Weak]
    
    style TX fill:#4ecdc4,color:#fff
    style RX fill:#4ecdc4,color:#fff
    style V1 fill:#4ecdc4,color:#fff
    style V2 fill:#eb4d4b,color:#fff
```

---

## Key Concepts

- **Multipath** = multiple signal paths from TX to RX
- Each path has: **delay (τ)**, **phase**, **amplitude**
- Paths sum at receiver → **constructive** or **destructive** interference
- Causes **fading** in wireless channels

---

## Related Topics

- [[Module 2 PYQ#how-does-fading-occur-derive-the-expression-for-doppler-shift|Fading & Doppler]]
- [[Module 2 PYQ|Module 2 PYQ - Fading Types]]
- [[Fading Theory]]
- [[Statistical Multipath Channel Models]]