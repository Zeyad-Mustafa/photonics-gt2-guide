# DeScribe — Importing an STL File

---

## Opening DeScribe and Starting a New Project

Launch DeScribe on the GPU workstation. To start a new project, go to File > New or click the New Project button. This opens a blank workspace.

---

## Importing the STL

Go to: File > Import > STL (or drag and drop the STL file into the DeScribe window).

After import, the model appears in the 3D viewport. Before proceeding, verify the following:

---

## Step 1 — Confirm the Model Appears Correctly

The model should appear as a recognizable 3D solid in the viewport. It should look like your design.

If the model appears as a solid rectangular box instead of your actual shape, this is a rendering mode problem, not a geometry problem. It does not mean your STL is corrupt. See common_errors.md for the solution (change the rendering mode in the 3D preview settings).

If the model appears extremely small (nearly invisible) or extremely large (filling the entire viewport and beyond), this is a units mismatch. See Step 2.

If the model is inverted (appears to be a hollow shell of empty space rather than a solid), the surface normals are flipped. Re-export the STL with corrected normals before proceeding.

---

## Step 2 — Confirm Dimensions

After import, check the bounding box dimensions displayed in the Properties panel (usually on the right side of the DeScribe interface). Verify that the dimensions match your design intent.

Common dimension problems:

Model appears 1000 times too small: your CAD was designed in micrometers but the STL was exported interpreting the numbers as millimeters. Solution: scale the model by 0.001 in DeScribe, or re-export from CAD with the unit set to millimeters.

Model appears 1000 times too large: your CAD was designed in millimeters but exported in a way that DeScribe is reading as meters or another large unit. Solution: scale down by the appropriate factor.

Model dimensions are correct: proceed to the next step.

---

## Step 3 — Select the Objective

In the parameter panel, select the objective you will use for this print from the dropdown menu. The available options correspond to the objectives installed on your GT2 system.

This selection changes the default parameter ranges and some interface options to be appropriate for that objective. Always set this correctly before adjusting any other parameters.

---

## Step 4 — Select the Resin

Select the resin (photoresist) from the dropdown. The available resins are those compatible with the selected objective. If your target resin does not appear, check that the correct objective is selected — some resins only appear when the compatible objective is chosen.

---

## Step 5 — Position the Model in the Build Volume

The build volume is shown as a transparent box in the viewport. Your model should be positioned within this box, sitting at or slightly above the bottom face (which represents the substrate surface).

Use the Position controls to move the model:
- Set Z position to 0 so the base of the model sits exactly at the substrate surface. If your structure needs a gap between the substrate and the first printed layer, set a small positive Z offset.
- Set X and Y position to 0 to center the structure over the default print position. This can be adjusted later using StageGoTo commands in the GWL file.

---

## Step 6 — Confirm Before Slicing

Before clicking Slice, confirm:
- Objective is selected correctly
- Resin is selected correctly
- Model dimensions are correct
- Model is positioned within the build volume with base at Z = 0
- Model is oriented so critical dimensions are in the XY plane

If all items are confirmed, proceed to slicing_parameters.md to set the remaining parameters before slicing.
