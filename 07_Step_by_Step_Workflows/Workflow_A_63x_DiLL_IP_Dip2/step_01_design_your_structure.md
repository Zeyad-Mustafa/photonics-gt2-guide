# Step 1 — Design Your Structure

> Before anything touches the machine, your structure must exist as a valid 3D model. This step covers what design constraints apply specifically to 2PP printing and to the 63x objective.

---

## Why This Step Matters

The GT2 can only print what is physically possible given its voxel size, scanning range, and the mechanical properties of the cured resist. A design that ignores these constraints will either fail to print, collapse after development, or produce a structure that looks nothing like your model.

Spend more time here than you think you need to. Fixing a design error costs 5 minutes. Discovering the same error after a 3-hour print costs far more.

---

## Design Constraints for the 63x Objective

| Parameter | Limit | Notes |
|---|---|---|
| Minimum lateral feature size | ~200 nm (practical) | Theoretical minimum is ~160 nm but requires optimal power tuning |
| Minimum axial (Z) feature size | ~500 nm | Voxel is elongated in Z due to Gaussian beam shape |
| Maximum print field (piezo mode) | 300 x 300 x 300 um | Per single print without stitching |
| Maximum print field (galvo mode) | 400 x 400 um (XY), ~8 mm (Z with stage) | Lower positional accuracy |
| Minimum wall thickness (practical) | 1–2 um | Thinner walls may collapse during development |
| Minimum pillar diameter (practical) | 2–3 um | Thinner pillars may collapse if tall |
| Minimum overhang span | ~5 um unsupported | Larger spans need support structures |

---

## Design Rules for 2PP in General

**Overhangs and bridges**  
Unlike FDM 3D printing, 2PP does not require support material for every overhang. Because the entire resin volume is present during printing, partially-cured structures can be self-supported during the print. However, after development (when liquid resin is washed away), unsupported overhangs longer than roughly 5–10 um can collapse due to capillary forces during drying. For long spans, add thin support pillars or design a scaffold.

**Aspect ratio**  
Tall, thin features collapse more easily than short, wide ones. A pillar that is 2 um in diameter and 50 um tall has a very high aspect ratio and will likely collapse. Keep aspect ratios (height/width) below approximately 20:1 for unsupported features.

**Connectivity**  
Every part of your structure must be connected to the substrate or to another part of the structure that is connected to the substrate. Floating isolated features in 3D space will wash away during development.

**Minimum layer thickness**  
In DeScribe, the minimum practical slice distance is approximately 200–300 nm for the 63x. Setting a slice distance smaller than the axial voxel size does not improve resolution — it just increases print time.

**Recommended CAD tools**  
AutoCAD, SolidWorks, Fusion 360, Blender (for organic shapes), or OpenSCAD (for parametric/scripted designs). Any tool that exports a clean, watertight STL is acceptable.

See [06_Software_Workflow/CAD_Design/designing_for_2PP.md](../../06_Software_Workflow/CAD_Design/designing_for_2PP.md) for a full set of design rules.

---

## Procedure

1. Open your CAD software of choice.
2. Design your structure with the constraints in the table above in mind.
3. Orient the structure so that its base (the face that will contact the substrate) is flat and lies in the XY plane at Z = 0.
4. Check all wall thicknesses — no wall should be thinner than 1 um.
5. Check all unsupported overhangs — add support pillars if any span exceeds ~5 um.
6. Check the overall dimensions — confirm the structure fits within 300 x 300 x 300 um if using piezo mode, or within 400 x 400 um (XY) if using galvo mode.
7. Run a mesh check or geometry validation in your CAD tool. Fix any non-manifold edges, open surfaces, or inverted normals before exporting.
8. Save the native CAD file before exporting.

---

## What Can Go Wrong

| Problem | Cause | Fix |
|---|---|---|
| Structure collapses after development | Unsupported thin features, high aspect ratio | Redesign with thicker walls or add support pillars |
| Print fails mid-job | Structure exceeds scan range | Check dimensions against 300 um (piezo) or 400 um (galvo) limits |
| STL export produces errors in DeScribe | Non-manifold geometry or open mesh | Run mesh repair in CAD tool before export |
| Printed dimensions are smaller than designed | Resist shrinkage (~10-15% for IP-Dip2) | Scale your design up by ~10-15% in DeScribe to compensate |

---

## Related Files

- [step_02_export_stl.md](./step_02_export_stl.md)
- [06_Software_Workflow/CAD_Design/designing_for_2PP.md](../../06_Software_Workflow/CAD_Design/designing_for_2PP.md)
- [06_Software_Workflow/CAD_Design/design_rules_checklist.md](../../06_Software_Workflow/CAD_Design/design_rules_checklist.md)
- [03_Objectives/63x_objective/voxel_dimensions.md](../../03_Objectives/63x_objective/voxel_dimensions.md)
