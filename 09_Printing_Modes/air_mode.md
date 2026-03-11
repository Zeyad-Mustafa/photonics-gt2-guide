# Air Mode

> Air mode is the only printing configuration on the GT2 that does not use any liquid between the objective and the substrate. It is used exclusively with the 20x air objective for 2D and pseudo-3D patterning of spin-coated photoresists.

---

## What Air Mode Is

In air mode, the 20x objective focuses through an **air gap** onto a **spin-coated resist layer** on the substrate surface. There is no immersion oil, no liquid resist drop, and no objective submersion.

```
        [ spin-coated resist ]    <- thin uniform layer, typically 1–10 um
        [    substrate       ]    <- silicon wafer or glass
              ↑ air gap
        [  20x objective     ]    <- working distance: ~1.2 mm
              |
         laser beam
         (from below)
```

The resist layer is applied before loading — it is not a liquid drop but a cured (pre-baked) polymer film that has been spin-coated and soft-baked onto the substrate. The GT2 laser exposes this layer via 2-photon absorption, just as in DiLL mode, but the optical configuration is completely different.

---

## The 20x Objective

The 20x is an **air (dry) objective** with NA 0.5 and a working distance of approximately 1.2 mm. It is not designed for liquid immersion. Submerging it in resist or oil would damage it.

| Parameter | Value |
|---|---|
| Magnification | 20x |
| Numerical aperture | 0.5 |
| Working distance | ~1.2 mm |
| Immersion medium | Air (dry) |
| Lateral voxel (typical) | ~1–2 um |
| Axial voxel (typical) | ~5–10 um |

The lower NA compared to the 25x (NA 0.8) or 63x (NA 1.4) means larger voxels and lower resolution. Air mode is not the right choice when high 3D resolution is needed — its advantage is compatibility with standard spin-coated photoresists and large-area flat-surface patterning.

---

## Compatible Resists

Air mode is used with **standard i-line photoresists** — the same resists used in conventional UV photolithography. These include:

- SU-8 (negative tone epoxy resist — widely used for microfluidic molds)
- AZ series positive-tone resists
- MicroChem PMMA
- Other spin-coatable photopolymers compatible with 365–405 nm exposure

Note: these resists respond to 2-photon absorption at 780 nm, but they were not designed for it. The exposure parameters (power, scan speed) must be calibrated carefully — the process window may be narrow compared to IP-series resists.

Do not use IP-series resists in air mode. IP-Dip2, IP-S, IP-Q, etc. are formulated for DiLL and require objective submersion for proper optical contact.

---

## What Structures Can Air Mode Produce

Air mode is fundamentally limited in Z depth by the resist film thickness. Spin-coated layers are typically 1–20 um thick.

| Structure Type | Feasibility in Air Mode |
|---|---|
| 2D planar patterns (flat features) | Yes — primary use case |
| Pseudo-3D (multilayer flat exposures) | Yes — possible with multiple exposure and development cycles |
| True freeform 3D | Limited — voxel size and layer thickness constraints |
| Sub-1 um features | No — NA 0.5 limits lateral resolution to ~1 um |
| Tall structures (> 20 um) | No — resist film thickness is the hard limit |

For most applications requiring true 3D printing, use DiLL mode with the 25x or 63x. Air mode is the right choice when:
- You need to pattern a standard photoresist alongside conventional UV lithography processes
- You are making microfluidic mold masters in SU-8
- Your substrate already has a spin-coated film and you need to expose it selectively

---

## Sample Holder for Air Mode

Air mode typically uses the **5-inch Mask Holder** (for wafer-scale substrates) or the **Universal Sample Holder** (for smaller chips). The substrate is loaded with the resist-coated surface facing the objective (downward, since this is an inverted microscope).

Because the resist is a solid film rather than a liquid drop, the loading orientation rules are the same as for other modes — printing surface faces the objective — but there is no risk of the resist shifting during loading.

---

## Interface Detection in Air Mode

Interface detection in air mode locates the top surface of the substrate (or the top surface of any hard layer beneath the resist). The air-resist interface has a delta-n of approximately 0.5 (air n = 1.0, resist n ~ 1.5), producing a very strong reflection signal. Interface detection is highly reliable in this configuration.

---

## Laser Power Considerations

Air mode with i-line resists requires careful power calibration. These resists were not designed for 2PP exposure:

- Too little power: no polymerization
- Too much power: over-exposure, blown features, thermal damage
- The process window (correct power range) is narrower than for IP-series resists

Start with very low power (10–15%) and make a power calibration test array before committing to a full print.

---

## Limitations of Air Mode

| Limitation | Detail |
|---|---|
| 2D/pseudo-3D only | Z range limited by resist film thickness (typically < 20 um) |
| Lower resolution than DiLL | NA 0.5 vs. NA 0.8 (25x) or NA 1.4 (63x) |
| Narrow process window | i-line resists not optimized for 780 nm 2PP exposure |
| No freeform 3D | Cannot print overhangs or complex 3D geometries |
| Objective cannot be used in DiLL | Air objective must not contact liquid |

---

## Related Files

- [dill_mode.md](./dill_mode.md)
- [inverted_immersion_mode.md](./inverted_immersion_mode.md)
- [03_Objectives/20x_objective/overview.md](../03_Objectives/20x_objective/overview.md)
- [03_Objectives/20x_objective/limitations.md](../03_Objectives/20x_objective/limitations.md)
- [04_Resists_and_Materials/i_line_photoresists/overview.md](../04_Resists_and_Materials/i_line_photoresists/overview.md)
- [04_Resists_and_Materials/i_line_photoresists/spin_coating_guide.md](../04_Resists_and_Materials/i_line_photoresists/spin_coating_guide.md)
