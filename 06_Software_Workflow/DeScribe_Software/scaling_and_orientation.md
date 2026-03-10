# DeScribe — Scaling and Orientation

---

## Why You May Need to Scale in DeScribe

There are two common reasons to scale a model in DeScribe rather than in CAD:

Units mismatch: if the model was designed in micrometers and the STL numbers are being read as millimeters, scale by 0.001 to bring the model to the correct size.

Shrinkage compensation: to pre-compensate for resin shrinkage, scale the model up before slicing. Scale Z by 1.10 to 1.15 (10 to 15 percent) and XY by 1.05 to 1.10 (5 to 10 percent). The printed structure then shrinks back to approximately the design dimensions.

---

## How to Scale in DeScribe

In the Properties panel with your model selected, find the Scale section. Enter scale factors for X, Y, and Z independently.

To scale uniformly (all axes by the same factor): enter the same value for X, Y, and Z, or use the Lock Aspect Ratio checkbox if available.

To apply shrinkage compensation: unlock aspect ratio, enter 1.10 for Z, 1.05 for X and Y. This scales Z more than XY because vertical shrinkage is typically greater.

After scaling, always re-check the bounding box dimensions in the Properties panel to confirm the scaled dimensions are what you expect.

---

## Orientation in the Build Volume

Orientation refers to how your model is rotated relative to the GT2's XYZ axes. The default import orientation is usually correct if your CAD model was designed with the print base facing down (negative Z direction in CAD = substrate side).

When to change orientation:

The substrate contact face is not flat: if the model has a curved or angled bottom, rotate it so the flattest face is at the bottom (Z = 0 plane).

Critical dimensions are in Z: if your most important features run vertically in the default orientation, rotate the model 90 degrees so they run horizontally. This takes advantage of the better lateral resolution.

The model is imported upside down: this happens when CAD coordinate systems differ from DeScribe's. Rotate 180 degrees around the X or Y axis.

---

## How to Rotate in DeScribe

In the Properties panel, find the Rotation section. Enter rotation angles in degrees around the X, Y, and Z axes.

Rotation is applied in the order X, then Y, then Z. For 90-degree rotations (the most common case), the order matters — a 90-degree rotation around X followed by 90 degrees around Y is not the same as the reverse.

After rotating, visually confirm in the viewport that the model is oriented correctly with the intended base face at the bottom.

---

## Checking Final Position

Before slicing, confirm:
- The base of the model sits at Z = 0 (substrate surface level). If the model was rotated, it may now have its base above Z = 0 — translate it down if needed.
- The model is within the build volume boundaries shown in the viewport. Any part of the model outside the build volume boundaries will be clipped and not printed.
- The XY center of the model is at the desired position. For single structures, center at X = 0, Y = 0. For arrays or specific positioning, use StageGoTo commands (see stagegoTo_commands.md).

---

Proceed to: 3d_preview_guide.md
