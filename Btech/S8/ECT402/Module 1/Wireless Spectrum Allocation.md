---
tags:
  - wireless_communication
  - spectrum
  - standards
---

# Wireless Spectrum Allocation & Standards

> The radio frequency spectrum is a **limited and expensive natural resource**. Efficient allocation is critical for wireless communication systems.

## Electromagnetic Spectrum

```mermaid
frequencyChart
    x-axis[Frequency (Hz)]
    ranges[
        {label: 'ELF/SLF/ULF', freq: '3 Hz - 3 kHz'},
        {label: 'VLF', freq: '3 - 30 kHz'},
        {label: 'LF', freq: '30 - 300 kHz'},
        {label: 'MF', freq: '300 kHz - 3 MHz'},
        {label: 'HF', freq: '3 - 30 MHz'},
        {label: 'VHF', freq: '30 - 300 MHz'},
        {label: 'UHF', freq: '300 MHz - 3 GHz'},
        {label: 'SHF', freq: '3 - 30 GHz'},
        {label: 'EHF', freq: '30 - 300 GHz'},
    ]
```

## Key Wireless Bands

| Band | Frequency | Typical Applications |
|------|-----------|---------------------|
| **LF (Low Frequency)** | 30-300 kHz | AM broadcasting, navigation |
| **MF (Medium Frequency)** | 300 kHz - 3 MHz | AM broadcasting (540-1600 kHz) |
| **HF (High Frequency)** | 3-30 MHz | Shortwave radio, RFID |
| **VHF (Very High Frequency)** | 30-300 MHz | FM radio (88-108 MHz), TV (Channels 2-13) |
| **UHF (Ultra High Frequency)** | 300 MHz - 3 GHz | TV (Channels 14-69), cellular, Wi-Fi |
| **SHF (Super High Frequency)** | 3-30 GHz | Wi-Fi (5 GHz), Satellite, Radar |
| **EHF (Extremely High Frequency)** | 30-300 GHz | 5G mmWave, 6G (planned) |

## Frequency Allocation Process

In most countries, spectrum allocation is regulated by government bodies:

- 🇺🇸 **FCC** (Federal Communications Commission) - USA
- 🇮🇳 **TRAI** (Telecom Regulatory Authority of India) - India
- 🇪🇺 **CEPT/ECC** - Europe

### Spectrum Allocation Methods

1. **Command & Control**: Government assigns specific frequencies to specific services
2. **Market-Based**: Frequencies auctioned to highest bidders (common for cellular)
3. **Unlicensed**: Open for anyone (e.g., Wi-Fi at 2.4/5 GHz, Bluetooth)

## Common Wireless Standards

| Standard | Frequency | Data Rate | Range | Application |
|----------|-----------|----------|-------|-----------|
| **Bluetooth** | 2.4 GHz | 1-3 Mbps | 10-100m | PAN |
| **Wi-Fi 802.11b** | 2.4 GHz | 11 Mbps | 100m | WLAN |
| **Wi-Fi 802.11g** | 2.4 GHz | 54 Mbps | 100m | WLAN |
| **Wi-Fi 802.11n** | 2.4/5 GHz | 600 Mbps | 250m | WLAN |
| **Wi-Fi 802.11ac** | 5 GHz | 3.5 Gbps | 250m | WLAN |
| **Wi-Fi 802.11ax** | 2.4/5/6 GHz | 9.6 Gbps | 250m | WLAN |
| **Zigbee** | 2.4 GHz | 250 kbps | 10-100m | IoT |
| **LTE (4G)** | 700 MHz - 2.6 GHz | 100-300 Mbps | 10+ km | Cellular |
| **5G NR** | Sub-6 GHz + mmWave | 1-10 Gbps | 10+ km | Cellular |
| **WiMAX** | 2.3-3.5 GHz | 70 Mbps | 50 km | Broadband |

## ISM Bands

> **ISM (Industrial, Scientific, Medical)** bands are unlicensed frequency ranges reserved for equipment like microwave ovens, RFID, and short-range communication.

| Band | Frequency | Regulated By |
|------|-----------|--------------|
| **ISM 433 MHz** | 433.05 - 433.79 MHz | Short Range Devices |
| **ISM 2.4 GHz** | 2.4 - 2.4835 GHz | Wi-Fi, Bluetooth, Zigbee |
| **ISM 5.8 GHz** | 5.725 - 5.875 GHz | Wi-Fi (U-NII) |

## Spectrum Efficiency Techniques

To maximize utilization of limited spectrum:

1. **Frequency Reuse** - Same frequencies used in spatially separated cells
2. **Spatial Division Multiple Access (SDMA)** - Beamforming to separate users
3. **Time Division (TDMA/FDMA)** - Sharing channels across time/frequency
4. **Code Division (CDMA)** - Spread spectrum using unique codes
5. **OFDM/OFDMA** - Multiple orthogonal sub-carriers

---

**Related Topics:**
- [[Cellular System Design Fundamentals]]
- [[Generations]]
- [[WLAN]]
- [[Bluetooth, PAN, WiMax]]