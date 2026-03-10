# Step 4 — Prepare the Substrate

> A contaminated substrate is the most common cause of adhesion failure. Structures that print perfectly but wash off during development almost always trace back to a substrate that was not cleaned correctly.

---

## Why This Step Matters

The GT2 prints structures that must adhere to the substrate surface during development, UV curing, and subsequent handling. The adhesion between the cured IP-Dip2 and the substrate depends entirely on molecular contact at the interface. Any contamination layer — oils, organic residues, dust, water — physically prevents that contact.

---

## Compatible Substrates for Workflow A (63x + IP-Dip2)

| Substrate | Notes |
|---|---|
| 170 um borosilicate glass (No. 1.5 coverslip) | Most common; n = 1.515, ideal refractive index match |
| Quartz (fused silica) | Lower autofluorescence than borosilicate; use for fluorescence applications |
| Silicon wafer piece (25 x 25 mm or smaller) | Opaque — camera view is limited; use for non-optical applications |
| ITO-coated glass | Acceptable for 63x if cleaned well |

For full substrate compatibility details, see [05_Substrates/borosilicate_glass_170um.md](../../05_Substrates/borosilicate_glass_170um.md).

---

## Procedure

1. Cut or cleave your substrate to the appropriate size (typically 10–25 mm on a side) if not already sized. Use a diamond scribe or dicing saw — never snap glass freehand.
2. Place the substrate in a clean glass beaker. Do not touch the printing surface with bare fingers. Hold by edges or use cleanroom tweezers.
3. Immerse in **acetone** and sonicate for 5 minutes, or soak with agitation for 10 minutes.
4. Transfer to **isopropanol (IPA)** and sonicate or agitate for 5 minutes.
5. Rinse with **deionized (DI) water** for 30 seconds.
6. Dry with a clean nitrogen (N2) gun. Blow from the center outward to avoid streaks.
7. Inspect the surface under a bright light or optical microscope. There should be no visible residue, particles, or watermarks.
8. Optional but recommended: perform a **2-minute oxygen plasma treatment** (100 W, 100 mTorr O2). Plasma removes sub-monolayer organic contamination and increases surface energy, which improves IP-Dip2 adhesion. See [08_Development_and_Post_Processing/oxygen_plasma_treatment.md](../../08_Development_and_Post_Processing/oxygen_plasma_treatment.md).
9. Use the substrate within 30 minutes of cleaning. Do not leave cleaned substrates exposed to lab air for extended periods.

---

## What Can Go Wrong

| Problem | Cause | Fix |
|---|---|---|
| Watermarks visible after drying | Drying too slowly or DI water quality poor | Re-clean and dry faster with N2 |
| Substrate surface still has particles | Tweezers or container contaminated | Use fresh cleanroom tweezers; use clean beakers |
| Structure washes off during development | Surface contamination at interface | Re-clean with oxygen plasma and reprint |
| Substrate cracks during cutting | Incorrect scribing technique | Score once firmly; do not saw back and forth |

---

## Related Files

- [step_05_apply_resist.md](./step_05_apply_resist.md)
- [05_Substrates/substrate_cleaning_procedure.md](../../05_Substrates/substrate_cleaning_procedure.md)
- [05_Substrates/borosilicate_glass_170um.md](../../05_Substrates/borosilicate_glass_170um.md)
- [08_Development_and_Post_Processing/oxygen_plasma_treatment.md](../../08_Development_and_Post_Processing/oxygen_plasma_treatment.md)
- [11_Troubleshooting/structure_not_adhering.md](../../11_Troubleshooting/structure_not_adhering.md)
