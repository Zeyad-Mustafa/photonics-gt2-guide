# GP-Silica — Overview

> GP-Silica is not a photopolymer resist. It is a silica nanoparticle composite paste. Printing with GP-Silica is a fundamentally different process that produces real fused silica glass structures after a high-temperature furnace cycle. Read this file entirely before attempting a GP-Silica print.

---

## What Is GP-Silica?

**GP-Silica** (Glass Printing Silica) is a composite printing material consisting of:

- **Fused silica (SiO2) nanoparticles** suspended in a photopolymer binder matrix
- The binder behaves like a standard photopolymer during printing — it polymerizes at the focal point of the 780 nm laser
- After printing, a **two-stage furnace process** burns away the organic binder (debinding) and sinters the silica nanoparticles into a dense, monolithic fused silica glass structure

The end result is a **true glass structure** — not a glass-like polymer, but actual fused silica with all its properties: high optical transparency across UV-to-NIR, excellent thermal stability (>1000 C), chemical resistance to nearly all solvents, and mechanical hardness.

---

## Key Specifications

| Parameter | Pre-Sinter (printed) | Post-Sinter (final glass) |
|---|---|---|
| Material | Silica/polymer composite | Fused silica (SiO2) |
| Refractive index | ~1.52 (printed) | 1.46 (fused silica) |
| Transparency | Limited (composite) | Excellent (UV to IR) |
| Mechanical hardness | Fragile (green body) | Very hard (glass) |
| Linear shrinkage | -- | ~25% (isotropic) |
| Max use temperature | ~100 C (binder melts) | >1000 C |

---

## Why Would You Use GP-Silica?

GP-Silica is chosen when the final structure must be **real glass**, not a polymer approximation. Applications include:

- Optical components that must survive high temperatures (e.g., inside a furnace or laser system)
- Chemically resistant microfluidic devices (glass is inert to acids, bases, solvents that dissolve polymers)
- Ultra-low-fluorescence optical components (fused silica has essentially zero autofluorescence)
- UV-transmitting optical elements (polymers typically absorb in the UV; fused silica transmits down to ~160 nm)
- High-precision micro-optics where glass's stable refractive index and dispersion properties are required

---

## The 25% Shrinkage Issue: How to Compensate

GP-Silica shrinks by approximately **25% linearly** during sintering (about 58% volumetrically). This is not a defect — it is inherent to the densification of the nanoparticle network.

To get a final glass structure of size X:
- Design and print at size X / 0.75 = X x 1.33

Example: To get a 100 um diameter post, design and print a 133 um diameter post. After sintering, it will be approximately 100 um.

The shrinkage is **isotropic** (equal in all directions) when the green body is free-standing. If the structure is constrained on one side (e.g., attached to a substrate during sintering), differential shrinkage can cause cracking. Free-standing sintering or careful substrate choice is required.

> Adjust all dimensions in your CAD file before printing. DeScribe has a scaling function — enter the inverse shrinkage factor (1.33x) before generating the GWL file.

---

## Recommended Objective

GP-Silica is used with the **25x objective** in DiLL mode. The 10x has insufficient resolution for the detail needed in most GP-Silica applications, and the 63x's small field makes it impractical for most glass structures.

---

## Related Files

- [workflow_special_steps.md](./workflow_special_steps.md)
- [debinding_and_sintering.md](./debinding_and_sintering.md)
- [07_Step_by_Step_Workflows/Workflow_D_Glass_Structures_GP_Silica/README.md](../../07_Step_by_Step_Workflows/Workflow_D_Glass_Structures_GP_Silica/README.md)
- [11_Troubleshooting/gp_silica_print_timeout.md](../../11_Troubleshooting/gp_silica_print_timeout.md)