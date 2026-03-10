# NanoWrite Software — Section Overview

## What NanoWrite Does

NanoWrite is Nanoscribe's machine control software. It runs on the computer physically attached to the GT2 and communicates directly with all machine hardware: the laser, the piezo stage, the galvo mirrors, the coarse XY stage, and the safety interlock system (SPS).

NanoWrite is responsible for:
- Laser warm-up and power monitoring
- Sample approach and interface detection
- Loading and executing GWL job files
- Real-time monitoring during printing
- Safety interlock management

NanoWrite does not design structures or generate toolpaths — that is DeScribe's job. NanoWrite only executes what DeScribe has already prepared.

---

## Files in This Subfolder

| File | Contents |
|---|---|
| startup_procedure.md | Power-on sequence, 45-minute warm-up, pre-print checklist |
| exchange_holder_dialog.md | Safe sample loading and unloading using the exchange dialog |
| sample_approach.md | Approach procedure, interface finder, Z = 0 definition |
| loading_gwl_job.md | Opening a job file, confirming settings, starting the print |
| monitoring_print.md | What to watch on the camera feed, detecting problems in progress |
| estimating_print_time.md | Reading and interpreting print time before committing |
| shutdown_procedure.md | Correct power-down sequence at end of session |

---

After NanoWrite, proceed to Section 07 — Step by Step Workflows, which walks through complete end-to-end print sessions using all software tools together.
