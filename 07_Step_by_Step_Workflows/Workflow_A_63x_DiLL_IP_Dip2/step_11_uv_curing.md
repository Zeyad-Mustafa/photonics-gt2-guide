# Step 11 — UV Curing

> UV post-curing completes the crosslinking of the polymer network. A structure that skips this step is mechanically weaker and may continue to shrink or distort over time.

---

## Why This Step Matters

During 2PP printing, only the resist at the laser focal point is fully polymerized. The surrounding volume receives no exposure and is removed in development. However, the printed structure itself may not be fully cross-linked — there may be unreacted monomer groups within the cured network that were not fully converted during printing.

UV post-curing drives these residual groups to complete their reaction, resulting in a harder, more stable, more dimensionally stable structure. For IP-Dip2, post-curing also shifts the refractive index slightly as the polymer network densifies.

---

## UV Curing Station

Your facility should have a dedicated UV curing station (typically a 405 nm LED or broadband UV lamp in a box with a yellow filtered viewport). The GT2 facility at most institutions has this adjacent to the machine.

| Parameter | Value |
|---|---|
| Wavelength | 405 nm |
| Maximum exposure time | 40 minutes (auto shutoff on most stations) |
| Typical exposure time for IP-Dip2 | 10–20 minutes |
| Eye protection | Yellow filter on viewport prevents direct UV exposure |

Do not look directly at the UV lamp. The yellow viewport filter blocks the 405 nm light from exiting the box. If your station does not have a filtered window, do not look at the sample while curing is in progress.

---

## Procedure

1. Place the developed and dried substrate face-up in the UV curing station.
2. Close the lid of the curing station.
3. Set the timer to 10–20 minutes for standard IP-Dip2 structures. Do not exceed 40 minutes — extended exposure can cause yellowing or embrittlement of some resist formulations.
4. Start the UV lamp.
5. Wait for the timer to complete. The station will shut off automatically if it has an auto-shutoff feature.
6. Remove the substrate. The structure is now fully cured.
7. Inspect again under an optical microscope. The structure should appear slightly more opaque or have a marginally different color compared to pre-UV-cure (the change is subtle).

---

## When UV Curing Is Optional vs. Required

| Situation | UV Cure Required? |
|---|---|
| Structures for SEM imaging | Recommended but optional |
| Structures for mechanical testing | Required |
| Optical elements (lenses, waveguides) | Required — refractive index and surface quality depend on full cure |
| Biocompatibility applications | Required — residual monomer can be cytotoxic |
| Temporary test prints | Optional |

---

## What Can Go Wrong

| Problem | Cause | Fix |
|---|---|---|
| Structure yellows or discolors | Over-exposure (> 40 min) or wrong wavelength | Reduce exposure time; confirm 405 nm wavelength |
| Structure cracks during UV cure | Excessive internal stress amplified by additional cross-linking | Use shorter exposure time; check that development was complete before curing |
| No visible change | Normal — UV curing effects on IP-Dip2 are subtle visually | Continue to characterization step |

---

## Related Files

- [step_12_characterization.md](./step_12_characterization.md)
- [08_Development_and_Post_Processing/uv_curing_station.md](../../08_Development_and_Post_Processing/uv_curing_station.md)
- [12_Safety/uv_curing_eye_safety.md](../../12_Safety/uv_curing_eye_safety.md)
