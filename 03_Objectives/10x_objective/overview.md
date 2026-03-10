# 🔭 10× Objective — Overview

> The 10× is the GT2's large-scale workhorse. It sacrifices resolution for speed and build volume — ideal when your structure is measured in millimeters rather than microns.

---

## Quick Specs

| Property | Value |
|---|---|
| Magnification | 10× |
| Numerical Aperture (NA) | 0.3 |
| Working Distance (WD) | 700 µm |
| Immersion type | DiLL (resin acts as immersion medium) |
| Resin stop type | Silicone ring |
| Lateral voxel size | ~1.6 µm |
| Axial voxel size | ~12 µm |
| Max structure height | ~700 µm |
| Max structure volume | ~10 mm³ |
| Typical laser power | 30–70% |

---

## What Makes the 10× Unique

The 10× objective has the **lowest numerical aperture (NA = 0.3)** of all GT2 objectives. Low NA means:

- **Larger focal volume** → larger voxels → lower resolution
- **Longer working distance (700 µm)** → can print taller structures than the other objectives
- **Less sensitive to substrate flatness** → more tolerant of imperfect substrates

The 10× is not designed for fine detail. It is designed for **printing large, complex 3D structures quickly** when micron-level resolution is acceptable.

---

## Typical Applications

- Large photonic scaffolds and lattices (mm-scale)
- Microfluidic channel molds (>10 µm features)
- Mechanical metamaterials with large unit cells
- Rapid prototyping of structures before switching to higher-res objective
- Structures requiring millimeter total height (up to ~700 µm)
- Multi-material prints using IP-Q as base layer

---

## What You Cannot Do With the 10×

- ❌ Print features smaller than ~5 µm reliably
- ❌ Use IP-Dip2, IP-S, IP-Visio, or IP-PDMS resists
- ❌ Achieve smooth vertical walls (axial voxel is 12 µm — stairstepping visible)
- ❌ Print high-aspect-ratio pillars thinner than ~10 µm

---

## Key Difference From 25× and 63×

The 10× uses a **Multi-DiLL Si Wafer holder** configuration — it is specifically optimized for printing on silicon wafer substrates. In NanoWrite, you must select the correct holder type that corresponds to the 10× workflow.

Also unlike the 25× and 63×, the 10× is more often run in **galvo scanning mode** for the outer layers to maximize speed, with piezo used only for the finest internal features.

---

> 🔗 Next in this folder: [when_to_use.md](when_to_use.md)