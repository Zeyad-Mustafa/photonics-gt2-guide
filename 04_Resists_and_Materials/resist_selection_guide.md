# Resist Selection Guide

> This file is your starting point every time you plan a new print. Use the decision tree and comparison tables below to identify the correct resist before you touch the machine.

---

## Decision Tree: Which Resist Do I Need?

Work through the questions in order. Stop at the first answer that applies.

```
START
  |
  v
Is your application biomedical? (cell scaffolds, implants, tissue contact)
  |
 YES --------> Use IP-Visio (25x objective)
  |
  NO
  |
  v
Do you need a flexible or elastic final structure?
  |
 YES --------> Use IP-PDMS (25x objective)
  |
  NO
  |
  v
Do you need to print true glass (fused silica)?
  |
 YES --------> Use GP-Silica (25x objective, 8-hour limit, sintering furnace required)
  |
  NO
  |
  v
Do you need the highest possible optical transparency for lenses or waveguides?
  |
 YES --------> Use IPX-Clear (compatible with 10x, 25x, 63x)
  |
  NO
  |
  v
What is your required feature resolution?
  |
  +-- Sub-200 nm features required --------> Use IP-Dip2 (63x objective)
  |
  +-- 500 nm to ~5 um features ---------> Use IP-S (25x) or IP-Dip2 (63x)
  |
  +-- 1 um to ~50 um features ----------> Use IP-S (25x) or IPX-Q (10x/25x)
  |
  +-- 10 um to mm-scale, fast print ----> Use IP-Q (10x) or IPX-Q (10x)
  |
  v
Are you doing 2D patterning on a spin-coated wafer?
  |
 YES --------> Use i-line photoresist (20x air objective)
  |
  NO
  |
  v
Default recommendation: IP-S with 25x objective
(balanced resolution, low shrinkage, well-characterized, easy to work with)
```

---

## Full Comparison Table

| Resist | Objective | Mode | Refractive Index (n) | Shrinkage | Viscosity | Key Strength | Limitation |
|---|---|---|---|---|---|---|---|
| IP-Dip2 | 63x | DiLL | 1.511 | Low-moderate | Low | Highest resolution, sub-200 nm | Slow, small build volume |
| IP-Dip | 63x | DiLL | ~1.52 | Moderate | Low | Proven original DiLL resist | Superseded by IP-Dip2 |
| IP-S | 25x | DiLL | 1.478 | Very low | Medium | Smooth surfaces, low shrinkage | Moderate resolution only |
| IP-Q | 10x | DiLL | 1.48 | Moderate | Low-medium | Fast large prints | Lower resolution than IP-S |
| IP-Visio | 25x | DiLL | ~1.48 | Low | Medium | Biocompatible, low fluorescence | Not for high-res features |
| IP-PDMS | 25x | DiLL | ~1.41 | Very low | High | Soft, elastic, flexible | Difficult to develop cleanly |
| IPX-Q | 10x, 25x | DiLL | ~1.48 | Moderate | Low-medium | Better clarity than IP-Q | Slight amber tint |
| IPX-Clear | 10x, 25x, 63x | DiLL / Oil | ~1.50 | Low | Medium | Maximum optical clarity | Newer, fewer published parameters |
| GP-Silica | 25x | DiLL | 1.46 (post-sinter) | High (sintering shrinks ~25%) | Very high (paste) | True fused silica result | 8-hr limit, furnace required |
| i-line resists | 20x | Air | varies | Low | depends on spin | Standard 2D lithography | No 3D printing capability |

---

## Resist-to-Objective Pairing Rules

This is not a preference — it is a hardware constraint. Each resist is formulated for a specific refractive index environment that matches its target objective and printing mode.

| Objective | Compatible Resists |
|---|---|
| 63x (NA 1.4, DiLL) | IP-Dip2, IP-Dip, IPX-Clear |
| 25x (NA 0.8, DiLL) | IP-S, IP-Visio, IP-PDMS, IP-Q, IPX-Q, IPX-Clear |
| 10x (NA 0.3, DiLL) | IP-Q, IPX-Q, IPX-Clear |
| 20x (NA 0.35, Air) | i-line photoresists only |

> Using a resist with the wrong objective will cause: failed interface detection, incorrect voxel size, poor polymerization, or no printing at all.

---

## Application-Based Quick Pick

| Application | Recommended Resist | Objective |
|---|---|---|
| Highest resolution microstructures | IP-Dip2 | 63x |
| Photonic crystals, waveguides | IPX-Clear or IP-Dip2 | 63x or 25x |
| Micro-optics (lenses, beam splitters) | IPX-Clear | 25x or 63x |
| Cell scaffolds, tissue engineering | IP-Visio | 25x |
| Microfluidic channels | IP-S or IP-PDMS | 25x |
| Soft robotics, flexible actuators | IP-PDMS | 25x |
| mm-scale structural parts (fast) | IP-Q or IPX-Q | 10x |
| True glass (fused silica) structures | GP-Silica | 25x |
| 2D lithography on wafer | i-line photoresist | 20x |
| Multi-scale stitched prints | IP-Q or IPX-Clear | 10x or 25x |

---

## How to Read a Resist Datasheet

When Nanoscribe provides a resist datasheet, the parameters you care most about are:

**Refractive index (n):** Must match the immersion medium/objective requirements for interface detection to work.

**Polymerization threshold power:** The minimum laser power at which polymerization begins. Below this, nothing happens. Going significantly above it causes blooming (voxels grow larger than intended).

**Voxel size (lateral / axial):** The expected minimum feature size at the polymerization threshold with the recommended objective. These values are typically given at a specific scan speed and laser power — do not use them out of context.

**Shrinkage (%):** How much the structure contracts after development and UV curing. High shrinkage causes warping, delamination, and dimensional inaccuracy.

**Developer compatibility:** Which solvents can be used to wash away the unexposed resin. Most IP-series resists use PGMEA (propylene glycol monomethyl ether acetate) followed by IPA rinse. See **[08_Development_and_Post_Processing/development_solvents.md](../08_Development_and_Post_Processing/development_solvents.md)**.

---

## Related Files

- [IP_Dip2/overview.md](./IP_Dip2/overview.md)
- [IP_S/overview.md](./IP_S/overview.md)
- [IP_Q/overview.md](./IP_Q/overview.md)
- [IPX_Clear/overview.md](./IPX_Clear/overview.md)
- [GP_Silica/overview.md](./GP_Silica/overview.md)
- [08_Development_and_Post_Processing/development_solvents.md](../08_Development_and_Post_Processing/development_solvents.md)
- [13_Key_Parameters_Reference/resist_properties_table.md](../13_Key_Parameters_Reference/resist_properties_table.md)