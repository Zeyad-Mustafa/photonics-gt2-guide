# Structure Not Adhering to Substrate

> You develop the substrate and find nothing there — or you find a floating polymer film somewhere in the development bath. The structure printed but did not bond to the substrate.

---

## What Is Happening

Adhesion failure means the polymerized structure separated from the substrate during or after development. The structure is fully formed but not attached. You may see:

- A floating polymer film or fragment in the PGMEA bath
- An empty substrate with faint residue where the structure should be
- Partial adhesion — the structure is still there but lifts off with the slightest touch

This is distinct from underexposure (structure was never fully formed) and from being washed away (structure broke apart during development). See [underexposure_and_voids.md](./underexposure_and_voids.md) and [structure_washed_off.md](./structure_washed_off.md) for those cases.

---

## Most Common Causes

**1. Substrate not cleaned before printing**

This is the most common cause. Organic contamination (oils, fingerprints, residual resist from a previous print) prevents the photopolymer from bonding to the substrate surface. IP-series polymers bond to glass and silicon through weak van der Waals and covalent interactions — these require direct contact with a clean surface.

**2. Not printing deep enough into the substrate**

If Z = 0 was set slightly above the true substrate surface, the first printed layer is floating in resist rather than touching the substrate. The structure forms but has no bond.

**3. Insufficient exposure in the first layers**

The lowest layers of the structure must be printed with enough dose to ensure full cure and strong interface adhesion. If power is at the low end of the process window, the base layers may be only partially polymerized.

**4. Substrate surface energy is too low**

Some substrates (PDMS, Teflon-coated, some polymers) have inherently low surface energy that resists adhesion. Standard glass, silicon, ITO, and quartz all have good surface energy for IP-series polymers.

**5. Resist was old or partially pre-polymerized**

Resist exposed to ambient light or stored incorrectly may have undergone partial polymerization before printing. This changes the mechanical properties of the cured polymer and can weaken adhesion.

---

## Diagnosis

Before reprinting, determine which cause applies:

1. Inspect the empty substrate under optical microscopy. If there is a clean circular region where the structure should be (matching the print field), the structure formed and detached. If there is nothing at all, consider underexposure.

2. Look at the PGMEA development bath. A floating polymer film or flakes visible in the bath confirms the structure formed and detached.

3. Check the substrate cleaning procedure used. Was O2 plasma applied? Was the substrate touched after cleaning?

4. Review the Z = 0 position recorded during interface detection. Was the interface found confidently, or was detection marginal?

---

## Fixes

Apply fixes in this order — start with substrate preparation before adjusting exposure parameters.

**Fix 1 — Clean the substrate properly**

Repeat the full substrate cleaning procedure:

1. Sonicate in acetone for 5 minutes (or wipe with acetone-dampened cleanroom swab).
2. Rinse with IPA.
3. Rinse with DI water.
4. Dry with N2.
5. Inspect under bright light — the surface should be visibly clean with no water spots or residue.

After cleaning, do not touch the substrate surface with bare hands. Use cleanroom gloves and handle only by edges.

**Fix 2 — Apply oxygen plasma treatment**

O2 plasma is the single most effective adhesion improvement step available without changing chemistry. It removes sub-monolayer organic contamination and activates the surface with hydroxyl groups that form covalent bonds with the photopolymer.

- Recommended parameters: 100–200 W, 100% O2, 1–2 minutes
- Use within 30 minutes of printing — surface energy decays over time
- Do not use on ITO substrates at high power — plasma can etch the ITO layer. 30 seconds at low power (50 W) is safe.

**Fix 3 — Verify Z = 0 is at the substrate surface**

After interface detection, examine the interference fringes in AxioVision. The fringes should disappear sharply at the detected Z position. If detection was ambiguous or if the fringes disappeared gradually, the detected Z may be off by 1–5 um above the true surface.

If you suspect Z = 0 is too high, manually adjust it 1–2 um lower (deeper into the substrate side) before printing.

**Fix 4 — Increase power or reduce scan speed for base layers**

In DeScribe, it is possible to add an adhesion layer or "anchor" at the base of the structure with higher exposure than the bulk. Some operators print the first 5–10 um of a structure at 110–120% of the nominal power to ensure strong substrate bonding, then reduce to normal power for the rest.

Alternatively, reduce scan speed by 20% for the first 10 layers.

**Fix 5 — Use an adhesion promoter**

For substrates with low surface energy or when plasma treatment is not available:

- Coat the clean substrate with a thin layer of HMDS (hexamethyldisilazane) vapor by placing it in a HMDS vapor prime oven for 5 minutes, or apply a dilute HMDS solution (1% in IPA), spin-coat, and bake at 90 C for 1 minute.
- HMDS converts surface hydroxyl groups to trimethylsilyl groups that bond better to most photopolymers.
- Note: HMDS changes the surface chemistry. Confirm it is appropriate for your application before use.

---

## What Can Go Wrong

| Symptom | Likely Remaining Cause | Additional Fix |
|---|---|---|
| Structure detaches again after plasma treatment | Z = 0 too high | Adjust Z = 0 lower |
| Partial adhesion — edges lift, center holds | Uneven surface energy | Full substrate plasma, extend plasma time |
| Large flat structures detach; small ones hold | Internal stress in large flat layers | Add support walls, reduce fill density, print in sections |
| Adhesion only fails on silicon, not on glass | Silicon native oxide layer | Piranha clean or buffered HF dip (see facility SOP) |

---

## Related Files

- [interface_not_found.md](./interface_not_found.md)
- [underexposure_and_voids.md](./underexposure_and_voids.md)
- [07_Step_by_Step_Workflows/Workflow_A_63x_DiLL_IP_Dip2/step_04_prepare_substrate.md](../07_Step_by_Step_Workflows/Workflow_A_63x_DiLL_IP_Dip2/step_04_prepare_substrate.md)
- [05_Substrates/substrate_preparation.md](../05_Substrates/substrate_preparation.md)
