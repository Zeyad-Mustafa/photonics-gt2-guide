# ⚛️ Section 01 — Physics and Principles

> **Learning Objective:** After reading this section, you will understand the science behind Two-Photon Polymerization well enough to make informed decisions about laser power, scan speed, voxel size, and material choice — without needing a physics degree.

---

## Why Learn the Physics?

You don't need to be a physicist to use the GT2. But understanding *why* it works the way it does will help you:
- Troubleshoot failed prints faster
- Choose the right parameters the first time
- Understand why certain resists work with certain objectives
- Predict how features will look before you print them

---

## Files in This Section

| File | What You'll Learn |
|---|---|
| [light_and_photons_basics.md](light_and_photons_basics.md) | What light is, what a photon is, wavelength vs energy |
| [one_photon_vs_two_photon_absorption.md](one_photon_vs_two_photon_absorption.md) | Why 2PP achieves resolution impossible with regular UV light |
| [femtosecond_laser_explained.md](femtosecond_laser_explained.md) | Why the laser must be ultrafast and near-infrared |
| [voxel_formation.md](voxel_formation.md) | How the focal point becomes a 3D voxel, aspect ratio, size control |
| [diffraction_limit_and_beyond.md](diffraction_limit_and_beyond.md) | The physical limit of optics — and how 2PP breaks it |
| [polymerization_chemistry.md](polymerization_chemistry.md) | What happens chemically when the resin solidifies |

---

## Recommended Reading Order

```
light_and_photons_basics
        ↓
one_photon_vs_two_photon_absorption
        ↓
femtosecond_laser_explained
        ↓
voxel_formation
        ↓
diffraction_limit_and_beyond
        ↓
polymerization_chemistry
```

---

## Key Physics Numbers to Keep in Mind

| Parameter | Value | Why It Matters |
|---|---|---|
| Laser wavelength | 780 nm | NIR — transparent to resin until 2-photon threshold |
| Pulse duration | 100 femtoseconds | Achieves extreme peak intensity at focal point |
| Repetition rate | 80 MHz | 80 million pulses per second — appears continuous |
| Minimum voxel width | ~160 nm | Lateral resolution limit with 63× objective |
| Minimum voxel height | ~500 nm | Axial resolution limit (always worse than lateral) |
| Diffraction limit (780 nm) | ~390 nm | 2PP achieves features BELOW this limit |

---

> 🔗 After this section → **[02_Machine_Components](../02_Machine_Components/README.md)**