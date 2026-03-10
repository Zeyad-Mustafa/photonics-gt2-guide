# 🖨️ How the GT2 Differs from Regular 3D Printing

> If you've used a desktop 3D printer before, this page will help you understand what's the same, what's different, and why those differences matter.

---

## What They Have in Common

Both regular 3D printers and the GT2:
- Take a 3D digital design as input (usually an STL file)
- Build structures layer by layer (bottom to top)
- Are controlled by software that converts your design into machine instructions
- Produce real physical objects you can hold

That's roughly where the similarities end.

---

## The Big Differences

### 1. Scale

| | Desktop FDM Printer | Nanoscribe GT2 |
|---|---|---|
| Smallest feature | ~200 µm (0.2 mm) | ~160 nm (0.00016 mm) |
| Ratio | — | **1,000× smaller** |
| Typical object size | Coffee mug to furniture | Grain of sand to pinhead |

To put this in perspective: a single human hair is about 70,000 nm wide. The GT2 can print features **437 times thinner** than a hair.

---

### 2. How Material Is Added

| | FDM (Desktop) | SLA/Resin (Desktop) | GT2 (2PP) |
|---|---|---|---|
| Method | Melts and extrudes plastic | UV light cures whole layers | Focused laser cures single voxels |
| Resolution | Low | Medium | Extremely high |
| Layer visibility | Yes (visible lines) | Slight | None (smooth surfaces) |
| 3D true freedom | Limited overhangs | Moderate | Full — any angle, any curve |

The GT2 doesn't cure entire layers at once like a resin printer. It cures **one tiny point at a time**, giving it complete 3D freedom.

---

### 3. The Material (Resin)

| | Desktop Resin Printer | GT2 |
|---|---|---|
| Resin type | Standard UV photopolymer | Specialized IP-series resins |
| Curing wavelength | 385–405 nm (UV/violet) | 780 nm NIR (two-photon) |
| Resin cost | ~$30–80/liter | ~$200–500/mL |
| Handling | Relatively simple | Requires cleanroom/lab protocols |

GT2 resins are highly engineered for specific optical properties, shrinkage behavior, and biocompatibility. They are not interchangeable with desktop printer resins.

---

### 4. The Software Workflow

| Stage | Desktop Printer | GT2 |
|---|---|---|
| Design | Any CAD tool | Any CAD tool |
| Slicing | Cura, PrusaSlicer, etc. | **DeScribe** (Nanoscribe's own software) |
| Machine control | OctoPrint, Pronterface, etc. | **NanoWrite** (Nanoscribe's own software) |
| File format | G-code (.gcode) | GWL script (.gwl) |

DeScribe is more complex than a regular slicer — it gives you control over laser power, scan speed, voxel overlap, hatching strategy, and more. This power comes with a steeper learning curve.

---

### 5. Post-Processing

| | FDM | GT2 |
|---|---|---|
| After printing | Remove supports | **Development** (chemical wash) |
| Chemicals needed | None | PGMEA, IPA solvents |
| UV curing needed | No | Yes (405 nm station) |
| Time | Minutes | 25–45 minutes |

The GT2 requires a **development step** after printing — you must chemically wash away the uncured liquid resin. This step requires careful handling of solvents in a lab setting.

---

### 6. Speed

| Structure size | Desktop FDM | GT2 |
|---|---|---|
| 1 cm³ object | ~30–120 min | Days (not practical at this scale) |
| 1 mm³ object | 5–10 min | 1–8 hours |
| 0.01 mm³ object | Not precise enough | 5–60 min |

The GT2 is **not designed for large objects**. It excels at small, highly precise structures. For anything larger than ~5 mm, print time becomes impractical.

---

### 7. Cost and Environment

| | Desktop Printer | GT2 |
|---|---|---|
| Machine cost | $200 – $5,000 | ~$500,000+ |
| Material cost | $20–80/kg | $200–500/mL |
| Environment needed | Anywhere | Cleanroom or vibration-isolated lab |
| Training required | A few hours | Days to weeks |
| Typical user | Hobbyist, maker | Researcher, engineer |

---

## When Would You Choose the GT2 Over a Regular Printer?

Use the GT2 when:
- ✅ You need features smaller than 50 µm
- ✅ Surface smoothness is critical (optics, microfluidics)
- ✅ You need true 3D geometry (not just stacked layers)
- ✅ You need biocompatible or optically transparent structures
- ✅ Your structure interacts with light at the micro/nanoscale

Stick with a desktop printer when:
- ✅ Your object is larger than 5–10 mm
- ✅ Resolution doesn't matter much
- ✅ You need many copies quickly
- ✅ You need a quick prototype

---

> 🔗 **Next:** [Key Terms Glossary →](key_terms_glossary.md)