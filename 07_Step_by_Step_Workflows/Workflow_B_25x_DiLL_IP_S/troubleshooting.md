# Troubleshooting — Workflow B (25x + IP-S)

> This file covers problems specific to the 25x objective and IP-S resist.

---

## Quick Diagnosis Table

| Symptom | Most Likely Cause | First Action |
|---|---|---|
| Interface not found | ITO side loaded wrong way up | Remove substrate; flip; reload |
| Poor resolution — features larger than expected | Adjustment ring not on Glyc position | Reinstall 25x with ring set to Glyc |
| Stitched fields misaligned | Stitch offset miscalibrated | Recalibrate stitch offset in NanoWrite |
| Structure has visible haze after development | Residual IP-S — under-developed | Re-develop in fresh PGMEA for 10 more minutes |
| Structure delaminated during development | IP-S did not adhere to ITO | Clean substrate again; add O2 plasma; reprint |
| Galvo scan lines visible on vertical surfaces | Hatch distance too large | Reduce hatch to 300–400 nm |
| Print time unexpectedly long | Solid fill mode instead of scaffold, or hatch too small | Check DeScribe settings; switch to Shell + Scaffold |
| Structure dimensions correct but surface rough | Scan speed too high for this hatch distance | Reduce scan speed by 20% |

---

## Problem: 25x Adjustment Ring Was Set Incorrectly

This is the most common mistake in Workflow B. If the adjustment ring was on the wrong position during the print, the voxel shape was distorted — typically elongated or with aberrated edges.

The structure may still be present after development, but dimensions will be off and surface quality will be poor. There is no fix after the fact — reslice and reprint with the ring correctly set to Glyc.

---

## Problem: Stitched Fields Have a Visible Seam

When printing structures larger than 400 x 400 um using multiple stitched galvo scan fields, a visible seam or step between fields indicates the stage repositioning offset is not calibrated correctly.

Fix:
1. Print a calibration structure (e.g., a flat grid spanning two fields) and measure the seam offset by SEM or optical microscopy.
2. Enter the measured offset into NanoWrite's stitch calibration (see your facility SOP).
3. Reprint.

---

## Related Files

- [11_Troubleshooting/structure_not_adhering.md](../../11_Troubleshooting/structure_not_adhering.md)
- [11_Troubleshooting/structure_washed_off.md](../../11_Troubleshooting/structure_washed_off.md)
- [11_Troubleshooting/overexposure_and_blooming.md](../../11_Troubleshooting/overexposure_and_blooming.md)
- [11_Troubleshooting/underexposure_and_voids.md](../../11_Troubleshooting/underexposure_and_voids.md)
- [03_Objectives/25x_objective/adjustment_ring_guide.md](../../03_Objectives/25x_objective/adjustment_ring_guide.md)
