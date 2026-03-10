# Workflow D — Glass Structures Using GP-Silica

> GP-Silica allows you to print true fused silica (glass) structures on the GT2. The printed part is a polymer-silica composite that is subsequently sintered in a furnace at 1500 degrees C to produce a pure glass structure. This workflow has additional requirements that no other workflow has — read this file completely before starting.

---

## What Is GP-Silica?

GP-Silica is not a conventional photopolymer resin. It is a suspension of **fused silica nanoparticles** in a photopolymerizable binder. When printed and developed, you have a composite structure (polymer + silica particles). After sintering, the polymer burns away and the silica particles fuse together, producing a structure made of pure fused silica glass.

The final glass structure is chemically and thermally identical to fused quartz: optically transparent across UV to near-IR, chemically inert, thermally stable, and mechanically hard.

---

## Critical Requirements and Constraints

Read all of these before proceeding:

**8-hour time limit.** Once the GP-Silica resist is applied to the substrate, the print job must be started, completed, and the sample removed within 8 hours. After 8 hours, the resist degrades and the print will fail. Schedule accordingly — do not apply resist and then leave it overnight.

**Furnace access required.** Post-processing requires a tube furnace capable of reaching 1500 degrees C in a controlled atmosphere. This is specialist equipment. Confirm furnace access with your facility before attempting this workflow.

**Shrinkage of 25–30%.** GP-Silica structures shrink significantly during sintering as the polymer burns off and the silica densifies. You must scale all dimensions up by approximately 1.3 to 1.35 (30–35%) before slicing to compensate.

**Cracking risk.** Designs with large solid masses or abrupt thickness changes are prone to cracking during sintering due to differential shrinkage. Hollow shell designs and structures with uniform wall thickness sinter more reliably.

---

## Files in This Workflow

| File | What It Covers |
|---|---|
| `README.md` | This file — overview and requirements |
| `special_requirements.md` | 8-hour limit, furnace requirements, design adaptations |
| `print_steps.md` | The full printing procedure (modified from standard DiLL) |
| `post_processing.md` | Debinding and sintering — the two-stage furnace process |

---

## Related Files

- [04_Resists_and_Materials/GP_Silica/overview.md](../../04_Resists_and_Materials/GP_Silica/overview.md)
- [04_Resists_and_Materials/GP_Silica/workflow_special_steps.md](../../04_Resists_and_Materials/GP_Silica/workflow_special_steps.md)
- [04_Resists_and_Materials/GP_Silica/debinding_and_sintering.md](../../04_Resists_and_Materials/GP_Silica/debinding_and_sintering.md)
- [11_Troubleshooting/gp_silica_print_timeout.md](../../11_Troubleshooting/gp_silica_print_timeout.md)
