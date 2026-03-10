# Step 2 — Export STL

> STL export requirements for Workflow B are identical to Workflow A. The same rules apply: watertight mesh, outward normals, correct units, no self-intersections.

---

## Procedure

Follow the same procedure as [Workflow A / step_02_export_stl.md](../Workflow_A_63x_DiLL_IP_Dip2/step_02_export_stl.md).

Key reminders:
- Export in micrometers
- Use binary STL format
- Set chord tolerance to 0.05 um for smooth curved surfaces
- Validate the mesh before transferring to the DeScribe computer
- Transfer to the CNF GPU workstation (not the NanoWrite PC)

---

## Related Files

- [step_01_design_your_structure.md](./step_01_design_your_structure.md)
- [step_03_slice_in_describe.md](./step_03_slice_in_describe.md)
- [06_Software_Workflow/CAD_Design/stl_export_guide.md](../../06_Software_Workflow/CAD_Design/stl_export_guide.md)
