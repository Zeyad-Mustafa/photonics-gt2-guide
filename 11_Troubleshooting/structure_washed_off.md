# Structure Washed Off During Development

> The structure appeared to print successfully, but after development you find it is missing or partially destroyed. The substrate is clean where the structure should be, or only a stub remains.

---

## What Is Happening

"Washed off" is mechanically different from adhesion failure. In adhesion failure, the structure forms fully and detaches intact. In wash-off, the structure breaks apart during the development rinse — either because features are too fragile, development was too aggressive, or surface tension forces during drying tore the structure from the substrate.

The visual clue is fragmented polymer debris in the development bath, or a fractured stub remaining on the substrate with broken features around it.

---

## Most Common Causes

**1. Thin, tall features with insufficient mechanical strength**

Pillars, walls, and overhanging features with high aspect ratios (height >> width) are vulnerable during development. As PGMEA or IPA flows past the feature, drag forces can snap it. During IPA drying, surface tension as the liquid front recedes applies a powerful capillary force that pulls features sideways and can tear them from the substrate.

**2. Over-development**

PGMEA dissolves uncured resist. If development continues too long, it begins to attack the surface of cured polymer, thinning features and weakening base connections. For IP-Dip2, development beyond 30 minutes risks over-development.

**3. Aggressive rinsing**

Pouring fresh PGMEA or IPA directly onto the structure, or agitating the development bath vigorously, increases drag forces on fragile features.

**4. Insufficient exposure — partially cured features**

If the structure is exposed near the lower edge of the process window, features may be mechanically weak due to incomplete polymerization. They survive development partially but fracture at weak points.

**5. No adhesion layer or support base**

Freestanding tall structures with a very small footprint have limited contact area with the substrate. High-aspect-ratio features with a base of only a few micrometers are at risk regardless of development procedure.

---

## Fixes

**Fix 1 — Reduce development agitation**

Do not stir, sonicate, or pour fresh solvent directly onto the structure. Place the sample gently in a still bath of PGMEA. If a second fresh bath is used, transfer the sample slowly.

**Fix 2 — Replace IPA rinse with critical point drying (CPD)**

Surface tension during IPA evaporation is the dominant cause of thin feature collapse. Critical point drying eliminates this entirely by replacing the IPA with liquid CO2 at high pressure, then transitioning to gaseous CO2 above the critical point — a phase transition with zero surface tension.

CPD is available at most facilities with electron microscopy labs. For structures with pillar diameters below 2–3 um or wall thicknesses below 1 um, CPD is the correct solution.

**Fix 3 — Shorten development time**

Verify that your PGMEA development time is within the recommended range:

| Resist | Recommended PGMEA development |
|---|---|
| IP-Dip2 | 20 minutes |
| IP-S | 20–25 minutes |
| IP-Q | 20–45 minutes (scale with volume) |
| GP-Silica | 20–30 minutes |

If you have been developing beyond these times, reduce to the standard time and evaluate.

**Fix 4 — Add a protective frame or wall around fragile features**

In CAD, add a solid wall (2–5 um thick, same height as the structure) encircling the most vulnerable features. This wall is sacrificial — it provides mechanical shelter from solvent flow during development and is removed by cleaving or dissolving after the structure is on the SEM stub or target substrate.

**Fix 5 — Add a wider base to high-aspect-ratio features**

For pillars and thin walls, add a wider base pad (e.g., 5 x 5 um at the bottom of a 1 um pillar) to increase the bonded footprint. This substantially increases the force required to detach the feature.

**Fix 6 — Increase exposure slightly**

If features are mechanically weak due to incomplete cure, increase laser power by 5–10% or reduce scan speed by 10–15% and reprint the calibration structure. Evaluate feature stiffness (they should not flex under the N2 dry stream after development).

---

## What Can Go Wrong

| Symptom | Likely Cause | Fix |
|---|---|---|
| Debris visible in development bath | Features snapped during development | Reduce agitation, add support walls |
| Structure present but collapsed to one side | Surface tension during IPA drying | Switch to CPD |
| Only the base layer remains | Feature-substrate bond held but features broke at their base | Wider base pad, higher exposure for lowest layers |
| Random features missing, others intact | Localized low exposure due to beam aberration or bubble | Check for air bubbles in resist, clean objective tip |

---

## Related Files

- [thin_features_collapsing.md](./thin_features_collapsing.md)
- [structure_not_adhering.md](./structure_not_adhering.md)
- [underexposure_and_voids.md](./underexposure_and_voids.md)
- [07_Step_by_Step_Workflows/Workflow_A_63x_DiLL_IP_Dip2/step_10_development.md](../07_Step_by_Step_Workflows/Workflow_A_63x_DiLL_IP_Dip2/step_10_development.md)
- [08_Development_and_Post_Processing/scaffold_and_shell_printing.md](../08_Development_and_Post_Processing/scaffold_and_shell_printing.md)
