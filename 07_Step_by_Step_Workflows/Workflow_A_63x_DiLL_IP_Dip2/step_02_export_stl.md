# Step 2 — Export STL

> The STL file is the bridge between your CAD design and the DeScribe slicing software. A bad STL will produce a bad GWL — or no GWL at all. This step explains how to export correctly.

---

## Why This Step Matters

DeScribe reads STL files and converts them into GWL laser path instructions. If the STL contains geometry errors — open surfaces, inverted normals, self-intersecting faces — DeScribe will either reject the file or produce a corrupted toolpath. There is no way to fix a bad STL inside DeScribe.

Export clean. Check before you leave your CAD workstation.

---

## What Is an STL File?

An STL (Standard Tessellation Language) file represents a 3D surface as a mesh of triangular faces. Each triangle has:
- Three vertices (X, Y, Z coordinates)
- One normal vector (pointing outward from the solid)

A valid STL for 2PP printing must be:
- **Watertight** — no gaps or holes in the surface mesh
- **Manifold** — every edge is shared by exactly two faces
- **Outward-facing normals** — all normal vectors point away from the interior of the solid
- **No self-intersections** — faces must not pass through each other

---

## STL Export Settings

These settings apply in most CAD tools:

| Setting | Recommended Value | Notes |
|---|---|---|
| Format | Binary STL | Smaller file size than ASCII; both work in DeScribe |
| Chord tolerance / deviation | 0.01–0.1 um | Controls how finely curved surfaces are tessellated |
| Angular tolerance | 1–5 degrees | Controls smoothness of curves |
| Units | Micrometers (um) | DeScribe works in micrometers; match this in your export |

If your CAD tool exports in millimeters by default, you can rescale inside DeScribe — but it is cleaner to export in the correct unit from the start.

---

## Procedure

1. In your CAD tool, select the body or component you want to export.
2. Go to File > Export (or equivalent) and select STL as the format.
3. Set the export units to micrometers.
4. Set chord tolerance to 0.05 um or equivalent fine tessellation. Coarse tessellation will make curved surfaces appear faceted in the print.
5. Choose Binary STL format.
6. Name the file clearly: `structurename_v1.stl`. Avoid spaces in filenames.
7. Export to a known folder.
8. Open the STL in a mesh viewer (MeshLab, Windows 3D Viewer, or similar) and visually confirm the geometry looks correct — no missing faces, no inverted patches, correct orientation.
9. If your tool provides a mesh analysis function, run it and resolve any errors before continuing.
10. Transfer the STL file to the computer running DeScribe (the CNF GPU computer, not the NanoWrite PC).

---

## Common Mesh Errors and How to Fix Them

| Error | Symptom in DeScribe | Fix |
|---|---|---|
| Open mesh (non-watertight) | Structure shows holes or DeScribe cannot slice it | Use MeshLab or Netfabb to close holes; re-export |
| Inverted normals | Structure appears inside-out in DeScribe preview | Flip normals in MeshLab (Filters > Normals > Flip) |
| Self-intersecting geometry | Slicing produces erratic toolpaths | Rebuild the geometry in CAD to eliminate intersections |
| Wrong units (mm instead of um) | Structure appears 1000x too large in DeScribe | Scale by 0.001 in DeScribe, or re-export with correct units |
| Model shows as a box in DeScribe | Rendering mode is wrong — not a mesh error | Change rendering mode in DeScribe (see [06_Software_Workflow/DeScribe_Software/common_errors.md](../../06_Software_Workflow/DeScribe_Software/common_errors.md)) |

---

## Note on DeScribe's Own Mesh Repair

DeScribe has limited mesh repair capabilities. For any significant mesh error, repair the STL externally using MeshLab (free, open source) before importing into DeScribe. Do not rely on DeScribe to fix structural geometry problems.

---

## Related Files

- [step_01_design_your_structure.md](./step_01_design_your_structure.md)
- [step_03_slice_in_describe.md](./step_03_slice_in_describe.md)
- [06_Software_Workflow/CAD_Design/stl_export_guide.md](../../06_Software_Workflow/CAD_Design/stl_export_guide.md)
- [06_Software_Workflow/DeScribe_Software/importing_stl.md](../../06_Software_Workflow/DeScribe_Software/importing_stl.md)
- [06_Software_Workflow/DeScribe_Software/common_errors.md](../../06_Software_Workflow/DeScribe_Software/common_errors.md)
