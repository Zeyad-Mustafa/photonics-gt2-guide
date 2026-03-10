# Print Steps — Workflow D (GP-Silica)

> The printing procedure for GP-Silica is similar to standard DiLL workflows but with modifications to account for the resist's particle suspension, the 8-hour time limit, and the higher laser power requirements.

---

## Before You Begin

Confirm all items from [special_requirements.md](./special_requirements.md):
- [ ] Furnace access confirmed and sintering scheduled
- [ ] Design scaled up by 1.35x to compensate for sintering shrinkage
- [ ] Laser has completed 45-minute warm-up BEFORE resist application
- [ ] Total estimated print time is under 6 hours (to leave 2-hour margin within the 8-hour limit)
- [ ] Compatible substrate (fused silica or platinum foil) is cleaned and ready

---

## Objective Selection for GP-Silica

GP-Silica is compatible with both the 25x and 63x objectives. Choose based on feature size:

| Objective | Use When |
|---|---|
| 25x | Features > 1 um; structure size up to 1 mm; faster print |
| 63x | Features < 1 um; highest-resolution glass structures |

For most GP-Silica applications (micro-optics, microfluidic glass chips, glass scaffolds), the 25x is the more practical choice.

---

## Slicing Parameters for GP-Silica in DeScribe

GP-Silica requires higher laser power than organic resists because the silica particles scatter light.

| Parameter | Value for 25x + GP-Silica | Value for 63x + GP-Silica |
|---|---|---|
| Slice distance | 0.8–1.0 um | 0.4–0.5 um |
| Hatch distance | 0.4–0.6 um | 0.2–0.3 um |
| Laser power | 40–60% | 30–50% |
| Scan speed | 30,000–70,000 um/s | 10,000–30,000 um/s |
| Strategy | Shell + Scaffold | Shell + Scaffold |
| Scale factor | 1.35x applied in DeScribe | 1.35x applied in DeScribe |

These are starting values. GP-Silica parameter optimization typically requires 2–3 test prints to find the correct exposure dose for your specific structure and objective.

---

## Procedure

1. Complete laser warm-up before this step.
2. Clean the substrate (fused silica or platinum foil) per [05_Substrates/substrate_cleaning_procedure.md](../../05_Substrates/substrate_cleaning_procedure.md).
3. Apply GP-Silica resist. GP-Silica is a thick, slightly opaque suspension (it looks slightly cloudy, not fully clear like IP-Dip2 or IP-S). Apply 1–2 drops to the substrate surface. The suspension must be homogeneous — if particles have settled, gently roll the bottle to resuspend before use. Do not shake vigorously.
4. Note the time. The 8-hour clock starts now.
5. Load the sample holder into the stage using the Exchange Holder dialog.
6. In NanoWrite, run the sample approach and interface detection. The opaque nature of GP-Silica means the camera image will be slightly hazier than with transparent resists — interference fringes will still appear but may be less sharp.
7. Load the GWL job file.
8. Confirm estimated print time. If it exceeds 6 hours, abort — do not start.
9. Start the print job and monitor.
10. After the job completes, remove the sample promptly. Do not leave GP-Silica-coated samples in the machine.
11. Develop immediately (see development below) or within 30 minutes.

---

## Development for GP-Silica

GP-Silica development uses **PGMEA** to remove the uncured binder and particles, followed by IPA:

1. Submerge in PGMEA for **20–30 minutes** with gentle agitation.
2. Transfer to IPA for 5 minutes.
3. Dry with N2.

After development, what remains is a fragile **polymer-silica composite structure**. Handle with extreme care — it is much more brittle than a fully organic resist print.

Inspect under optical microscope. The structure should appear slightly translucent and whitish/gray (the silica particles scatter light).

---

## What Can Go Wrong

| Problem | Cause | Fix |
|---|---|---|
| Structure does not form | Laser power too low for GP-Silica | Increase power by 10–15%; reslice and reprint |
| Structure is porous or crumbles | Underexposure — particles not fully bound | Increase laser power; reduce scan speed |
| Structure fractures during development | Fragile composite — development too aggressive | Reduce agitation; develop more gently |
| Print quality degrades mid-job | Approaching or past 8-hour limit | Abort; apply fresh resist; reprint |

---

## Related Files

- [post_processing.md](./post_processing.md)
- [special_requirements.md](./special_requirements.md)
- [04_Resists_and_Materials/GP_Silica/workflow_special_steps.md](../../04_Resists_and_Materials/GP_Silica/workflow_special_steps.md)
- [11_Troubleshooting/gp_silica_print_timeout.md](../../11_Troubleshooting/gp_silica_print_timeout.md)
