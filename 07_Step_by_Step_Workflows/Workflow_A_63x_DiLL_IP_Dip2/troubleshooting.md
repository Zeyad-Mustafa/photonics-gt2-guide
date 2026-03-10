# Troubleshooting — Workflow A (63x + IP-Dip2)

> This file covers problems specific to the 63x objective and IP-Dip2 resist. For machine-level errors (SPS faults, stage errors), see [11_Troubleshooting/](../../11_Troubleshooting/README.md).

---

## Quick Diagnosis Table

| Symptom | Most Likely Cause | First Action |
|---|---|---|
| No structure visible after development | Underexposure or interface not found | Increase laser power 20%; verify interface detection |
| Structure is present but much smaller than designed | IP-Dip2 shrinkage | Scale model by 1.10–1.15x and reprint |
| Structure washed off during development | Poor substrate adhesion | Add oxygen plasma step; reprint |
| Thin features collapsed | Capillary forces during drying | Dry faster; redesign with thicker features |
| Surface is rough or has layer lines visible | Hatch distance too large | Reduce hatch to 200–250 nm and reprint |
| Structure has voids or gaps in interior | Slice distance too large | Reduce to 400–500 nm and reprint |
| Structure is overexposed — swollen, bloomed edges | Laser power too high | Reduce power by 10–15% and reprint |
| Interface not found | Delta-n too low or wrong substrate side | Check substrate orientation; switch to quartz |
| Objective crashed into substrate | Exchange Holder dialog not used | Always use dialog; check objective for damage |
| Resist wicked into objective housing | Fiber ring missing or damaged | Replace fiber ring; clean objective |

---

## Problem: Structure Is Smaller Than Designed

IP-Dip2 shrinks approximately 10–15% during polymerization and post-cure. This is expected behavior, not a defect.

To compensate:
1. In DeScribe, use the Scale function to increase all dimensions by 1.10 to 1.15 (10–15%).
2. Do not scale the Z-origin offset — only scale the structure geometry.
3. After the compensated print, measure the actual dimensions by SEM and calculate your specific shrinkage factor (it may differ from 10–15% depending on your laser power and hatch settings).
4. Use that measured factor for all subsequent prints with the same parameters.

---

## Problem: Structure Washes Off During Development

This indicates insufficient adhesion at the substrate interface.

Diagnostic questions:
- Was the substrate cleaned immediately before printing? (Cleaned > 1 hour before printing may have recontaminated)
- Was oxygen plasma treatment performed? (Strongly recommended for 63x + IP-Dip2 on glass)
- Was the first printed layer at exactly Z = 0 (substrate surface)? If interface detection placed Z = 0 above the actual surface, the first layers printed in air or in liquid and never contacted the substrate.

Fixes:
1. Re-clean the substrate (acetone > IPA > DI water > N2 dry).
2. Perform a 2-minute oxygen plasma treatment immediately before applying resist.
3. Verify interface detection: the Z = 0 value should correspond to the substrate surface, not the bottom of the resist drop.
4. If still failing, try adding an adhesion promoter — consult your facility SOP.

---

## Problem: Thin Features Collapsed After Development

Capillary forces during drying are the primary cause of thin feature collapse. When the IPA on the surface evaporates, the liquid-air interface exerts lateral force on thin pillars and walls.

Fixes in order of increasing complexity:
1. Dry the substrate faster — use a stronger N2 flow to quickly remove all IPA before capillary forces build.
2. Redesign features with a larger minimum diameter (> 3 um for pillars, > 1.5 um for walls).
3. Use critical point drying (CPD) if your facility has a critical point dryer — this eliminates the liquid-air interface entirely and prevents capillary force.
4. Add support structures to tall thin features in your CAD design.

---

## Problem: Poor Surface Quality (Visible Layers or Rough Surface)

Possible causes and fixes:

| Specific Symptom | Cause | Fix |
|---|---|---|
| Horizontal layer lines visible on vertical surfaces | Slice distance too large | Reduce slice distance to 300–400 nm |
| Rough surface texture on top face | Hatch distance too large | Reduce hatch to 200 nm |
| Wavy or irregular surface | Galvo scan used for high-resolution feature | Switch to piezo mode |
| Speckled surface texture | Laser power too high causing local over-curing | Reduce laser power by 10% |

---

## Related Files

- [11_Troubleshooting/structure_not_adhering.md](../../11_Troubleshooting/structure_not_adhering.md)
- [11_Troubleshooting/structure_washed_off.md](../../11_Troubleshooting/structure_washed_off.md)
- [11_Troubleshooting/thin_features_collapsing.md](../../11_Troubleshooting/thin_features_collapsing.md)
- [11_Troubleshooting/overexposure_and_blooming.md](../../11_Troubleshooting/overexposure_and_blooming.md)
- [11_Troubleshooting/underexposure_and_voids.md](../../11_Troubleshooting/underexposure_and_voids.md)
- [11_Troubleshooting/interface_not_found.md](../../11_Troubleshooting/interface_not_found.md)
- [11_Troubleshooting/objective_crashing.md](../../11_Troubleshooting/objective_crashing.md)
