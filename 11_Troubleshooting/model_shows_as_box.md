# 3D Model Shows as a Solid Box in DeScribe

> You import your STL file into DeScribe and the preview renders as a solid filled box instead of your actual structure. Slicing produces a solid block. This is a rendering and mesh issue, not a DeScribe bug.

---

## What Is Happening

DeScribe renders and slices 3D models using the surface normals of the STL mesh to determine what is inside and what is outside the model. If the surface normals are incorrect — pointing inward instead of outward, or pointing in random directions — DeScribe cannot determine which side of each triangle face is the "solid" side. It defaults to filling the entire bounding box of the model.

Two related problems produce this symptom:

1. **Inverted normals** — the faces of the mesh have outward normals pointing inward (into the solid), which tells DeScribe that the "solid" region is everything outside the shape.

2. **Non-manifold geometry** — the mesh has holes, self-intersections, or non-connected edges. A mesh with holes is topologically ambiguous: DeScribe cannot determine a consistent inside/outside, and fills the bounding box as a fallback.

---

## Confirming the Diagnosis

In DeScribe, after import, switch the 3D view to "Wireframe" mode (View menu or toolbar). In wireframe mode:
- If you see your intended geometry as a wireframe mesh: the model imported correctly but normals are wrong.
- If the wireframe shows only a box outline: the mesh is severely broken or the file format is wrong.

Check the DeScribe import log (shown in the status bar or log panel after import) for warnings about normals, non-manifold edges, or open boundaries.

---

## Fixes

### Fix 1 — Recalculate normals in MeshLab (most common fix)

MeshLab is free and handles this reliably.

1. Open your STL in MeshLab.
2. Go to Filters > Normals, Curvatures and Orientation > Re-Orient all faces coherently.
3. Then go to Filters > Normals, Curvatures and Orientation > Invert Faces Orientation — only if the preview in MeshLab shows the model "inside out" (dark where it should be light).
4. Export as STL (binary or ASCII — DeScribe accepts both).
5. Re-import into DeScribe.

### Fix 2 — Use MeshLab to repair non-manifold geometry

1. In MeshLab: Filters > Cleaning and Repairing > Select Non Manifold Edges. If any are selected, the mesh has topology errors.
2. Apply Filters > Cleaning and Repairing > Repair non Manifold Edges by removing faces.
3. Apply Filters > Cleaning and Repairing > Close Holes (set hole size large enough to close all open boundaries).
4. Re-export and re-import.

### Fix 3 — Use Meshmixer or Netfabb for automatic repair

If MeshLab manual repair is tedious:
- Meshmixer (free, Autodesk): Analysis > Inspector shows holes and errors; the "Auto Repair All" button fixes most issues in one click.
- Netfabb (online or desktop): drag-and-drop STL, click the repair tool, download the fixed file.

### Fix 4 — Regenerate the mesh from CAD with correct export settings

If the model comes from a parametric CAD tool (Fusion 360, SolidWorks, FreeCAD, OpenSCAD):

- Ensure the export settings specify "outward-facing normals" if available.
- Use a finer mesh resolution for curved surfaces — coarse triangulation on curves sometimes produces coincident faces that appear non-manifold.
- In SolidWorks: File > Save As > STL, then Options — set Resolution to Fine, check "Do not translate STL output data to positive space."
- In Fusion 360: Make > 3D Print, set Refinement to High.

### Fix 5 — Check that the file is actually an STL

Occasionally a file is saved with the .stl extension but is actually a STEP, OBJ, or other format that DeScribe cannot parse. Open the file in a text editor (STL ASCII files start with "solid"; binary files start with a 80-character header). If the content is XML or another format, re-export from CAD as genuine STL.

---

## Prevention

When exporting STL from any CAD tool, verify the mesh before importing to DeScribe:

1. Open in MeshLab and confirm the preview shows the correct geometry with correct shading (light on outside faces).
2. Run Filters > Cleaning and Repairing > Select Non Manifold Edges — zero selected means the mesh is clean.
3. Confirm face count is reasonable (not 0, not millions for a simple shape).

---

## What Can Go Wrong

| Symptom after fix | Likely remaining cause | Next step |
|---|---|---|
| Model renders correctly in DeScribe but slice is still solid | Wrong rendering mode — press F5 to update slice preview | Switch to Slice view, press F5 |
| Model renders correctly but slice is mirrored | Export coordinate system mismatch | Rotate or mirror the model in DeScribe before slicing |
| MeshLab "Re-orient" fails with error | Geometry is too broken for automatic repair | Use Meshmixer Auto Repair, then re-try in MeshLab |
| Box disappears but model is now hollow (shell only) | Normals correct but model was designed as shell — this may be intended | If solid infill is needed, add it in CAD or use DeScribe's fill settings |

---

## Related Files

- [06_Software_Workflow/DeScribe_Software/stl_import_guide.md](../06_Software_Workflow/DeScribe_Software/stl_import_guide.md)
- [06_Software_Workflow/DeScribe_Software/slicing_parameters.md](../06_Software_Workflow/DeScribe_Software/slicing_parameters.md)
- [07_Step_by_Step_Workflows/Workflow_A_63x_DiLL_IP_Dip2/step_02_export_stl.md](../07_Step_by_Step_Workflows/Workflow_A_63x_DiLL_IP_Dip2/step_02_export_stl.md)
