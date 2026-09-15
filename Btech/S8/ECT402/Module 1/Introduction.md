---
banner: "https://images.unsplash.com/photo-1583602621722-cbd1130b210b?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
banner_y: 0.116
tags:
  - wireless_communication
  - not_important
---

# Introduction

- At their core, these systems use electromagnetic waves—radio, microwave, sometimes even infrared or millimeter waves—to carry signals across space without needing a physical connection.

```mermaid
graph LR 
Transmitter --> Medium --> Receiver

```

- A transmitter takes your information (`voice`, `text`, `video`), converts it into an electrical signal, **and modulates it onto a carrier wave** (a high-frequency signal suitable for transmission).
- That carrier rides through the wireless medium—air, vacuum, sometimes even water.
- A receiver picks it up, demodulates it, and extracts the *original information*.

### Carrier

$$
y = A \sin(2\pi f t)
$$

Where:

* $A$ = amplitude
* $f$ = frequency
* $t$ = time
