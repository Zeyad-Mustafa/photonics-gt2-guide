# DeScribe — Common Errors and Solutions

---

## Error: Model Displays as a Bounding Box

Symptom: after importing the STL, the 3D viewport shows a rectangular box instead of your actual model geometry. The box dimensions match your model, but no detail is visible.

Cause: this is a rendering mode setting in DeScribe, not a problem with your STL file. The toolpaths are still generated correctly.

Solution: go to the 3D preview settings or the View menu. Look for a Rendering Mode or Display Mode option. Change it from Bounding Box (or Box Preview) to Solid, Shaded, or Automatic. The model should then display correctly.

If the rendering mode option is not accessible before compilation, compile the preview first (F5) and then look for the rendering mode setting in the preview window.

---

## Error: Model Appears at Wrong Scale

Symptom: after importing, the model appears extremely small (nearly a dot in the viewport) or extremely large (exceeding the build volume by a large margin).

Cause: unit mismatch between the CAD export and DeScribe's interpretation.

Solution: apply a scale factor in the Properties panel.
- If the model is 1000 times too small: scale by 1000 (designed in mm, exported as um)
- If the model is 1000 times too large: scale by 0.001 (designed in um, exported as mm)
- If unsure: check the bounding box dimensions in Properties and compare to expected dimensions

---

## Error: Compilation Fails or Takes Extremely Long

Symptom: pressing F5 produces an error or the compilation progress bar stalls and never completes.

Cause 1: the STL has geometry errors (non-manifold mesh, open boundaries, self-intersections).
Solution: repair the STL using Meshmixer, 3D Builder, or Netfabb and re-import.

Cause 2: the STL file is extremely large (over 200 MB) due to over-refined mesh.
Solution: re-export the STL with lower mesh resolution settings. Chord deviation of 0.001 mm (not 0.0001 mm) is usually sufficient for most structures and produces much smaller files.

Cause 3: the GPU workstation is low on available RAM or VRAM.
Solution: close other applications on the GPU workstation before running DeScribe. If the problem persists, restart the computer and try again.

---

## Error: Preview Shows Inverted Geometry

Symptom: the 3D preview shows filled areas where empty space should be and empty areas where solid material should be. The structure appears to be the negative of the intended design.

Cause: surface normals in the STL are pointing inward instead of outward. DeScribe is printing the empty space rather than the solid.

Solution: repair the normals in Meshmixer (Edit > Normals > Recalculate Outside) or your CAD tool, re-export the STL, and re-import.

---

## Error: Layers Missing in Preview

Symptom: the preview animation shows the structure building up correctly for most of its height, but stops before reaching the top. The final layers of the model are not present in the preview.

Cause 1: the top of the model extends beyond the build volume boundary. DeScribe clips anything outside the build volume.
Solution: check the model position in the build volume. Move the model down (reduce Z position) so the entire model fits within the boundary.

Cause 2: the model height exceeds the working distance of the selected objective.
Solution: either use a different objective with longer working distance (10x has 700 um) or reduce the height of the model in CAD.

---

## Error: Job File Cannot Find Data File in NanoWrite

Symptom: when loading the job file in NanoWrite, an error appears saying the data file cannot be found.

Cause: the include statement in the job file contains an absolute path that does not exist on the GT2 computer. This happens when files are generated on the GPU workstation and transferred to the GT2 computer, and the full path (such as C:\Users\GPU_user\Projects\) is embedded in the job file.

Solution: open the job file in Notepad on the GT2 computer. Find the include line. Replace the full path with just the filename (no directory path). Ensure both the job file and the data file are in the same folder on the GT2 computer.

Before edit: include C:\Users\GPU_user\Projects\structure_data.gwl
After edit: include structure_data.gwl

---

## Error: Print Time Is Much Longer Than Expected

Symptom: after compilation, the estimated print time is much longer than anticipated.

Cause 1: slice distance or hatch distance is much smaller than needed.
Solution: increase slice distance and hatch distance. For the 25x objective, slice distances below 0.3 um are rarely needed and significantly extend print time.

Cause 2: solid fill is selected for a large structure that could use shell and scaffold.
Solution: switch to shell and scaffold mode. This typically reduces print time by 60 to 90 percent for large structures.

Cause 3: scan speed is set lower than necessary.
Solution: increase scan speed. Increase laser power proportionally to maintain equivalent exposure.

Cause 4: the model scale is wrong and the structure is much larger than intended.
Solution: check bounding box dimensions and correct the scale factor.

---

This is the final file in the DeScribe Software subfolder.
Proceed to: NanoWrite_Software subfolder.
