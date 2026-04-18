---
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
