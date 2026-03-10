# i-line Photoresists — Overview

> i-line resists are not 2PP materials. They are conventional photoresists used with the GT2's 20x air objective for 2D and pseudo-3D patterning on spin-coated wafers. This file explains what they are and when they apply.

---

## What Are i-line Photoresists?

**i-line photoresists** are standard single-photon photosensitive polymer films used in conventional photolithography. The term "i-line" refers to the 365 nm mercury lamp emission line that is the classic exposure wavelength for this resist class.

On the GT2, i-line resists are exposed using the **780 nm femtosecond laser**, not a 365 nm source. The two-photon absorption of the 780 nm pulsed beam provides enough photon energy to expose the i-line resist (2 x 1.59 eV = 3.18 eV, equivalent to ~390 nm — close to the i-line absorption band of most such resists).

This means the GT2 can write **2D patterns directly on spin-coated photoresist wafers** without a photomask, using laser direct writing.

---

## Key Differences from IP-Series Resists

| Property | IP-series (2PP resists) | i-line photoresists |
|---|---|---|
| Physical state before printing | Liquid drop on substrate | Solid film, spin-coated on substrate |
| Exposure mechanism | Two-photon polymerization | Near-threshold single-photon (or two-photon) absorption |
| Result of exposure | Solidified 3D voxel | Changed solubility in developer |
| 3D capability | Full 3D | 2D only (flat pattern in the film plane) |
| Objective used | 10x, 25x, 63x | 20x air objective only |
| Sample holder | Universal or Multi-DiLL | 5-inch mask holder or Universal |
| Development | PGMEA + IPA | Standard photoresist developer (e.g., AZ 300 MIF, MF-319) |

---

## When to Use i-line Resists on the GT2

Use i-line resists when:

- You need standard 2D lithography patterns (lines, pads, contacts) without a photomask
- Your design requires sub-1 um 2D features (the 20x air objective can resolve ~500 nm 2D features in suitable resists)
- You are integrating GT2 patterning into a larger cleanroom process flow that uses conventional photoresist layers
- You need patterns on large wafer areas (up to 4 inches with the 5-inch mask holder)

Do NOT use i-line resists when:

- You need 3D structures (i-line resists cannot build 3D geometry — use any IP-series resist)
- You need the highest UV/visible transparency (i-line resists are designed to absorb light, not transmit it)

---

## Common i-line Resist Options

| Resist | Type | Developer | Notes |
|---|---|---|---|
| AZ 1505 | Positive | AZ 300 MIF or AZ 726 | Thin, ~500 nm at standard spin speeds; good for fine features |
| AZ 4110 | Positive | AZ 300 MIF | Thicker, ~1 um; good for etch masks |
| SU-8 (2000.5 - 2010) | Negative | SU-8 developer (PGMEA) | Thick, chemically resistant cross-linked structures; pseudo-3D possible with thick films |
| ma-N 1400 series | Negative | ma-D 533S | Good for chrome lift-off processes |

> The choice of specific i-line resist depends on your downstream process (etch mask, lift-off, structural). This is a conventional photolithography choice — consult your cleanroom's process documentation.

---

## Related Files

- [spin_coating_guide.md](./spin_coating_guide.md)
- [03_Objectives/20x_objective/overview.md](../../03_Objectives/20x_objective/overview.md)
- [03_Objectives/20x_objective/compatible_resists.md](../../03_Objectives/20x_objective/compatible_resists.md)
- [09_Printing_Modes/air_mode.md](../../09_Printing_Modes/air_mode.md)