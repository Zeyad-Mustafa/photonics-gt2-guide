# Step 1 — Design Your Structure

> Design constraints for the 25x objective are more relaxed than for the 63x. You have a larger print field, larger minimum features, and more latitude in wall thickness. This makes Workflow B much more suitable for complex 3D geometries.

---

## Design Constraints for the 25x Objective

| Parameter | Limit | Notes |
|---|---|---|
| Minimum lateral feature size | ~500 nm (practical: 1–2 um) | Resolution limited by NA 0.8 |
| Minimum axial feature size | ~1 um | |
| Maximum print field (galvo mode) | 400 x 400 um (XY), ~8 mm (Z with stage) | Most common mode for 25x |
| Maximum print field (piezo mode) | 300 x 300 x 300 um | Higher positional accuracy |
| Minimum wall thickness (practical) | 2–5 um | Thinner walls feasible but fragile |
| Minimum pillar diameter | 3–5 um for aspect ratios < 10:1 | |

For structures larger than 400 x 400 um, use field stitching (multiple print fields joined together). DeScribe and NanoWrite support automatic stitching using `StageGoToX` / `StageGoToY` GWL commands. See [06_Software_Workflow/DeScribe_Software/stagegoTo_commands.md](../../06_Software_Workflow/DeScribe_Software/stagegoTo_commands.md).

---

## Design Recommendations Specific to IP-S

IP-S has approximately 5% shrinkage — much lower than IP-Dip2. For most mesoscale structures, this is small enough to ignore. For precision parts where dimensional accuracy matters, scale your design by 1.05 in all directions before slicing.

IP-S produces very smooth surfaces. Shell + Scaffold hatching strategy with a 500 nm hatch distance gives excellent surface quality for optical and microfluidic applications.

---

## Procedure

Follow the same design process as Workflow A Step 1, with the updated constraints in the table above.

1. Design in your CAD tool with the 25x constraints in mind.
2. Orient the base of the structure at Z = 0.
3. Check all features against minimum dimensions.
4. Run a mesh validation.
5. Save the native file.

---

## Related Files

- [step_02_export_stl.md](./step_02_export_stl.md)
- [06_Software_Workflow/CAD_Design/designing_for_2PP.md](../../06_Software_Workflow/CAD_Design/designing_for_2PP.md)
- [03_Objectives/25x_objective/voxel_dimensions.md](../../03_Objectives/25x_objective/voxel_dimensions.md)
