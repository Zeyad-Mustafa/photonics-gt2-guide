# 🧱 10× Objective — Compatible Substrates

---

## Primary Substrate: Silicon Wafer

The 10× DiLL workflow is optimized for **silicon wafer substrates**, specifically pieces cut to approximately **25×25 mm**.

### Why Silicon?
- High refractive index (n ≈ 3.5) → large Δn vs IP-Q resin (n = 1.48) → reliable interface detection
- Extremely flat surface → consistent working distance across large print areas
- Readily available, inexpensive
- Compatible with downstream microfabrication (etching, deposition)

### Preparing Silicon Wafer Pieces
1. Use a **DISCO dicing saw** (or scribe-and-cleave) to cut 25×25 mm pieces from a full wafer
2. Clean with acetone → IPA → DI water → nitrogen dry
3. Optional: O₂ plasma (120 s, 100 W) for improved adhesion
4. Use the **polished side** (shiny side) facing up for resin deposition

---

## Secondary Substrate: Nanoscribe 25×25 mm Glass Slides

Pre-cut 25×25 mm borosilicate glass slides from Nanoscribe are also compatible with the 10×.

- Use when optical transparency of the substrate is required
- Refractive index of glass (n ≈ 1.52) is close to IP-Q (n = 1.48) — Δn is small (~0.04)
- Interface detection may be less reliable — ensure Δn ≥ 0.04
- Must use polished side facing objective

---

## Substrate Requirements Summary

| Requirement | Minimum Value |
|---|---|
| Refractive index difference (Δn) | ≥ 0.04 vs IP-Q |
| Surface flatness | < 5 µm across print area |
| Substrate thickness | Compatible with Multi-DiLL holder clearance |
| Surface cleanliness | No particles > 1 µm |

---

## What Substrates Do NOT Work With 10×

| Substrate | Reason |
|---|---|
| ITO-coated glass (standard) | This is the 25× substrate — wrong holder |
| 170 µm borosilicate | This is the 63× substrate |
| Flexible polymer films | Too much surface variation for reliable interface detection |
| Rough or unpolished surfaces | Interface detection fails |

---

> 🔗 Next: [voxel_dimensions.md](voxel_dimensions.md)