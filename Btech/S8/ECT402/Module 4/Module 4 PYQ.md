---
id: Module 4 PYQ
tags:
  - academics
  - btech
  - s8
  - ect402
  - module4
  - pyq
dg-publish: true
---

# Module 4 PYQ - Diversity, Equalization, and Multiple Access

---

## 1. Differentiate between Microdiversity and Macrodiversity.

### Answer

| Aspect | Microdiversity | Macrodiversity |
|--------|---------------|----------------|
| **Scale** | Small (same location) | Large (different locations) |
| **Target** | Small-scale fading | Large-scale fading (shadowing) |
| **Implementation** | Multiple antennas at same BTS | Multiple base stations |
| **Handoff** | Not required | Required (soft/hard handover) |
| **Examples** | [[4.1 Diversity#selection-combining| MRC]], [[4.1 Diversity#selection-combining| Selection Combining]], [[4.1 Diversity#alamouti-scheme-2x2-mimo| Alamouti]] | Soft handover in CDMA, Cooperative diversity |

### Explanation

- **Microdiversity**: Diversity techniques applied at the same location using multiple antennas. Used to combat [[Module 2/Fading Theory#small-scale-fading| small-scale fading ]] caused by [[Module 2/Multipath Propagation| multipath propagation ]]. Antennas are typically separated by λ/2.

- **Macrodiversity**: Diversity across different geographic locations (multiple base stations). Used to combat [[Module 2/Fading Theory#large-scale-fading| large-scale fading ]] ([[Module 2/Path Loss#shadowing| shadowing ]]) caused by obstacles between transmitter and receiver. Requires handoff mechanisms.

---

## 2. Why does Maximal Ratio Combining achieve full diversity?

### Answer

**Full diversity** means the diversity order equals the number of independent receive branches (N). MRC achieves this because it **coherently combines** all received signals, weighting each branch by its channel gain.

We say MRC achieves "full diversity" because it extracts and perfectly combines the useful energy from *every single available signal branch*.

Unlike Selection Combining, which simply picks the strongest signal and throws the rest away, MRC applies a weight to each branch based on its specific channel gain. It aligns the phases of all the incoming signals so they add together constructively.

Because of this optimal combining, the total output SNR becomes the exact sum of the individual SNRs from all the branches ($\gamma_{out} = \gamma_1 + \gamma_2 + ... + \gamma_N$). By capturing all the available energy across all $N$ branches, it achieves a diversity order of exactly $N$, which is the maximum (or "full") possible diversity gain for that system.

### Key Reasons

1. **Weighted Combining**: Each branch is weighted by $w_k = h_k^*$ (channel gain conjugate)
2. **Coherent Addition**: Signals add in phase, maximizing SNR
3. **Sum of SNRs**: Combined SNR = Σ (γ_k) - the sum of all branch SNRs
4. **Error Probability**: P_e ∝ (SNR)^(-N) - decays with order N

### Mathematical Insight

For N branches: $r_k = \sqrt{E_s} h_k s + n_k$

After MRC combining:
$$y = \sum_{k=1}^{N} w_k r_k = \sqrt{E_s} s \sum_{k=1}^{N} |h_k|^2 + \sum_{k=1}^{N} h_k^* n_k$$

Combined SNR:
$$\gamma_{total} = \frac{E_s}{N_0} \sum_{k=1}^{N} |h_k|^2 = \sum_{k=1}^{N} \gamma_k$$

### Comparison

| Technique | Diversity Order |
|-----------|----------------|
| MRC | N (full) |
| Selection Combining | 1 |
| Equal Gain Combining | N |

**Why Selection Combining fails**: Uses only the single best branch, discarding energy from other branches. Only achieves first-order diversity.

---

## Footnotes

[^1]: See [[4.1 Diversity]] - Detailed notes on diversity techniques

[^2]: See [[4.2 Equalization]] - Detailed notes on equalization

[^3]: See [[4.3 Multiuser Systems]] - Detailed notes on multiple access

---

*More questions to be added...*
