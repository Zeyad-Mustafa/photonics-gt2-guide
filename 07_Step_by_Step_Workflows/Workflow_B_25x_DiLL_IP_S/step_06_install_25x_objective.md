# Step 6 — Install the 25x Objective

> The 25x objective has one critical mechanical feature that the other objectives do not: an adjustment ring that must be set to the correct position for DiLL mode. Getting this wrong degrades resolution significantly without any obvious warning during the print.

---

## The Adjustment Ring — The Most Commonly Missed Step

The 25x objective is a multi-immersion objective. It can be used with different immersion media by rotating an adjustment ring on the objective barrel. The ring has labeled positions for different media (water, glycerol, oil, etc.).

For DiLL mode with IP-series resists, the adjustment ring must be set to **"Glyc"** (glycerol position). On the ring, look for the position where **three of the longest bar markers are visible**. This is the glycerol setting.

```
Adjustment ring positions (schematic, viewed from side):

[  |  |  |  |  ]   <- wrong position
[  |||  |  |   ]   <- wrong position
[  |||  |||    ]   <- CORRECT: "Glyc" — three longest bars
```

Why glycerol? The 25x was designed for aqueous and glycerol immersion in biological microscopy. Its glycerol correction is close enough to the refractive index of IP-series resists (n ~ 1.47–1.48) to produce well-corrected focus without spherical aberration. Using the water setting (n = 1.33) or the oil setting (n = 1.515) introduces spherical aberration that degrades resolution and increases voxel elongation.

---

## Procedure

1. Retrieve the 25x objective from its storage position.
2. Locate the adjustment ring on the objective barrel. It is typically a ribbed ring approximately 1/3 of the way up from the front lens.
3. Rotate the ring to the "Glyc" position (three longest bars visible). Rotate slowly and feel for detents — the ring clicks at each labeled position.
4. Confirm the setting visually before installing.
5. In NanoWrite, use the Exchange Holder dialog to retract the objective to the safe position.
6. Open the top hatch.
7. Thread the 25x objective into the turret finger-tight. The 25x uses a **silicone O-ring** (not a fiber ring) to seal the threads.
8. Close the hatch.
9. Select the 25x in NanoWrite and confirm the working distance is set to 380 um.

---

## Cleaning the 25x After Use

After printing with IP-S or other resists, the 25x objective tip will be coated in resist. Clean it the same way as the 63x:
1. Lens tissue dampened with PGMEA — one gentle wipe.
2. Follow with IPA on a fresh lens tissue.
3. Inspect and repeat if needed.

The 25x is more tolerant of cleaning than the 63x because its coating is more robust, but the same care applies — never scrub.

---

## What Can Go Wrong

| Problem | Cause | Fix |
|---|---|---|
| Poor resolution / elongated voxels | Adjustment ring on wrong position | Remove objective; set ring to Glyc; reinstall |
| Interface detection inconsistent | Working distance set incorrectly | Set to 380 um in NanoWrite |
| Resist wicks into objective | O-ring missing or damaged | Check O-ring before each installation |

---

## Related Files

- [step_07_load_sample_holder.md](./step_07_load_sample_holder.md)
- [03_Objectives/25x_objective/overview.md](../../03_Objectives/25x_objective/overview.md)
- [03_Objectives/25x_objective/adjustment_ring_guide.md](../../03_Objectives/25x_objective/adjustment_ring_guide.md)
- [03_Objectives/25x_objective/installation_steps.md](../../03_Objectives/25x_objective/installation_steps.md)
