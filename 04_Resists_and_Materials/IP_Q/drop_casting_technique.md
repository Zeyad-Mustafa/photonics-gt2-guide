# IP-Q — Drop Casting Technique

> The way you apply IP-Q to the substrate is one of the most critical steps in the 10x workflow. Applying too much resist — or creating a flat drop instead of a domed one — is the most common cause of failed interface detection with the 10x objective. Read this file carefully before your first print.

---

## Why Drop Shape Matters for the 10x

In the standard 25x and 63x DiLL workflows, the resist volume on the substrate is less critical because the objective tip enters the resist from below and the interface detection relies primarily on the refractive index step at the substrate surface.

With the 10x objective:
- The working distance is 700 um — much longer than the 25x (380 um) or 63x (360 um)
- The long working distance means the objective approaches the resist drop from further below
- The system's auto-interface finder relies on detecting the **curved bottom surface of the resist drop** as the first refractive interface it encounters

If the drop is spread flat (like a thin film), the bottom surface of the drop is nearly parallel to the substrate — and there is no curved interface for the system to detect cleanly. A **semi-spherical (domed) drop** has a well-defined curved surface that produces a clear reflection signal.

```
CORRECT: Semi-spherical drop
        ( resist )
        (   drop  )
   ___________________
       substrate

   -> Curved bottom surface of drop is clearly detectable
   -> Interface detection works reliably

INCORRECT: Flat puddle
   ___________________
   ___________________  <- thin flat film
   ___________________
       substrate

   -> No curved surface -> poor or failed interface detection
   -> Flat drop may also partially dewet the substrate
```

---

## How Many Drops to Apply

**Apply only 1-2 small drops.**

This is the single most important rule for IP-Q application. One drop from the bottle dropper tip is approximately 10-20 uL. Two drops is the maximum.

| Drop Count | Result |
|---|---|
| 1 drop | Ideal — forms a small domed semi-spherical drop |
| 2 drops | Acceptable — slightly larger dome, still detectable |
| 3+ drops | Too much — drop spreads flat, merges, interface detection may fail |
| Drop from pipette tip (5 uL) | Ideal — smallest controllable volume |

If you have applied too much resist and the drop is already flat, do not try to remove it with a pipette. Remove the substrate from the holder, clean it (acetone then IPA), dry it, and re-apply correctly.

---

## Step-by-Step Application Procedure

1. Prepare your substrate: silicon wafer piece or large flat substrate, cleaned and dry.
2. Load the substrate into the Multi-DiLL Silicon Wafer Holder, **polished side up** (the polished/smooth side is the printing surface; it faces upward, away from the objective, before the holder is inverted).
3. With the substrate held flat and horizontal, bring the IP-Q dropper bottle tip close to the substrate center.
4. Allow **one drop** to fall onto the center of the substrate. Do not touch the tip to the substrate.
5. Watch the drop — it should form a domed, semi-spherical bead. If it spreads immediately into a thin flat film, the substrate surface is contaminated and needs to be cleaned.
6. If a second drop is needed (for larger print areas), apply it immediately adjacent to the first. They will merge into one slightly larger dome.
7. Insert the holder into the stage using the Exchange Holder dialog.

---

## What If the Drop Spreads Flat?

A drop that spreads flat immediately after application indicates one of these issues:

| Cause | Fix |
|---|---|
| Substrate contamination (oil, organics from handling) | Clean with acetone then IPA, dry with N2, retry |
| Substrate has high surface energy (plasma-cleaned recently) | Paradoxically, oxygen plasma can make IP-Q spread too flat — wait 30-60 min after plasma before applying resist |
| IP-Q viscosity is too low (resist is degraded or at high temperature) | Let the resist cool to room temperature; check for degradation |
| Silicon surface is hydrophilic from oxidation | Brief HF dip or fresh O2 plasma then immediate application can help — discuss with your lab supervisor |

---

## The Polished Side Rule

Silicon wafers have a **polished side** (mirror-like) and a **rough back side** (matte). Always apply IP-Q to the **polished side**. The polished side is the side that was epitaxially grown and is optically smooth — the laser must interact with this smooth surface to print cleanly.

When loaded in the Multi-DiLL holder and inserted into the stage:
- The polished side faces upward initially (when you apply resist)
- After inserting the holder, the polished side (with resist) faces downward toward the objective

This is the same inverted-microscope logic as all other holders.

---

## Related Files

- [overview.md](./overview.md)
- [properties.md](./properties.md)
- [handling_and_storage.md](./handling_and_storage.md)
- [02_Machine_Components/sample_holder_types.md](../../02_Machine_Components/sample_holder_types.md)
- [07_Step_by_Step_Workflows/Workflow_C_10x_Large_Scale/step_03_apply_IP_Q.md](../../07_Step_by_Step_Workflows/Workflow_C_10x_Large_Scale/step_03_apply_IP_Q.md)
- [11_Troubleshooting/flat_resist_drop_problem.md](../../11_Troubleshooting/flat_resist_drop_problem.md)