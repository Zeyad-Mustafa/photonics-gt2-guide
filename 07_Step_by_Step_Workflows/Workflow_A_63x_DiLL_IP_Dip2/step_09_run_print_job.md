# Step 9 — Run the Print Job

> This is the step where the machine does the work. Your role is to load the job, confirm the estimated time, start it, and monitor it. Do not leave the machine unattended during your first several prints.

---

## Why This Step Matters

Starting the print job commits the machine to executing every laser movement in the GWL file. Once started, the job cannot be paused (in most configurations) — it either completes or is aborted. An aborted print means a wasted substrate, wasted resist, and time lost. Verify everything before clicking Start.

---

## Pre-Print Checklist

Before starting the job, confirm each item:

- [ ] Laser has completed its 45-minute warm-up
- [ ] Interface detection completed successfully (Z = 0 is set)
- [ ] GWL job file loaded in NanoWrite
- [ ] Estimated print time reviewed and accepted
- [ ] Laser power settings match your DeScribe parameters
- [ ] Scan mode (piezo or galvo) matches your DeScribe settings
- [ ] SPS green Process light is illuminated
- [ ] Top hatch is closed

If any item is unchecked, resolve it before proceeding.

---

## Procedure

1. In NanoWrite, go to File > Load Job (or equivalent) and navigate to your `_job.gwl` file. Both the `_job.gwl` and `_data.gwl` must be in the same folder.
2. NanoWrite will parse the job file and display a summary including estimated print time. Read this carefully.
3. If the estimated time is unexpectedly long (hours when you expected minutes), go back and check your DeScribe parameters. It is faster to re-slice than to waste hours on a misconfigured job.
4. Confirm the print origin position in NanoWrite: this is where the center of your structure will be located on the substrate. Use the stage XY controls to position the origin over the desired area (center of resist drop, free of surface defects).
5. Click "Start Job."
6. The machine will begin printing. On the AxioVision camera, you will see the structure begin to grow — increased opacity or scattering in the resist where layers have been written.
7. Monitor the print for the first few minutes. Signs of a problem:
   - No visible change in the resist after several minutes (possible underexposure or beam path issue)
   - Visible cracking or collapse (overexposure, or poor substrate adhesion)
   - NanoWrite error dialog (read the message and respond accordingly)
8. Once confident the print is proceeding correctly, you may monitor less frequently. Return to the machine periodically — do not leave the building during a long print.
9. When the job completes, NanoWrite will display "Job Complete" and the stage will move to a rest position.
10. Do not immediately remove the sample. Proceed to Step 10 (Development).

---

## Estimating Print Time

NanoWrite and DeScribe both show an estimated print time after the GWL is compiled and loaded. Factors that increase print time:

- Smaller slice distance (more layers)
- Smaller hatch distance (more scan lines per layer)
- Solid fill strategy instead of scaffold
- Piezo mode (slower than galvo for equivalent volume)
- Large structure volume

A 100 x 100 x 100 um cube with 0.5 um slices and 0.3 um hatch in solid fill mode with the 63x in piezo mode can take 1–4 hours. Plan accordingly.

---

## What Can Go Wrong

| Problem | Cause | Fix |
|---|---|---|
| No visible structure forming in camera | Laser power too low, or GWL loaded incorrectly | Abort job; check laser enable and power settings; reload GWL |
| NanoWrite reports "Out of Range" error | Structure coordinates exceed piezo range | Re-slice in DeScribe with smaller dimensions or switch to galvo |
| SPS safe state error mid-print | Interlock violation (hatch opened, power interruption) | See [11_Troubleshooting/sps_safe_state_error.md](../../11_Troubleshooting/sps_safe_state_error.md) |
| Print completes but structure is in wrong location | Print origin was not set correctly | Re-approach, re-set origin, reprint on fresh area |
| Resist bubbles visible growing during print | Laser power too high — thermal damage | Abort; reduce laser power by 10–20%; reprint |

---

## Related Files

- [step_08_find_interface.md](./step_08_find_interface.md)
- [step_10_development.md](./step_10_development.md)
- [06_Software_Workflow/NanoWrite_Software/loading_gwl_job.md](../../06_Software_Workflow/NanoWrite_Software/loading_gwl_job.md)
- [06_Software_Workflow/NanoWrite_Software/monitoring_print.md](../../06_Software_Workflow/NanoWrite_Software/monitoring_print.md)
- [06_Software_Workflow/NanoWrite_Software/estimating_print_time.md](../../06_Software_Workflow/NanoWrite_Software/estimating_print_time.md)
