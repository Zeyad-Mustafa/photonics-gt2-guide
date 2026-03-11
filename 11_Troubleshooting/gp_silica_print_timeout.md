# GP-Silica Print Timeout

> Your GP-Silica print ran past the 8-hour resist lifetime window, or you are planning a print that will exceed it. This file explains what happens when GP-Silica ages past its lifetime and how to manage the timing.

---

## The 8-Hour Limit

GP-Silica is a suspension of silica nanoparticles in a photopolymer carrier. Unlike IP-series resists, which are stable for days or weeks after application (if protected from light), GP-Silica begins to settle and separate as soon as it is applied to the substrate.

The 8-hour window is the time from when GP-Silica is applied to the substrate until when the structure must be fully printed and ready for development. After 8 hours:

- The nanoparticle suspension becomes inhomogeneous — particles settle toward the bottom of the drop, leaving the upper portion depleted
- The photopolymer carrier may partially pre-polymerize from ambient light exposure (if not in darkness)
- The print quality degrades in the upper layers: lower particle density means the sintered glass will be porous or non-uniform

A structure printed partly in fresh GP-Silica and partly in aged GP-Silica will have visible variation in sintered density — and may crack during sintering at the boundary.

---

## What Happens If You Exceed 8 Hours

| Time past 8 hours | Expected effect |
|---|---|
| 0–30 min over | Mild — upper layer particle density slightly low; sintering may show slight porosity |
| 30 min – 2 hours over | Moderate — visible stratification in the brown body after debinding; crack risk during sintering |
| > 2 hours over | Severe — print is unusable for glass applications; discard and restart |

If you suspect the resist was past its lifetime during printing, do not proceed to debinding and sintering — the brown body may crack in the furnace, wasting furnace time and potentially contaminating the furnace.

---

## Planning a Print Within the 8-Hour Window

The 8-hour clock starts when GP-Silica is applied to the substrate, not when the laser starts. Plan your time accordingly:

```
Time budget for a GP-Silica print session:

00:00 — Machine startup (begin here if machine is cold)
00:45 — Laser warm-up complete
00:50 — Substrate preparation complete
01:00 — GP-Silica applied to substrate (8-hour clock starts)
01:05 — Sample loaded, interface detection complete
01:10 — Print job starts
...print runs for N hours...
09:00 — 8-hour limit reached (print must be done by this time)
```

This means a structure that takes more than approximately 7 hours to print cannot be safely done in a single GP-Silica session.

---

## Checking Print Time Estimate Before Applying Resist

**Always estimate print time in DeScribe before applying GP-Silica to the substrate.**

1. Import your STL into DeScribe.
2. Set parameters appropriate for GP-Silica (see [07_Step_by_Step_Workflows/Workflow_D_Glass_Structures_GP_Silica/print_steps.md](../07_Step_by_Step_Workflows/Workflow_D_Glass_Structures_GP_Silica/print_steps.md)).
3. Slice and check the time estimate.
4. If the estimate exceeds 6 hours, apply the fixes below before applying resist.
5. Only when the estimate is within the 8-hour window should you apply GP-Silica to the substrate.

Do not apply GP-Silica, start the machine, and discover the print will take 12 hours. At that point you have no good options.

---

## Fixes for Long GP-Silica Print Times

### Fix 1 — Use scaffold or shell printing

GP-Silica structures intended for sintering are often solid — they need to survive the thermal cycle as a "brown body." However, a well-designed shell (4–6 um thick) with an internal scaffold is mechanically viable for debinding and sintering and reduces print volume by 50–80%.

Consult [07_Step_by_Step_Workflows/Workflow_D_Glass_Structures_GP_Silica/special_requirements.md](../07_Step_by_Step_Workflows/Workflow_D_Glass_Structures_GP_Silica/special_requirements.md) for the design-for-sintering risk table (solid blocks = high risk; uniform shells = low risk).

### Fix 2 — Reduce structure size

GP-Silica shrinks approximately 25–30% during sintering (scale factor 1.35x). If your final glass part must be 100 x 100 x 50 um, print at 135 x 135 x 67.5 um. Confirm that the print time for the scaled-up version still fits within 8 hours.

### Fix 3 — Increase scan speed

GP-Silica requires higher laser power than IP-series resists due to nanoparticle scattering, but scan speed can be increased in parallel. If standard parameters are set at 40% power and 50,000 um/s, try 50% power and 80,000 um/s and verify the calibration structure.

### Fix 4 — Split into multiple prints

For very large glass structures, design the structure as two or more interlocking pieces that are sintered separately and assembled afterward. Each piece must fit within the 8-hour window.

---

## If the Print Is Running and You Are Approaching the 8-Hour Limit

If you are mid-print and realize the job will exceed the 8-hour window:

1. Check the NanoWrite progress display — what percentage is complete? How many hours remain?
2. Calculate: will it finish before the 8-hour mark? If yes, continue.
3. If no: consider stopping the print at the current layer and developing what has been printed. A partial structure may be usable for debugging even if not functional. Document the exact stop point.
4. Do not continue printing for more than 1 hour past the 8-hour mark under any circumstances — the resulting structure will not produce reliable sintered glass.

---

## Warm Up Before Applying Resist

The machine requires a 45-minute laser warm-up before every print. Complete the warm-up before applying GP-Silica. Do not start the warm-up after applying GP-Silica — this burns 45 minutes of your 8-hour window during which the resist is sitting and settling.

Correct order:
1. Start machine, begin laser warm-up.
2. While warming up: prepare substrate, set up print job in DeScribe.
3. After warm-up is complete: apply GP-Silica.
4. Load sample, run interface detection, start print immediately.

---

## Related Files

- [07_Step_by_Step_Workflows/Workflow_D_Glass_Structures_GP_Silica/special_requirements.md](../07_Step_by_Step_Workflows/Workflow_D_Glass_Structures_GP_Silica/special_requirements.md)
- [07_Step_by_Step_Workflows/Workflow_D_Glass_Structures_GP_Silica/print_steps.md](../07_Step_by_Step_Workflows/Workflow_D_Glass_Structures_GP_Silica/print_steps.md)
- [07_Step_by_Step_Workflows/Workflow_D_Glass_Structures_GP_Silica/post_processing.md](../07_Step_by_Step_Workflows/Workflow_D_Glass_Structures_GP_Silica/post_processing.md)
- [print_taking_too_long.md](./print_taking_too_long.md)
- [04_Resists_and_Materials/GP_Silica/handling_and_storage.md](../04_Resists_and_Materials/GP_Silica/handling_and_storage.md)
