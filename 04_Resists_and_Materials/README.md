# Module 04 — Resists and Materials

> "The objective defines what is possible. The resist defines what actually happens."
> This module covers every photopolymer resin and material the GT2 can print with — what it is, why it exists, how to use it, and how to store it safely.

---

## What You Will Learn in This Module

After reading all the files in this folder, you will be able to:

- Explain what a photoresist is and why the choice of resist matters as much as the choice of objective
- Select the correct resist for your application using the decision guide
- Describe the key physical and optical properties of each IP-series and IPX-series resist
- Handle, apply, and store each resist correctly and safely
- Understand the special requirements of GP-Silica and i-line resists
- Know which resist pairs with which objective, and why

---

## Files in This Module

| File | What It Covers |
|---|---|
| `resist_selection_guide.md` | Decision tree and comparison table — how to pick the right resist |
| `IP_Dip2/overview.md` | Highest resolution resist, refractive index 1.511, 63x only |
| `IP_Dip2/properties.md` | Viscosity, sensitivity, shrinkage, refractive index data |
| `IP_Dip2/use_with_63x.md` | Specific workflow steps for IP-Dip2 with the 63x objective |
| `IP_Dip2/handling_and_storage.md` | Temperature, light exposure, shelf life, disposal |
| `IP_S/overview.md` | Low-shrinkage, smooth-surface resist for the 25x objective |
| `IP_S/properties.md` | Physical and optical properties |
| `IP_S/use_with_25x.md` | Workflow steps for IP-S with the 25x objective |
| `IP_S/handling_and_storage.md` | Storage and safety |
| `IP_Q/overview.md` | Fast large-volume printing, 10x objective |
| `IP_Q/properties.md` | Properties and print characteristics |
| `IP_Q/drop_casting_technique.md` | Critical: only 1-2 drops, semi-spherical shape required |
| `IP_Q/handling_and_storage.md` | Storage and safety |
| `IP_Visio/overview.md` | Biocompatible, very low fluorescence, cell scaffold applications |
| `IP_Visio/bio_applications.md` | Cell scaffolds, lab-on-chip, tissue engineering |
| `IP_Visio/handling_and_storage.md` | Biocompatibility handling precautions |
| `IP_PDMS/overview.md` | Soft, flexible, elastic printed structures |
| `IP_PDMS/applications.md` | Microfluidics, soft robotics, flexible devices |
| `IP_PDMS/handling_and_storage.md` | PDMS-specific handling notes |
| `IPX_Q/overview.md` | Better resolution than IP-Q, slight amber tint |
| `IPX_Q/comparison_with_IP_Q.md` | Side-by-side comparison: when to choose IPX-Q over IP-Q |
| `IPX_Clear/overview.md` | Highly transparent, compatible with all objectives |
| `IPX_Clear/optical_applications.md` | Lenses, waveguides, photonic devices |
| `IPX_Clear/handling_and_storage.md` | Storage and safety |
| `GP_Silica/overview.md` | Fused silica beads — the only way to print real glass on the GT2 |
| `GP_Silica/workflow_special_steps.md` | 8-hour print time limit, special substrate requirements |
| `GP_Silica/debinding_and_sintering.md` | Furnace steps: debinding at 600C, sintering at 1500C |
| `i_line_photoresists/overview.md` | Standard photoresists for the 20x air objective |
| `i_line_photoresists/spin_coating_guide.md` | Spin speed, bake conditions, development |

---

## What Is a Photoresist?

A **photoresist** (or "resist") is a light-sensitive material that changes its physical or chemical properties when exposed to light. In the context of the GT2:

- The resist starts as a **liquid** (a photopolymer resin)
- Exposure to the focused laser causes the liquid to **solidify** (polymerize) at the focal point
- After printing, the unexposed liquid is washed away with a developer solvent, leaving only the solid 3D structure

This is the same fundamental principle used in photolithography (semiconductor fabrication) and standard SLA 3D printing — but at a resolution orders of magnitude finer, thanks to the two-photon absorption physics described in **[01_Physics_and_Principles](../01_Physics_and_Principles/README.md)**.

---

## Why Does Resist Choice Matter?

Beginners often assume the objective is the dominant factor in print quality. In reality, **the resist is equally important**. The resist determines:

| Property | What It Affects |
|---|---|
| Refractive index (n) | Interface detection, optical path through the material |
| Viscosity | How the drop behaves, how well it wets the substrate |
| Sensitivity (polymerization threshold) | Minimum laser power needed, voxel size control |
| Shrinkage | Dimensional accuracy of the final structure |
| Biocompatibility | Whether cells can survive on the printed structure |
| Mechanical properties | Stiffness, elasticity, flexibility of the final part |
| Optical transparency | Whether the structure can guide or transmit light |
| Fluorescence background | Critical for fluorescence microscopy applications |

There is no single "best" resist. There is only the best resist **for your specific application**.

---

## The IP-Series vs. IPX-Series: What Is the Difference?

Nanoscribe's resists fall into two families:

**IP-series** (original formulation):
- IP-Dip2, IP-Dip, IP-S, IP-Q, IP-Visio, IP-PDMS
- Proven, well-characterized formulations
- Specific objective pairings (not all IP resists work with all objectives)

**IPX-series** (extended/improved formulations):
- IPX-Q, IPX-Clear
- Improved optical clarity, reduced yellowing, or broader objective compatibility
- IPX-Clear is notable for being compatible with **all four objectives**

---

## Resist at a Glance

| Resist | Objective | Key Strength | Refractive Index |
|---|---|---|---|
| IP-Dip2 | 63x | Highest resolution, sub-200 nm | 1.511 |
| IP-Dip | 63x | Original DiLL resist | ~1.52 |
| IP-S | 25x | Low shrinkage, smooth surfaces | 1.478 |
| IP-Q | 10x | Fast large-volume prints | 1.48 |
| IP-Visio | 25x | Biocompatible, low fluorescence | ~1.48 |
| IP-PDMS | 25x | Flexible, elastic structures | ~1.41 |
| IPX-Q | 10x, 25x | Better resolution than IP-Q | ~1.48 |
| IPX-Clear | All | Highest optical clarity | ~1.50 |
| GP-Silica | 25x | True fused silica (glass) after sintering | 1.46 (post-sinter) |
| i-line resists | 20x | Standard 2D lithography | varies |

---

## Chemical Safety Note

All IP-series and IPX-series resists are **photopolymer resins** containing acrylate monomers and photoinitiators. They require:

- Handling in a **fume hood** or well-ventilated area
- **Nitrile gloves** at all times (acrylates are skin sensitizers)
- Protection from ambient light during use (they are photosensitive)
- Proper waste disposal (do not pour down the drain)

Full chemical safety information: **[12_Safety/chemical_safety.md](../12_Safety/chemical_safety.md)**

---

## What Comes Next

After this module, proceed to:

- **[05_Substrates/](../05_Substrates/README.md)** — What substrates can the GT2 print on?
- **[06_Software_Workflow/](../06_Software_Workflow/README.md)** — DeScribe and NanoWrite
- **[07_Step_by_Step_Workflows/](../07_Step_by_Step_Workflows/README.md)** — Complete end-to-end print workflows