# Step 1 — Design Your Structure

> With the 10x objective, minimum feature sizes are in the 2–5 um range and the print field is large. Design with coarser geometry and focus on overall form rather than fine detail.

---

## Design Constraints for the 10x Objective

| Parameter | Limit | Notes |
|---|---|---|
| Minimum lateral feature size | ~2–5 um (practical) | NA 0.3 sets a large voxel floor |
| Minimum axial feature size | ~5–10 um | Very elongated voxel in Z |
| Maximum print field (galvo mode) | 400 x 400 um per field | Use stitching for larger structures |
| Maximum structure volume (with stitching) | ~100 x 100 x 8 mm³ | Full stage travel |
| Minimum wall thickness | 10–20 um | Thinner walls are possible but fragile |
| Minimum pillar diameter | 10–20 um for stable freestanding features | |

---

## What the 10x Is Good At

The 10x shines for:
- Bulk structures where interior quality is less important than overall shape
- Large arrays of repeated features (printed with StageGoTo stitching)
- Structural scaffolds with feature sizes of 20 um or larger
- Rapid prototyping where a fast low-resolution print is used to validate a design before committing to 25x or 63x time

---

## Procedure

1. Design with feature sizes no smaller than 5 um.
2. Use scaffold or shell hatching — solid fill of a large volume with the 10x will take many hours. Shell + Scaffold dramatically reduces print time.
3. Check that your design can be printed in stitched galvo fields of 400 x 400 um each.
4. Run mesh validation and export STL as described in Workflow A Step 2 — the STL export process is identical.
5. Transfer STL to DeScribe workstation.

---

## Related Files

- [step_02_prepare_silicon_substrate.md](./step_02_prepare_silicon_substrate.md)
- [03_Objectives/10x_objective/voxel_dimensions.md](../../03_Objectives/10x_objective/voxel_dimensions.md)
- [06_Software_Workflow/CAD_Design/designing_for_2PP.md](../../06_Software_Workflow/CAD_Design/designing_for_2PP.md)
