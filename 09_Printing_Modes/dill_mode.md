# DiLL Mode — Dip-In Laser Lithography

> DiLL is the primary printing mode for the GT2 and the one you will use for the vast majority of prints. Understanding exactly what happens at the objective tip during DiLL printing explains why certain rules — resist volume, substrate orientation, objective cleanliness — are non-negotiable.

---

## What DiLL Mode Is

In DiLL mode, the objective lens is inverted (pointing upward) and its front element is submerged **directly into the liquid photoresist**. The resist serves simultaneously as the printing medium and as the immersion medium for the objective.

```
        [ substrate ]          <- glass, silicon, ITO, quartz
        [  resist   ]          <- IP-Dip2, IP-S, IP-Q, etc. (liquid)
        [  resist   ]
        [  resist   ]
        [objective tip]        <- submerged in resist
              |
         laser beam
         (from below)
```

The laser focuses inside the resist volume. Because the objective tip is already inside the resist, there is no glass-resist interface between the objective and the focal point. The optical path is homogeneous from the objective front element up to the substrate surface.

---

## Why DiLL Exists

Before DiLL was developed, 2PP printing required the laser to travel through a cover glass before reaching the resist. This introduced two problems:

1. **Spherical aberration accumulation with depth** — as the focal point moved deeper into the resist, the difference in refractive index between glass and resist caused the focal spot to distort. Print quality degraded with depth.

2. **Working distance limitation** — the cover glass consumed much of the objective's working distance, limiting how tall a structure could be.

DiLL eliminates both problems. By immersing the objective directly in the resist:
- The optical path from objective to focal point is in a single medium (the resist)
- Spherical aberration due to glass-resist index mismatch is eliminated
- The full working distance of the objective is available within the resist volume

---

## Which Objectives Use DiLL

| Objective | DiLL Compatible | Notes |
|---|---|---|
| 63x (NA 1.4) | Yes | Primary DiLL objective for highest resolution |
| 25x (NA 0.8) | Yes | Most common DiLL objective; adjustment ring must be on Glyc |
| 10x (NA 0.3) | Yes | DiLL with IP-Q; uses Multi-DiLL Silicon Wafer Holder |
| 20x (air) | No | Air mode only; cannot be submerged |

---

## Which Resists Are Used in DiLL Mode

All IP-series and IPX-series resists are designed for DiLL mode:

| Resist | Primary Objective | n at 780 nm |
|---|---|---|
| IP-Dip2 | 63x | 1.511 |
| IP-S | 25x | 1.478 |
| IP-Visio | 25x | ~1.48 |
| IP-PDMS | 25x | ~1.41 |
| IP-Q | 10x | 1.48 |
| IPX-Q | 10x / 25x | ~1.48 |
| IPX-Clear | 10x / 25x / 63x | ~1.50 |
| GP-Silica | 25x / 63x | ~1.45 (composite) |

---

## The DiLL Optical Path in Detail

When printing in DiLL mode, the laser travels along this path:

```
Femtosecond laser
      |
Galvo mirrors (if galvo mode)
      |
Scan lens + tube lens
      |
Objective front element (submerged in resist)
      |
Resist volume (homogeneous medium)
      |
FOCAL POINT (voxel forms here)
      |
More resist volume
      |
Substrate surface (Z = 0, detected by interface finder)
```

The focal point can be positioned anywhere within the resist volume, from just above the substrate (Z = +0.1 um) to the full working distance of the objective (e.g., 380 um for the 25x). Structures are built by scanning the focal point in X, Y, and Z to trace out every voxel.

---

## Interface Detection in DiLL Mode

Before printing, the GT2 must locate the substrate surface (Z = 0). In DiLL mode, this is done with the objective already submerged in resist:

1. The laser is set to a power level well below the polymerization threshold.
2. The system scans the objective upward in Z, monitoring reflected light intensity.
3. When the focal point crosses the resist-substrate interface, reflected intensity changes due to the refractive index step (delta-n).
4. This Z position is recorded as Z = 0.

For DiLL to work reliably, delta-n between resist and substrate must be at least 0.04. See [05_Substrates/interface_detection_requirements.md](../05_Substrates/interface_detection_requirements.md).

---

## Practical Rules for DiLL Mode

**Keep the objective tip clean.** Any dried resist on the front element distorts the beam and degrades focus. Clean after every print session.

**Apply resist immediately before printing.** Liquid resists exposed to ambient light for extended periods partially pre-polymerize. Apply resist, load the holder, and start printing within 30 minutes.

**Do not run out of resist mid-print.** If the resist volume is insufficient and the objective tip becomes exposed to air during a print, the optical path is disrupted immediately and the structure is ruined. Apply enough resist to keep the objective submerged throughout the job.

**Check the resist drop for bubbles.** An air bubble in the resist volume directly above or below the focal point scatters the laser and creates a void in the structure. Remove bubbles before loading (see [07_Step_by_Step_Workflows/Workflow_A_63x_DiLL_IP_Dip2/step_05_apply_resist.md](../07_Step_by_Step_Workflows/Workflow_A_63x_DiLL_IP_Dip2/step_05_apply_resist.md)).

---

## DiLL vs. Oil Immersion Mode

DiLL and oil immersion both involve liquid between the objective and the sample, but they are different configurations:

| Feature | DiLL Mode | Oil Immersion Mode |
|---|---|---|
| Objective submerged in | Photoresist (the printing medium) | Immersion oil (inert, not the printing medium) |
| Resist location | Between objective tip and substrate | On top of the substrate |
| Substrate | Resist is the immersion medium — no oil needed | 170 um glass coverslip with oil below, resist above |
| Objective | 10x, 25x, or 63x | 63x only |
| Depth limit | Full objective working distance | ~1 mm from substrate into resist |

See [oil_immersion_mode.md](./oil_immersion_mode.md) for the oil immersion configuration.

---

## Related Files

- [oil_immersion_mode.md](./oil_immersion_mode.md)
- [02_Machine_Components/sample_holder_types.md](../02_Machine_Components/sample_holder_types.md)
- [05_Substrates/interface_detection_requirements.md](../05_Substrates/interface_detection_requirements.md)
- [03_Objectives/25x_objective/dill_mode_explained.md](../03_Objectives/25x_objective/dill_mode_explained.md)
- [07_Step_by_Step_Workflows/README.md](../07_Step_by_Step_Workflows/README.md)
