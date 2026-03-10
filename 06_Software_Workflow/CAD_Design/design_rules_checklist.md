# Design Rules Checklist

Run through every item on this list before exporting your STL. Catching problems here takes two minutes. Catching them after a failed four-hour print takes much longer.

---

## Geometry Checks

[ ] The model is a single closed solid with no open edges or holes in the surface.

[ ] Surface normals are all pointing outward (away from the solid interior). Check using Meshmixer Inspector or equivalent.

[ ] No self-intersecting faces. Two surfaces that cross each other will produce incorrect toolpaths in DeScribe.

[ ] No zero-thickness walls (shell bodies or surfaces without volume). DeScribe cannot slice surfaces — only solid volumes.

[ ] The model was designed in millimeters, or you know the unit conversion factor to apply in DeScribe.

---

## Feature Size Checks

[ ] The smallest wall thickness in the design is at or above the minimum stable wall thickness for your chosen objective (500 nm for 63x, 1.5 um for 25x, 5 um for 10x).

[ ] The smallest gap or channel width is at or above the minimum developable gap (500 nm for 63x, 2 um for 25x, 8 um for 10x).

[ ] All isolated pillars or posts have a diameter-to-height aspect ratio below 1:10.

[ ] All cantilevers or overhangs are within the maximum unsupported span for your objective.

---

## Orientation and Adhesion Checks

[ ] The face of the structure that will contact the substrate is flat (or has a flat base added).

[ ] The contact footprint is large enough for reliable adhesion throughout development. If the footprint is very small, a perimeter wall or base flange has been added.

[ ] Critical dimensions (smallest gaps, finest features) are in the XY plane rather than the Z direction, taking advantage of the better lateral resolution.

[ ] The total structure height does not exceed the working distance of the objective being used (360 um for 63x, 380 um for 25x, 700 um for 10x).

---

## Shrinkage Compensation

[ ] If dimensional accuracy is critical, the model has been scaled up to compensate for shrinkage. Z dimension scaled by 1.10 to 1.15. XY dimensions scaled by 1.05 to 1.10. (Skip this item if dimensional tolerances are loose.)

---

## Export Settings

[ ] Mesh resolution is set appropriately: chord deviation 0.0001 mm, angle deviation 0.5 degrees or equivalent.

[ ] Export format is binary STL, not ASCII.

[ ] Filename contains no spaces, parentheses, or special characters.

[ ] STL file size is below 200 MB. If larger, check whether mesh resolution is set too high and reduce.

---

## Final Validation

[ ] The STL file has been opened in 3D Builder, Meshmixer, or an equivalent tool and no geometry errors were found (or all errors were repaired before export).

[ ] The bounding box dimensions of the exported STL match the expected dimensions of your design.

---

If all items are checked, proceed to DeScribe for slicing.
