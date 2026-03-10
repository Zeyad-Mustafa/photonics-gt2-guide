# Step 4 — Prepare the ITO-Coated Glass Substrate

> ITO-coated glass is the standard substrate for 25x DiLL printing. The ITO (indium tin oxide) layer provides excellent refractive index contrast with IP-S, making interface detection reliable. The orientation rule — ITO side facing the objective — is critical and must not be reversed.

---

## Why ITO for the 25x?

ITO-coated glass (n_ITO ~ 1.8–2.0) has a significantly higher refractive index than IP-S (n = 1.478). This large delta-n (approximately 0.3–0.5) produces a very clear reflection signal during interface detection, making the 25x + ITO combination one of the most reliable setups for auto-approach on the GT2.

Compare this to the 63x + borosilicate glass combination (delta-n ~ 0.004) — the 25x + ITO substrate is far more forgiving for interface detection.

---

## Orientation: ITO Side Faces Down (Toward the Objective)

This is the single most important rule for this substrate:

```
CORRECT LOADING ORIENTATION:

   [ ITO coating side ]   <- faces DOWN, toward objective
   [  glass body       ]  <- faces UP, toward top hatch
   [ resist drop       ]  <- on top of ITO surface (before inverting)

After holder insertion (inverted microscope):
   [ glass body        ]  <- now on top
   [ ITO coating       ]  <- now on bottom, facing up toward objective
   [ IP-S drop         ]  <- between ITO and objective tip
```

If you load the substrate ITO-side up (glass toward objective), the laser must travel through the full glass thickness before reaching the interface. The optical path length changes, the focal point shifts, and the interface detection will find the wrong surface or fail entirely.

---

## Cleaning Procedure

1. Obtain a clean ITO-coated glass substrate (standard size: 25 x 75 mm slide, or a cut piece). Store unused substrates in a covered container away from dust.
2. Place the substrate in a glass beaker. Hold by edges only — do not touch the ITO surface.
3. Sonicate or soak in **acetone** for 5 minutes.
4. Transfer to **IPA** for 5 minutes.
5. Rinse briefly with **DI water**.
6. Dry with N2.
7. Optional: oxygen plasma treatment for 2 minutes (100 W, O2). This is recommended for IP-S on ITO — it increases wettability and adhesion.
8. Use within 30 minutes.

---

## Verifying ITO Side

If you cannot tell which side is the ITO coating:
- The ITO side often has a very slightly different reflectivity or color under bright light (a faint bluish or golden tint depending on the ITO thickness).
- Use a multimeter set to resistance mode: touch the two probes to the same face of the substrate. The ITO side is conductive and will show a finite resistance (typically 10–100 ohms/sq). The plain glass side is insulating and will show no reading.

---

## What Can Go Wrong

| Problem | Cause | Fix |
|---|---|---|
| Interface detection fails | ITO side facing wrong direction | Remove substrate; flip; reload |
| ITO coating damaged | Scratched with tweezers or abrasive contact | Use a fresh substrate |
| Watermarks after cleaning | Poor drying | Re-clean and dry faster with N2 |
| Structure does not adhere to ITO | Surface contamination | Repeat cleaning; add oxygen plasma |

---

## Related Files

- [step_05_apply_IP_S_resist.md](./step_05_apply_IP_S_resist.md)
- [05_Substrates/ITO_coated_glass.md](../../05_Substrates/ITO_coated_glass.md)
- [05_Substrates/substrate_cleaning_procedure.md](../../05_Substrates/substrate_cleaning_procedure.md)
- [05_Substrates/interface_detection_requirements.md](../../05_Substrates/interface_detection_requirements.md)
