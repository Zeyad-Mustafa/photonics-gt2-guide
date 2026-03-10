# IP-Dip2 — Overview

> IP-Dip2 is the primary resist for the 63x objective and the go-to choice when you need the absolute highest resolution the GT2 can achieve. This file explains what it is, why it exists, and when to use it.

---

## What Is IP-Dip2?

**IP-Dip2** is Nanoscribe's second-generation dip-in lithography resist, designed specifically for use with the **63x oil-immersion objective** in DiLL (Dip-In Laser Lithography) mode. It is a low-viscosity photopolymer resin that the objective tip is submerged into directly during printing.

The "Dip2" designation indicates it is the successor to the original IP-Dip formulation, with improvements in:
- Reduced polymerization threshold (more sensitive — requires less laser power)
- Lower shrinkage than IP-Dip
- Better batch-to-batch consistency
- Optimized refractive index match for the 63x objective

---

## Key Specifications

| Parameter | Value |
|---|---|
| Refractive index (n) at 780 nm | 1.511 |
| Recommended objective | 63x (NA 1.4) |
| Printing mode | DiLL (Dip-In Laser Lithography) |
| Minimum lateral feature size | ~160 nm |
| Minimum axial (Z) feature size | ~500 nm |
| Developer | PGMEA, followed by IPA rinse |
| Appearance | Clear, colorless liquid |
| Viscosity | Low (similar to water) |

---

## Why 1.511 Refractive Index?

The refractive index of IP-Dip2 (n = 1.511) is deliberately matched to:

1. **Immersion oil used with the 63x objective** — the 63x is an oil-immersion objective. The immersion oil (Zeiss Immersol 518F, n = 1.518) bridges the gap between the objective's front lens and the substrate. IP-Dip2's n of 1.511 is close enough to the oil that the optical path remains consistent from the objective through the oil, through the substrate (borosilicate glass, n ≈ 1.515), and into the resist.

2. **Minimizing spherical aberration** — if the refractive index of the resist were very different from the oil, the focal spot would distort as depth increases. Matching n values keeps the voxel shape consistent throughout the print depth.

> If you tried to print IP-S (n = 1.478) with the 63x oil objective, the refractive index mismatch would cause severe spherical aberration, distorted voxels, and failed interface detection.

---

## When to Use IP-Dip2

Use IP-Dip2 when:

- You need features smaller than ~500 nm lateral size
- Your application requires the absolute maximum resolution of the GT2
- You are printing photonic crystals, nano-gratings, or sub-wavelength structures
- Your substrate is quartz, borosilicate glass (170 um), or silicon (with appropriate n)
- Print volume is small (the 63x print field is ~150 x 150 um maximum)

Do NOT use IP-Dip2 when:

- Your structure is larger than ~200 x 200 x 100 um (use IP-S with 25x instead)
- Speed is a priority (the 63x/IP-Dip2 combination is inherently slow)
- You need flexible or biocompatible output (wrong material class entirely)

---

## IP-Dip2 vs. the Original IP-Dip

| Property | IP-Dip | IP-Dip2 |
|---|---|---|
| Refractive index | ~1.52 | 1.511 |
| Sensitivity | Moderate | Higher (lower threshold power) |
| Shrinkage | Moderate | Lower |
| Availability | Being phased out | Current standard |
| Recommended | Legacy workflows only | All new workflows |

If your lab has a stock of IP-Dip (original), it will still work with the 63x objective, but IP-Dip2 should be preferred for any new work. The parameters differ — do not use IP-Dip parameters when printing with IP-Dip2.

---

## Related Files

- [properties.md](./properties.md) — Detailed physical and optical properties
- [use_with_63x.md](./use_with_63x.md) — Step-by-step workflow with the 63x objective
- [handling_and_storage.md](./handling_and_storage.md) — Storage temperature, light protection, disposal
- [03_Objectives/63x_objective/overview.md](../../03_Objectives/63x_objective/overview.md)
- [resist_selection_guide.md](../resist_selection_guide.md)