# Step 3 — Slice in DeScribe

> DeScribe converts your STL into a GWL laser path file. The parameters you set here determine your structure's resolution, surface quality, mechanical strength, and print time. This is the most parameter-intensive step in the workflow.

---

## Why This Step Matters

The STL file describes geometry. The GWL file describes every laser position and movement. DeScribe is the translator between them. The slicing parameters you enter — slice distance, hatch distance, laser power, scan speed — are permanently baked into the GWL. If they are wrong, the only fix is to re-slice and re-print.

Do not rush this step.

---

## Before You Open DeScribe

- DeScribe must be installed on the **CNF GPU computer** (or equivalent workstation), not on the NanoWrite PC that controls the GT2. These are separate machines.
- Your STL file must be accessible on the DeScribe computer.
- You must know which objective and resist you are using — the parameters below are specific to the 63x + IP-Dip2 combination.

---

## Procedure

1. Open DeScribe on the GPU workstation.
2. Go to File > Import and select your STL file.
3. In the import dialog, confirm the units are micrometers. If the model appears the wrong size, scale it here.
4. In the Object panel, verify the model geometry looks correct. If it shows as a gray box instead of your structure, change the rendering mode from "Bounding Box" to "Solid" or "Wireframe" using the View menu.
5. Set the **Objective** dropdown to **63x**.
6. Set the **Resist** dropdown to **IP-Dip2** (if available) or manually enter matching parameters.
7. Set slicing parameters as described in the table below.
8. Check the hatching strategy — for solid structures, use Shell + Scaffold. For hollow or optical structures, use Contour Only or Shell Only.
9. Verify structure orientation: the base of your structure (the face that contacts the substrate) must be at Z = 0. Rotate if needed.
10. Press F5 to compile and preview the toolpath animation. Watch the full animation at least once. Confirm layers appear in the correct order and the structure builds as expected.
11. If the preview looks correct, go to File > Export GWL and save both the `_data.gwl` and `_job.gwl` files to the same folder.
12. Transfer the GWL files to the NanoWrite PC (USB drive or network share).

---

## Recommended Starting Parameters for 63x + IP-Dip2

These are conservative starting parameters. Optimize them based on your specific structure and desired resolution.

| Parameter | Starting Value | Notes |
|---|---|---|
| Slice distance | 0.5 um | Distance between Z layers |
| Hatch distance | 0.3 um | Distance between adjacent laser scan lines |
| Laser power | 20–30% | Start low; increase if underexposed |
| Scan speed | 10,000–50,000 um/s | Faster = less exposure per point |
| Hatching strategy | Shell + Scaffold | Good mechanical strength with shorter print time |
| Scan mode | Piezo | For structures < 300 x 300 x 300 um |

> Always check the estimated print time shown by DeScribe after compiling (F5). A 30-minute estimated time becomes a 3-hour commitment if you discover an error mid-print. Verify before transferring to the machine.

---

## Understanding Slice Distance and Hatch Distance

**Slice distance** is the vertical step between layers. For the 63x, the axial voxel size is approximately 500 nm. A slice distance of 500 nm means each layer just touches the previous one. Using 300–500 nm gives solid, well-connected layers. Using 1 um or more can leave gaps between layers (underexposure in Z).

**Hatch distance** is the lateral spacing between scan lines within a layer. For the 63x, the lateral voxel diameter is approximately 160–300 nm depending on power. A hatch distance smaller than the voxel diameter ensures overlap between adjacent lines. Use 200–400 nm for solid fills.

```
Cross-section view (XZ plane):

Slice distance = 0.5 um:
   layer 3  ---- ---- ---- ---- ----   Z = 1.0 um
   layer 2  ---- ---- ---- ---- ----   Z = 0.5 um
   layer 1  ---- ---- ---- ---- ----   Z = 0.0 um (substrate)

Hatch distance = 0.3 um (top view, single layer):
   |  |  |  |  |  |  |  |  |  |  |
   0.3um spacing between scan lines
```

---

## Hatching Strategies

| Strategy | Description | Use When |
|---|---|---|
| Shell + Scaffold | Solid outer shell with internal scaffold fill | Most structures — good balance of speed and strength |
| Solid Fill | Every voxel in the volume is cured | Maximum mechanical strength; longest print time |
| Contour Only | Only the outer surface shell is cured | Hollow structures, optical shells |
| Shell Only | Outer surface without internal scaffold | Thin-walled vessels |

---

## What Can Go Wrong

| Problem | Cause | Fix |
|---|---|---|
| Model shows as a gray box | Wrong rendering mode in DeScribe | Change rendering mode to Solid or Wireframe |
| Preview animation looks wrong | Incorrect Z orientation | Rotate model so base is at Z = 0 |
| Estimated print time is unreasonably long | Slice/hatch distance too small, or solid fill on large structure | Increase slice distance, use scaffold mode, reduce fill density |
| GWL export produces only one file | Some DeScribe versions split into _data and _job | Both files are needed; check export folder |
| Structure prints smaller than designed | IP-Dip2 shrinkage (~10-15%) | Scale model by 1.10–1.15x before slicing |

---

## Related Files

- [step_02_export_stl.md](./step_02_export_stl.md)
- [step_04_prepare_substrate.md](./step_04_prepare_substrate.md)
- [06_Software_Workflow/DeScribe_Software/slicing_parameters.md](../../06_Software_Workflow/DeScribe_Software/slicing_parameters.md)
- [06_Software_Workflow/DeScribe_Software/hatching_strategies.md](../../06_Software_Workflow/DeScribe_Software/hatching_strategies.md)
- [06_Software_Workflow/DeScribe_Software/generating_gwl_files.md](../../06_Software_Workflow/DeScribe_Software/generating_gwl_files.md)
- [06_Software_Workflow/DeScribe_Software/3d_preview_guide.md](../../06_Software_Workflow/DeScribe_Software/3d_preview_guide.md)
