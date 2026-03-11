# Voxel Sizes Reference

## Overview

Voxel size is not fixed — it depends on objective, laser power, scan speed, and resin. The values below are for typical operating conditions. Higher power produces larger voxels; lower power produces smaller voxels down to the polymerization threshold.

Lateral voxel = smallest printable feature dimension in XY
Axial voxel = smallest printable feature dimension in Z (always larger than lateral)
Aspect ratio = axial divided by lateral

---

## 63x Objective (NA 1.4, IP-Dip2)

| Condition | Lateral voxel | Axial voxel | Aspect ratio |
|---|---|---|---|
| Low power (12 to 15%) | 130 to 160 nm | 350 to 450 nm | ~3:1 |
| Typical power (18 to 25%) | 160 to 250 nm | 450 to 600 nm | ~3:1 |
| High power (30 to 35%) | 250 to 400 nm | 600 to 900 nm | ~3:1 |

Notes:
- The 63x produces the smallest voxels of any GT2 objective.
- At low power (12 to 15%), features below 200 nm lateral are achievable by operating near the polymerization threshold.
- The 3:1 axial-to-lateral aspect ratio is fundamental to the optics and cannot be significantly changed by parameter adjustment.

---

## 25x Objective (NA 0.8, IP-S)

| Condition | Lateral voxel | Axial voxel | Aspect ratio |
|---|---|---|---|
| Low power (18 to 22%) | 350 to 450 nm | 1.0 to 1.3 um | ~3:1 |
| Typical power (25 to 35%) | 400 to 600 nm | 1.2 to 1.8 um | ~3:1 |
| High power (40 to 45%) | 600 to 900 nm | 1.8 to 2.5 um | ~3:1 |

Notes:
- Voxel size is larger than the 63x due to lower NA.
- Minimum stable feature: approximately 800 nm lateral, 1.5 um axial at typical power.
- Values are similar for IP-Visio and IPX-Clear at the same power percentages.

---

## 10x Objective (NA 0.3, IP-Q)

| Condition | Lateral voxel | Axial voxel | Aspect ratio |
|---|---|---|---|
| Low power (35 to 40%) | 1.2 to 1.6 um | 8 to 10 um | ~7:1 |
| Typical power (45 to 55%) | 1.6 to 2.5 um | 10 to 14 um | ~7:1 |
| High power (60 to 70%) | 2.5 to 4.0 um | 14 to 18 um | ~7:1 |

Notes:
- The 10x has a much larger axial-to-lateral aspect ratio (~7:1) compared to high-NA objectives because low NA objectives have less axial confinement of the focal volume.
- Minimum stable feature: approximately 3 to 5 um lateral.
- Large axial voxel is an advantage for fast printing of tall structures — fewer layers are needed for the same height.

---

## Voxel Aspect Ratio Comparison

| Objective | NA | Lateral voxel (typical) | Axial voxel (typical) | Aspect ratio |
|---|---|---|---|---|
| 63x | 1.4 | 160 to 250 nm | 450 to 600 nm | ~3:1 |
| 25x | 0.8 | 400 to 600 nm | 1.2 to 1.8 um | ~3:1 |
| 10x | 0.3 | 1.6 to 2.5 um | 10 to 14 um | ~7:1 |

The increase in axial aspect ratio at low NA is one reason the 10x objective is used for large structures rather than high-resolution ones — the axial smearing at low NA would destroy fine Z-resolution features even if the lateral size were acceptable.

---

## Effect of Resin on Voxel Size

Different resins have different photoinitiator concentrations and monomer reactivity. At the same laser power percentage, voxel sizes vary between resins:

| Resin | Relative sensitivity | Voxel size compared to IP-S at same power |
|---|---|---|
| IP-Dip2 | High | Smaller (requires less power for same voxel) |
| IP-S | Reference | Reference |
| IP-Visio | Moderate | Slightly larger (requires slightly more power) |
| IP-PDMS | Low | Larger (requires significantly more power) |
| IP-Q | Moderate | Similar to IP-S |
| GP-Silica | Low | Larger (nanoparticle loading reduces sensitivity) |

---

## Using Voxel Size to Tune Feature Dimensions

For a target lateral feature size smaller than the typical voxel:
- Reduce laser power toward the polymerization threshold
- Only the central region of the focal volume exceeds threshold, producing a smaller effective voxel
- Verify with SEM — optical microscopy cannot resolve sub-500 nm features

For a target feature size larger than the minimum voxel:
- Increase laser power, which enlarges the effective voxel
- Or write multiple adjacent scan lines — hatch distance determines how they overlap and merge
