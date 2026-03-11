# Overexposure and Blooming

> Your structure printed, but it is larger than the CAD model, features are fused together, fine gaps are filled in, or the surface looks rough and grainy. These are all signs of overexposure.

---

## What Is Overexposure

Two-photon polymerization occurs when the local laser intensity exceeds the polymerization threshold. Overexposure happens when the dose delivered to the resist is higher than needed to just polymerize the voxel — the polymerized region grows beyond the intended voxel boundary.

This is called "blooming" because the polymerized zone expands outward from the scan path like a bloom. In 3D, an overexposed structure looks like every feature has been inflated slightly — dimensions are larger than designed, gaps between features are narrower than designed, and fine features may be fused.

---

## How to Recognize Overexposure

| Observation | Indicates |
|---|---|
| Structure dimensions larger than CAD by 5–30% | Overexposure |
| Designed gaps (e.g., 2 um slot) are partially or fully filled | Overexposure — voxels from adjacent scan lines merged across the gap |
| Surface texture is rough, granular, or "cauliflower-like" | Severe overexposure — voxel halos visible |
| Structure is darker / more yellow-brown than usual | Thermal effects from very high dose |
| Fine pillars are thicker than designed | Overexposure radially |
| Overhangs and cantilevers are sagging or drooping | Gravity + over-softened polymer, or print-through below the bottom surface |

---

## Causes

**1. Laser power too high**

The most direct cause. If power is set above the process window for the resist-objective combination, every voxel is overexposed.

**2. Scan speed too low**

Lower scan speed means the laser dwells longer at each point, increasing dose. Power and scan speed interact — what matters is the dose (power x dwell time per voxel), not power or speed individually.

**3. Slice distance too small**

Overlapping layers are normal and necessary, but if slice distance is much less than the axial voxel size, adjacent layers reinforce each other excessively and the structure grows in Z beyond the CAD dimensions.

**4. Laser warm-up incomplete**

In the first 20–30 minutes of operation, laser power output is not stable. Prints started before the 45-minute warm-up is complete may receive inconsistent dose, with some regions receiving more than intended.

**5. Resist pre-polymerization**

Resist exposed to ambient light before printing, or stored incorrectly, may have partially polymerized. This lowers the effective polymerization threshold — less dose is needed to cure it, so the existing power setting overexposes.

---

## Fixes

### Fix 1 — Reduce laser power

In DeScribe, reduce the laser power setting by 10–20% increments. Print a calibration structure (power sweep array) to find the correct power range before reprinting the full job.

The process window for IP-Dip2 at 63x is typically 15–35% laser power at 10,000–50,000 um/s. For IP-S at 25x: 20–40% at 50,000–100,000 um/s. These are starting ranges — your facility's system may differ.

### Fix 2 — Increase scan speed

If reducing power alone brings structure dimensions to the correct range but surface quality suffers, try a combination of slightly higher power and faster scan speed. Faster scanning can produce smoother surfaces at equivalent dose.

Increase scan speed in 25% steps and evaluate the calibration structure.

### Fix 3 — Increase slice distance

If Z dimensions are consistently larger than designed, increase the slice distance. The axial voxel size for 63x is approximately 1.0–1.5 um. Slice distances smaller than 0.5 um produce excessive layer overlap at standard power settings.

### Fix 4 — Ensure 45-minute laser warm-up is complete**

Always wait for the full 45-minute warm-up before printing. Do not start a job based on a warm-up that "seemed close enough." See [06_Software_Workflow/NanoWrite_Software/startup_procedure.md](../06_Software_Workflow/NanoWrite_Software/startup_procedure.md).

### Fix 5 — Use fresh resist from proper storage**

If the resist has been stored at room temperature for more than a week, or if the bottle has been left open or in ambient light, discard it and open a fresh bottle. Store IP-series resists at 4–8 degrees C in dark conditions.

---

## Calibration Structure

The most efficient way to find the correct parameters is to print a power sweep array: a grid of identical test structures (e.g., 10 x 10 um squares or sets of parallel lines) printed at different power levels. Examine under SEM or optical microscope and identify the power at which the structures match the CAD dimensions. Then use that power for the full print.

---

## What Can Go Wrong

| After fix | Possible cause | Next step |
|---|---|---|
| Power reduced but still overexposed | Resist is pre-polymerized | Use fresh resist |
| Reducing power causes underexposure before reaching correct size | Process window is very narrow | Try changing resist lot or adjusting scan speed |
| Outer surfaces correct, interior still overexposed | Interior hatch pattern too dense | Increase hatch distance or use scaffold printing |

---

## Related Files

- [underexposure_and_voids.md](./underexposure_and_voids.md)
- [13_Key_Parameters_Reference/scanning_speed_table.md](../13_Key_Parameters_Reference/scanning_speed_table.md)
- [04_Resists_and_Materials/IP_Dip2/handling_and_storage.md](../04_Resists_and_Materials/IP_Dip2/handling_and_storage.md)
- [06_Software_Workflow/NanoWrite_Software/startup_procedure.md](../06_Software_Workflow/NanoWrite_Software/startup_procedure.md)
