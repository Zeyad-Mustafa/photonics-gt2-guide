# DeScribe — 3D Preview Guide

---

## What the 3D Preview Does

After you click Slice, DeScribe calculates all the toolpaths but does not immediately generate the final GWL files. Instead, it first compiles a 3D preview — an animated visualization of the print showing how the laser will trace through your structure layer by layer.

The 3D preview has two purposes:

Verification: you can visually confirm that the slicing produced the correct toolpaths for your structure. If something is wrong (missing layers, incorrect fill, inverted geometry), you will see it here before wasting machine time.

Time estimate: after compilation, DeScribe displays the estimated total print time. This is the main number to check before proceeding.

---

## Compiling the Preview

After setting all parameters, press F5 (or click the Compile button) to start the preview compilation. Compilation time depends on the complexity of your model and the performance of the GPU workstation. Simple structures take seconds. Large complex structures with solid fill and fine parameters may take several minutes.

A progress indicator shows compilation progress. Do not close DeScribe or restart the computer during compilation.

---

## Reading the Preview

When compilation completes, the preview animation is available. Press Play (or the spacebar) to run the animation.

What you see: the cross-section of your structure at the current layer height, with the hatch lines drawn in sequence as the animation plays. The color typically indicates layer height — lower layers in one color, upper layers in another.

What to look for:

Correct geometry: does the cross-section at each layer look like the correct cross-section of your model? For a cylinder, you should see circles. For a box, you should see squares.

Correct fill: are the hatch lines filling the interior of each cross-section? Gaps or missing regions indicate a geometry problem in the STL or a slicing parameter problem.

Correct layer count: does the structure build up to the expected height? If it stops early, the model may be truncated at the build volume boundary.

No inverted geometry: if the solid regions appear where empty space should be and vice versa, the surface normals are inverted. Go back, fix the STL, and re-import.

---

## Color by Height

The standard DeScribe color scheme shows layers colored by height from the substrate upward. The exact colors depend on the DeScribe version, but typically:

- Layers near the substrate are shown in one color (often blue or green)
- Layers in the middle of the structure transition through the color range
- Layers at the top of the structure are shown in another color (often red or yellow)

This color coding makes it easy to confirm that the full height of the structure is present and that no layers are missing.

---

## Checking the Estimated Print Time

After compilation, the estimated print time is displayed in the information panel. Read this carefully before proceeding.

Questions to ask about the print time:

Is it within my machine time reservation? If you have reserved two hours and the print takes six, you need to adjust parameters or reserve more time.

Is it realistic for the structure size? A 100 um cube taking eight hours with solid fill and 63x parameters is normal. The same structure taking 30 seconds suggests the parameters or model scale are wrong.

If the print time is too long, reduce it by: increasing slice distance, increasing hatch distance, increasing scan speed, switching to shell and scaffold mode, or switching to a larger objective.

---

## The Preview Shows a Box Instead of My Model

This is a known issue in some DeScribe versions where the 3D viewport renders the model as its bounding box rather than the actual geometry. The toolpaths are still correct — only the visual representation is wrong.

Solution: look for a Rendering Mode setting in the 3D Preview menu or the View menu. Switch from Bounding Box to Solid or Shaded. See common_errors.md for the full procedure.

---

Proceed to: generating_gwl_files.md
