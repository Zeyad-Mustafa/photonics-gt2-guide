# Step 3 — Slice in DeScribe

> The slicing procedure is the same as Workflow A, but the parameters are different. The 25x objective has a larger voxel, so slice and hatch distances are larger — and print times are shorter for equivalent volumes.

---

## Procedure

Follow the same general procedure as Workflow A Step 3. The key differences are:

1. Set the **Objective** dropdown to **25x**.
2. Set the **Resist** dropdown to **IP-S**.
3. Use the parameters in the table below instead of the 63x parameters.
4. For galvo scan mode, confirm "Galvo" is selected as the scan mode (recommended for most 25x prints).
5. Press F5 to compile, review the preview animation, and verify estimated print time before exporting GWL.

---

## Recommended Starting Parameters for 25x + IP-S

| Parameter | Starting Value | Notes |
|---|---|---|
| Slice distance | 1.0 um | 25x axial voxel is ~1 um; use 0.7–1.0 um for solid layers |
| Hatch distance | 0.5 um | 25x lateral voxel is ~500 nm |
| Laser power | 25–40% | IP-S is less sensitive than IP-Dip2; start at 30% |
| Scan speed | 50,000–100,000 um/s (galvo) | Much faster than 63x; galvo mode enables high speed |
| Hatching strategy | Shell + Scaffold | Best for most structures |
| Scan mode | Galvo | Default for 25x; switch to piezo for precision features |

---

## Why Galvo Mode Is Preferred for the 25x

The 25x objective combined with IP-S is the best combination for fast large-area printing. In galvo mode, the 400 x 400 um scan field can be traversed at 100 mm/s. For structures that would take 4 hours in piezo mode, galvo mode often completes in 30–60 minutes.

The trade-off (~1–2 um positional accuracy in galvo mode) is acceptable for the vast majority of 25x applications, where feature sizes are already 2–10 um or larger.

---

## What Can Go Wrong

Same as Workflow A Step 3, plus:

| Problem | Cause | Fix |
|---|---|---|
| Galvo scan field exceeded | Structure > 400 um in XY | Use StageGoToX/Y stitching commands |
| Structure prints correctly but joins between stitched fields are visible | Stitching offset incorrect | Calibrate stitch offset in NanoWrite |
| IP-S structure has slightly larger dimensions than designed | IP-S shrinkage (~5%) less than expected compensation | Fine-tune scaling; IP-S is more predictable than IP-Dip2 |

---

## Related Files

- [step_04_prepare_ITO_substrate.md](./step_04_prepare_ITO_substrate.md)
- [06_Software_Workflow/DeScribe_Software/slicing_parameters.md](../../06_Software_Workflow/DeScribe_Software/slicing_parameters.md)
- [06_Software_Workflow/DeScribe_Software/stagegoTo_commands.md](../../06_Software_Workflow/DeScribe_Software/stagegoTo_commands.md)
- [09_Printing_Modes/galvo_scan_mode.md](../../09_Printing_Modes/galvo_scan_mode.md)
