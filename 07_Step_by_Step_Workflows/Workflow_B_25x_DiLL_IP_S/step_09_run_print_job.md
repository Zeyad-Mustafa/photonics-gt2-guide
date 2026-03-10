# Step 9 — Run the Print Job

> The print job execution for Workflow B is the same as Workflow A. The key difference is that galvo mode is used by default, making the print significantly faster for equivalent volumes.

---

## Procedure

Follow the pre-print checklist and procedure in [Workflow A / step_09_run_print_job.md](../Workflow_A_63x_DiLL_IP_Dip2/step_09_run_print_job.md).

Key differences for Workflow B:
- Galvo scan mode is active — the stage XY position does not move during a single scan field print; only the galvo mirrors move
- Print speed will be noticeably faster than the 63x
- If your structure uses stitching (multiple print fields), NanoWrite will automatically reposition the XY stage between fields using the StageGoToX/Y commands embedded in the job GWL

---

## Monitoring a Galvo Mode Print

In galvo mode, the camera image will update faster than in piezo mode because each layer is completed more quickly. The structure will appear to grow in height more visibly per unit time.

Watch for:
- Uniform layer-by-layer growth
- No visible cracking or delamination between layers
- Consistent brightness/opacity across the structure cross-section (inconsistent opacity may indicate power variation)

---

## Related Files

- [step_10_development.md](./step_10_development.md)
- [06_Software_Workflow/NanoWrite_Software/loading_gwl_job.md](../../06_Software_Workflow/NanoWrite_Software/loading_gwl_job.md)
- [09_Printing_Modes/galvo_scan_mode.md](../../09_Printing_Modes/galvo_scan_mode.md)
