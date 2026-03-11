# Underexposure and Voids

> Your structure has missing layers, internal voids, holes where there should be solid material, or features that are thinner and weaker than designed. These are signs of underexposure.

---

## What Is Underexposure

Polymerization requires the laser intensity at the focal point to exceed the threshold dose for the resist. If intensity is below this threshold — even slightly — the voxel does not polymerize. During development, unpolymerized resist dissolves, leaving gaps, holes, or entirely absent features.

Underexposure is the mirror image of overexposure: where overexposure produces features larger than designed, underexposure produces features smaller than designed or absent entirely.

---

## How to Recognize Underexposure

| Observation | Indicates |
|---|---|
| Structure partially present but with gaps or pinholes | Underexposure in specific regions |
| Features thinner than designed | Voxels smaller than expected |
| Top of structure missing but bottom intact | Power insufficient to reach upper layers (depth-dependent attenuation) |
| Entire structure absent after development | Severe underexposure — nothing polymerized |
| Structure present but mechanically fragile; collapses on touch | Partial polymerization — below gel point |
| Interior voids in a nominally solid structure | Hatch lines not overlapping — hatch distance too large |

---

## Distinguishing Underexposure from Other Failures

Before assuming underexposure, confirm the structure actually attempted to print:

1. Check NanoWrite logs — did the job complete normally with no errors?
2. Was Z = 0 found correctly? If interface detection set Z = 0 above the substrate, the print ran in empty resist above the substrate.
3. Was the resist applied and the drop in the correct shape?

If all of the above are correct and the structure is still missing or incomplete, proceed with the underexposure fixes below.

---

## Causes

**1. Laser power too low**

The dose delivered to the resist is below the polymerization threshold. The femtosecond pulse intensity at the focal point does not achieve two-photon absorption.

**2. Scan speed too high**

High scan speed reduces dwell time per voxel, reducing dose. Even if power is within range, speed above a certain threshold drops dose below the threshold.

**3. Hatch distance too large**

If the spacing between scan lines is larger than the voxel diameter, the lines do not overlap. Regions between scan lines receive zero dose and remain uncured. After development, these appear as narrow channels or pinholes running parallel to the scan direction.

**4. Slice distance too large**

If the Z step between layers is larger than the axial voxel size, adjacent layers do not overlap. A thin uncured gap remains between layers. This produces planar void planes running horizontal through the structure, visible as horizontal striations under optical microscopy.

**5. Objective front element dirty or partly blocked**

Dried resist, dust, or oil contamination on the objective front element reduces the laser power reaching the focal point and degrades beam quality. Even a slight contamination can shift the dose below the polymerization threshold at the margins of the process window.

**6. Laser not warmed up**

During the first 30–45 minutes of operation, laser output is not stable. Power may be lower than the dial setting suggests. Printing before warm-up is complete risks underexposure.

**7. Resist is old or improperly stored**

Some resists degrade over time, raising the effective polymerization threshold. A fresh bottle may require less power than an old one, but an expired or heat-damaged resist may behave unpredictably and require substantially more power.

---

## Fixes

### Fix 1 — Increase laser power

Increase by 5–10% increments. Print a calibration array. The process window for most IP-series resists at standard scan speeds is 10–30 percentage points wide — there is room to adjust.

Do not increase power all the way to the top of the process window in one step. Overshoot leads to overexposure and blooming.

### Fix 2 — Reduce scan speed

Reduce by 20% increments. Lower speed increases dwell time per voxel and raises dose. This is useful when power is already at the correct level but dose is marginal.

### Fix 3 — Reduce hatch distance

If the pattern of voids follows the scan line direction (long parallel channels), the hatch distance is too large. Reduce it by 30–50% in DeScribe and re-slice.

For the 25x: hatch distance should be no more than 60–70% of the voxel diameter (~300 nm for standard settings). For the 63x: no more than 200 nm.

### Fix 4 — Reduce slice distance

If voids are planar horizontal layers, slice distance is too large. Reduce by 30–50%. Axial voxel size for the 63x is approximately 1.0–1.5 um; slice distance should be at most 70% of this (~0.7 um or less at 63x).

### Fix 5 — Clean the objective

Wipe the objective front element with a PGMEA-dampened lens tissue, then IPA, then dry. Inspect under bright light. Retry with a fresh calibration print.

### Fix 6 — Wait for full laser warm-up

If you are printing within the first 45 minutes after startup, wait. Laser output power stabilizes only after the full warm-up period.

---

## Pattern-Specific Diagnosis

Use the pattern of voids to identify the cause:

| Pattern of voids | Likely cause |
|---|---|
| Random pinholes throughout | Borderline underexposure; increase power slightly |
| Regular parallel channels (horizontal in layer) | Hatch distance too large |
| Horizontal void planes (between layers) | Slice distance too large |
| Voids only in upper portion of structure | Depth-dependent attenuation; increase power or use higher-NA objective |
| Entire interior voided, only shell present | Severe underexposure or hatch pattern not covering interior |
| Structure completely absent | Extreme underexposure, interface detection error, or wrong substrate orientation |

---

## Related Files

- [overexposure_and_blooming.md](./overexposure_and_blooming.md)
- [interface_not_found.md](./interface_not_found.md)
- [13_Key_Parameters_Reference/scanning_speed_table.md](../13_Key_Parameters_Reference/scanning_speed_table.md)
- [06_Software_Workflow/DeScribe_Software/slicing_parameters.md](../06_Software_Workflow/DeScribe_Software/slicing_parameters.md)
