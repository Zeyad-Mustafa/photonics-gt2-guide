# Step 10 — Development

> Development removes the unpolymerized IP-Dip2 from around your structure. The cured structure stays. Done incorrectly, development will wash the structure off the substrate, collapse thin features, or leave residual resist that obscures your structure.

---

## Why This Step Matters

After printing, the substrate is covered in IP-Dip2: both the cured (polymerized) structure and a large volume of uncured liquid resist. Development is a chemical step that selectively dissolves the uncured material while leaving the cross-linked polymer intact.

For IP-Dip2, the developer is **PGMEA** (propylene glycol monomethyl ether acetate), followed by an IPA rinse.

---

## Chemicals Required

| Chemical | Purpose |
|---|---|
| PGMEA (propylene glycol monomethyl ether acetate) | Primary developer — dissolves uncured IP-Dip2 |
| Isopropanol (IPA) | Rinse — removes residual PGMEA and final traces of resist |
| Nitrogen (N2) gun | Drying |

All steps must be performed in a fume hood. PGMEA and IPA are flammable and irritating to respiratory tract.

---

## Procedure

1. Carefully remove the sample holder from the stage using the Exchange Holder dialog. Hold it level to prevent the resist pool from shifting.
2. Remove the substrate from the holder. Use cleanroom tweezers, gripping the substrate edge only.
3. Immediately submerge the substrate (printing side down) in a small glass dish filled with **PGMEA**.
4. Agitate gently by swirling the dish or using a magnetic stir bar at low speed. Development time: **20 minutes** for standard IP-Dip2 structures. Increase to 30 minutes for dense, thick structures.
5. Transfer the substrate to a second dish of **fresh IPA** for a 5-minute rinse.
6. Remove and dry immediately with the **N2 gun**. Dry from the center of the substrate outward with steady, gentle pressure. Do not blow so hard that features are mechanically damaged.
7. Inspect the substrate under an optical microscope at low magnification (5x or 10x) to confirm the structure is present and the surrounding area is clear of residual resist.

---

## What "Over-Development" and "Under-Development" Look Like

| Condition | Visual Indicator | Cause | Fix |
|---|---|---|---|
| Under-developed | Hazy coating around structure; structure edges blurred | Development time too short or PGMEA too old | Re-immerse in fresh PGMEA for additional time |
| Over-developed | Structure partially dissolved or collapsed | Development time too long or aggressive agitation | Reduce time; use gentler agitation |
| Correct | Structure is sharp, clean edges, no haze on substrate | — | Proceed |

---

## What Can Go Wrong

| Problem | Cause | Fix |
|---|---|---|
| Structure washes off entirely | Poor adhesion to substrate (see Step 4) | Reprint after improving substrate cleaning or adding O2 plasma |
| Thin features collapsed | Capillary forces during drying | Dry faster; use critical point drying for very fragile structures |
| Residual haze on substrate | PGMEA exhausted (too much resist dissolved in it) | Use fresh PGMEA; develop in two baths |
| Structure not visible at all | Underexposure during print — nothing polymerized | Reprint with higher laser power |

---

## Related Files

- [step_11_uv_curing.md](./step_11_uv_curing.md)
- [08_Development_and_Post_Processing/development_solvents.md](../../08_Development_and_Post_Processing/development_solvents.md)
- [08_Development_and_Post_Processing/development_times_table.md](../../08_Development_and_Post_Processing/development_times_table.md)
- [08_Development_and_Post_Processing/ipa_rinse_procedure.md](../../08_Development_and_Post_Processing/ipa_rinse_procedure.md)
- [11_Troubleshooting/structure_washed_off.md](../../11_Troubleshooting/structure_washed_off.md)
- [11_Troubleshooting/thin_features_collapsing.md](../../11_Troubleshooting/thin_features_collapsing.md)
