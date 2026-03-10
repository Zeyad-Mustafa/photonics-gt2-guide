# 🔬 25× Objective — Overview

> The 25× is the most commonly used objective in most research labs. It strikes the ideal balance between resolution (~400 nm lateral) and print speed — making it the first choice for the majority of GT2 projects.

---

## Quick Specs

| Property | Value |
|---|---|
| Magnification | 25× |
| Numerical Aperture (NA) | 0.8 |
| Working Distance (WD) | 380 µm |
| Immersion type | DiLL (resin acts as immersion medium) |
| Resin stop type | Silicone ring |
| Lateral voxel size | ~400 nm |
| Axial voxel size | ~1.5 µm |
| Max structure height | ~380 µm |
| Max structure volume | ~1 mm³ |
| Typical laser power | 20–50% |

---

## What Makes the 25× the Most Versatile Objective

The 25× sits in the middle of the objective lineup — not the fastest, not the finest, but the most practical for a wide range of applications:

- **Resolution** good enough for most microfluidics, MEMS, and photonic devices
- **Speed** fast enough for structures up to ~1 mm³ in reasonable time (hours, not days)
- **Resist options** the widest selection: IP-S, IP-Visio, IP-PDMS, IP-Q, IPX-Clear
- **Standard substrate** ITO-coated glass is widely available and easy to handle

Most first-time GT2 users learn on the 25× before moving to the 63× or 10×.

---

## The Adjustment Ring — Critical Step

⚠️ The 25× objective has an **adjustment ring** on its body that MUST be set correctly before use.

The ring compensates for refractive index differences in the immersion medium. For DiLL mode with IP-series resins:

**Set the ring to "Glyc" (Glycerin position) — the 3 longest bars on the scale**

If the ring is set incorrectly:
- Focus quality degrades
- Voxel size increases unexpectedly
- Structures may appear blurry or incomplete
- Interface detection may fail

→ See [adjustment_ring_guide.md](adjustment_ring_guide.md) for full details with diagrams.

---

## Typical Applications

- Microfluidic chips and lab-on-chip devices (channel width > 2 µm)
- Cell scaffolds for tissue engineering (IP-Visio)
- Flexible microstructures (IP-PDMS)
- Photonic waveguides and couplers
- MEMS cantilevers and springs
- Micro-optical elements (lenses > 50 µm diameter)
- General research structures requiring µm-scale precision

---

## What You Cannot Do With the 25×

- ❌ Features smaller than ~1 µm reliably
- ❌ Sub-wavelength photonic crystal devices (use 63×)
- ❌ Structures taller than ~380 µm (use 10×)
- ❌ Millimeter-scale volumes efficiently (use 10×)

---

> 🔗 Next: [when_to_use.md](when_to_use.md)