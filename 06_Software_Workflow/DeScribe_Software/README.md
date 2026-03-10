# DeScribe Software — Section Overview

## What DeScribe Does

DeScribe is Nanoscribe's proprietary slicing and toolpath generation software. It is the bridge between your CAD model and the GT2 machine. Its job is to take a 3D solid (your STL file) and convert it into a sequence of laser movements (GWL code) that the GT2 can execute.

This conversion involves several steps that DeScribe handles automatically based on the parameters you set:

Slicing: the 3D model is cut into horizontal layers separated by the slice distance you specify. Each layer becomes one level of laser scanning.

Hatching: within each layer, DeScribe generates a pattern of parallel scan lines (the hatch) that fills the interior of the slice cross-section. The spacing of these lines is the hatch distance.

Shell generation: optionally, DeScribe can add outer shell passes around the perimeter of each layer, in addition to the interior hatch. Shell passes improve surface quality.

Toolpath ordering: DeScribe determines the most efficient order to write all the lines in all the layers, minimizing unnecessary stage moves.

GWL output: the complete toolpath is written to a GWL script file ready for NanoWrite.

---

## Where to Run DeScribe

DeScribe must be run on the designated GPU workstation, not on the GT2's control computer and not on your personal laptop.

The GPU workstation is a separate computer in the GT2 lab (typically located next to or near the GT2 machine). It has a dedicated graphics card required for DeScribe's 3D preview compilation and rendering.

The GT2's control computer runs NanoWrite only. Do not install DeScribe on it.

---

## Files in This Subfolder

| File | Contents |
|---|---|
| installation_and_setup.md | System requirements, finding the GPU workstation, initial setup |
| importing_stl.md | How to import your STL, unit confirmation, position in build volume |
| slicing_parameters.md | Slice distance, hatch distance, laser power, scan speed — all explained |
| hatching_strategies.md | Shell and scaffold, solid fill, contour modes and when to use each |
| scaling_and_orientation.md | Scaling, rotating, and positioning your model |
| 3d_preview_guide.md | Compiling and reading the 3D preview animation |
| generating_gwl_files.md | Generating the output files and understanding what each does |
| multi_print_jobs.md | Printing multiple structures in one job |
| stagegoTo_commands.md | Using StageGoTo commands to position prints |
| common_errors.md | Known DeScribe problems and solutions |

---

After completing DeScribe setup, proceed to the NanoWrite Software subfolder.
