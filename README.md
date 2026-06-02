# RF Frequency Component Selector

A lightweight, open-source tool for comparing and selecting RF frequency control components (OCXO, TCXO, Rubidium Oscillators, PDRO, PLL, GPSDO).

## Features

- 🔍 **Component Search**: Search by frequency, stability, phase noise, or model number
- 📊 **Side-by-Side Comparison**: Compare specifications across different component types
- 📐 **Phase Noise Calculator**: Calculate integrated phase noise from spot frequencies
- ⏱ **Stability Converter**: Convert between ppm, ppb, and ppt at any frequency
- 📋 **Selection Guide**: Interactive decision tree for choosing between OCXO vs TCXO vs Rubidium

## Quick Start

```bash
# Open directly in browser
open index.html

# Or serve locally
python3 -m http.server 8000
```

## Component Database

This tool includes specification data for frequency control components from [BRIDZA RF](https://rf.bridza.com), a distributor for Chengdu Samephase Technology (同相科技).

### Supported Component Types

| Type | Frequency Range | Stability | Typical Applications |
|------|----------------|-----------|---------------------|
| OCXO | 10MHz–100MHz | ±0.1ppb–±100ppb | Base stations, test equipment, radar |
| TCXO | 10MHz–100MHz | ±0.1ppm–±2ppm | Portable radios, GPS, telecom |
| Rubidium | 10MHz | ±5E-11/month | Timekeeping, navigation, calibration |
| PDRO | 1GHz–44GHz | -120dBc/Hz@1kHz | Radar, satellite comm, EW |
| PLL | 10MHz–100MHz | ±0.01ppb | Synthesizers, LO, frequency conversion |
| GPSDO | 10MHz | ±1E-12 (locked) | Timing infrastructure, PTP/NTP servers |

## Phase Noise Calculator

Calculate integrated phase noise from spot frequency measurements:

```javascript
// Example: Integrate phase noise from 100Hz to 1MHz
const spots = [
  { offset: 100, dBcHz: -120 },
  { offset: 1000, dBcHz: -145 },
  { offset: 10000, dBcHz: -154 },
  { offset: 100000, dBcHz: -156 },
  { offset: 1000000, dBcHz: -174 }
];
```

## OCXO vs TCXO Selection Guide

| Factor | OCXO | TCXO |
|--------|------|------|
| Temperature Stability | ±0.1–100 ppb | ±0.1–2 ppm |
| Power Consumption | 0.5–3W | 5–50mW |
| Warm-up Time | 1–5 min | <10ms |
| Phase Noise | Excellent | Good |
| Size | Larger (20x20mm+) | Compact (2x1.6mm+) |
| Cost | $20–$500+ | $1–$50 |
| Best For | High-precision timing | Portable/wearable devices |

Read the full comparison: [OCXO vs TCXO – Complete Selection Guide](https://rf.bridza.com/resources/comparisons/ocxo-vs-tcxo.html)

## Resources

- [BRIDZA RF Product Catalog](https://rf.bridza.com/products/) – OCXO, TCXO, Rubidium, PDRO, PLL, GPSDO
- [OCXO vs TCXO Comparison](https://rf.bridza.com/resources/comparisons/ocxo-vs-tcxo.html)
- [PDRO Selection Guide](https://rf.bridza.com/resources/application-notes/app-note-09-pdro-selection-guide.html)
- [Phase Micro-Stepper Guide](https://rf.bridza.com/resources/application-notes/app-note-08-phase-micro-stepper.html)

## License

MIT License – Free to use, modify, and distribute.

## Contributing

Contributions welcome! Please feel free to submit a Pull Request.

---

*Data sourced from [BRIDZA RF](https://rf.bridza.com) – RF frequency control components for engineers worldwide.*
