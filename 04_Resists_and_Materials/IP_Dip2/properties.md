# IP-Dip2 — Properties

> This file covers the physical, optical, and print-process properties of IP-Dip2 in detail. Use this page when calibrating parameters or troubleshooting print quality.

---

## Optical Properties

| Property | Value | Notes |
|---|---|---|
| Refractive index (n) at 780 nm | 1.511 | Measured in liquid state; cured state is very similar |
| Absorption at 780 nm | Very low | Transparent to NIR — essential for deep printing |
| Transmission (visible) | >95% (cured) | Cured structures are optically clear |
| Fluorescence background | Low-moderate | Not ideal for confocal fluorescence imaging; use IP-Visio for that |

---

## Physical Properties (Liquid State)

| Property | Value |
|---|---|
| Appearance | Clear, colorless liquid |
| Viscosity | ~50-100 mPa·s (low, similar to light oil) |
| Density | ~1.1 g/cm3 |
| Vapor pressure | Low (low evaporation rate) |
| Miscibility | Miscible with PGMEA, IPA |

The low viscosity of IP-Dip2 is one of its important features. When the 63x objective dips into the resist, the low viscosity ensures:
- Complete wetting of the objective tip
- No air bubbles trapped at the interface
- Clean separation of the objective from the resist when the holder is removed

---

## Print Process Properties

| Property | Value | Notes |
|---|---|---|
| Polymerization threshold (typical) | ~10-20% laser power (63x, piezo, 10 mm/s) | Varies with scan speed — always calibrate for your system |
| Optimal laser power range | ~15-35% (63x) | Above ~50% risks blooming and proximity effects |
| Scan speed range | 1-10,000 um/s (piezo), up to 100 mm/s (galvo) | Higher speed = smaller voxel (less dose) |
| Minimum lateral voxel | ~160 nm | At threshold power, low scan speed, 63x |
| Minimum axial voxel | ~500 nm | Axial (Z) is always larger than lateral due to voxel aspect ratio |
| Voxel aspect ratio | ~1:3 (lateral:axial) | Elongated along the optical axis |

> These are representative values. Your actual threshold will depend on laser calibration, ambient temperature, resist age, and substrate. Always run a power/speed calibration array on a new batch.

---

## Mechanical Properties (Cured State)

| Property | Value | Notes |
|---|---|---|
| Young's modulus | ~0.5-1 GPa | Stiff polymer, not flexible |
| Hardness | Moderate-high | Resistant to scratching after full UV cure |
| Shrinkage (linear) | ~5-8% | Lower than original IP-Dip |
| Shrinkage behavior | Isotropic to slightly anisotropic | Can cause warping in large flat structures |
| Thermal stability | Up to ~150 C | Not suitable for high-temperature applications |

---

## Shrinkage: What It Means in Practice

A 5-8% linear shrinkage means that a structure designed to be 100 um tall will print at approximately 92-95 um. For most applications this is acceptable. For precision optical components, you must compensate by scaling your design up by the inverse shrinkage factor in DeScribe.

Shrinkage is highest in the Z (axial) direction because:
1. The structure builds up layer by layer, and each new layer contracts slightly as it cures
2. The axial voxel is larger, so more material per layer is undergoing shrinkage

Rule of thumb: if dimensional accuracy matters, print a test structure first and measure the actual dimensions before printing your final design.

---

## Developer Compatibility

| Solvent | Role | Notes |
|---|---|---|
| PGMEA (propylene glycol monomethyl ether acetate) | Primary developer | Dissolves uncured IP-Dip2 efficiently |
| IPA (isopropanol) | Rinse | Removes PGMEA residue; use after PGMEA step |
| MIBK | Alternative developer | Used in some protocols; less common |

Development time: typically 20 minutes in PGMEA, followed by 5 minutes in IPA.

> See **[08_Development_and_Post_Processing/development_solvents.md](../../08_Development_and_Post_Processing/development_solvents.md)** for full development protocol.

---

## Aging and Batch Variation

IP-Dip2 is sensitive to:

- **Age:** Older resist (near or past expiry) has increased polymerization threshold. Structures printed with aged resist may be underexposed at previously calibrated power settings.
- **Light exposure:** Even brief exposure to ambient light initiates partial polymerization, increasing viscosity and reducing sensitivity. Keep the vial covered at all times except when dispensing.
- **Temperature:** Storage at elevated temperature accelerates degradation. Always store at 2-8 C (refrigerated, not frozen).

If you suspect resist degradation, print a calibration array before committing to a full print job.

---

## Related Files

- [overview.md](./overview.md)
- [use_with_63x.md](./use_with_63x.md)
- [handling_and_storage.md](./handling_and_storage.md)
- [13_Key_Parameters_Reference/resist_properties_table.md](../../13_Key_Parameters_Reference/resist_properties_table.md)
- [08_Development_and_Post_Processing/development_solvents.md](../../08_Development_and_Post_Processing/development_solvents.md)