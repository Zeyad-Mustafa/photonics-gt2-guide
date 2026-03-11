# Module 11 — Troubleshooting

> Most problems on the GT2 fall into one of four categories: adhesion failures, exposure failures, software or interface errors, and process/timing errors. This module covers each with a specific diagnosis procedure and a set of fixes ordered from simplest to most involved.

---

## How to Use This Module

Start with symptoms, not assumptions. Before adjusting any parameter, confirm exactly what you are seeing. Many failures look similar on the surface — a structure that "didn't print" could be a power problem, an interface detection problem, a development problem, or an adhesion problem. Each has a different fix.

If you are new to the GT2, read [structure_not_adhering.md](./structure_not_adhering.md) and [interface_not_found.md](./interface_not_found.md) first — these are the two most common first-time failures.

---

## Quick Symptom Index

| Symptom | File |
|---|---|
| Structure is missing entirely after development | [structure_not_adhering.md](./structure_not_adhering.md) |
| Structure was present but detached during development | [structure_washed_off.md](./structure_washed_off.md) |
| Resist drop is flat; interface detection fails | [flat_resist_drop_problem.md](./flat_resist_drop_problem.md) |
| "Interface not found" error or wrong Z = 0 | [interface_not_found.md](./interface_not_found.md) |
| 3D model shows as solid box in DeScribe | [model_shows_as_box.md](./model_shows_as_box.md) |
| Estimated print time is unreasonably long | [print_taking_too_long.md](./print_taking_too_long.md) |
| Structure is bloated, fused, or over-sized | [overexposure_and_blooming.md](./overexposure_and_blooming.md) |
| Structure has voids, gaps, or missing layers | [underexposure_and_voids.md](./underexposure_and_voids.md) |
| SPS Safe State error; green Process light not lit | [sps_safe_state_error.md](./sps_safe_state_error.md) |
| Objective moved into substrate; crashing sound | [objective_crashing.md](./objective_crashing.md) |
| Fine features (pillars, walls) collapse after development | [thin_features_collapsing.md](./thin_features_collapsing.md) |
| GP-Silica print ran past the 8-hour resist lifetime | [gp_silica_print_timeout.md](./gp_silica_print_timeout.md) |

---

## General Troubleshooting Principles

**Change one variable at a time.** When a print fails, resist the urge to change power, scan speed, and development time simultaneously. Each change eliminates one hypothesis. Changing multiple variables at once prevents you from knowing which one mattered.

**Print a calibration test first.** A power sweep array or voxel calibration structure takes 10–30 minutes and tells you whether your exposure parameters are in range before you commit to a 4-hour full print.

**Document every failure.** Write down the exact parameter set, the observed outcome, and the conditions (substrate, resist lot number, development time). Patterns emerge over time.

**Check the obvious first.** Many failures trace back to: wrong objective selected in DeScribe, resist applied more than 30 minutes before printing, substrate loaded wrong side down, or development time that was too short.

---

## Related Modules

- [07_Step_by_Step_Workflows/](../07_Step_by_Step_Workflows/README.md)
- [04_Resists_and_Materials/](../04_Resists_and_Materials/README.md)
- [12_Safety/sps_safety_system.md](../12_Safety/sps_safety_system.md)
- [13_Key_Parameters_Reference/](../13_Key_Parameters_Reference/README.md)
