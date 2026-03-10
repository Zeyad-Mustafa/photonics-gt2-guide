# STL Export Guide

---

## What Is an STL File

STL (Standard Tessellation Language, also called Standard Triangle Language) is the universal file format for 3D printing. It represents the surface of a 3D model as a mesh of triangles. Each triangle is defined by three vertex coordinates and a normal vector pointing away from the solid interior.

DeScribe reads the STL file, determines the interior volume of the model, and generates laser toolpaths to fill that volume with voxels.

---

## STL Format: Binary vs ASCII

STL files come in two formats: binary and ASCII.

Binary STL: more compact, smaller file size, faster to load. Recommended for all GT2 use.

ASCII STL: human-readable text format. Much larger file size. Only useful if you need to inspect the raw triangle data manually.

All major CAD tools export binary STL by default. If your software gives you a choice, always choose binary.

---

## Mesh Resolution

The STL mesh must be fine enough to accurately represent your model's geometry. If the mesh is too coarse, curved surfaces appear faceted (flat polygons instead of smooth curves), and DeScribe will print the faceted version.

Recommended mesh quality settings when exporting:

| Setting | Recommended value |
|---|---|
| Maximum chord deviation | 0.0001 mm (0.1 um) |
| Maximum angle deviation | 0.5 degrees |
| Minimum triangle edge length | No minimum needed |

These settings produce a mesh fine enough that the faceting is significantly smaller than the voxel size of any GT2 objective. The result is indistinguishable from a perfect smooth surface at the printing scale.

If your CAD software uses different terminology, look for settings labeled resolution, quality, tolerance, or refinement, and set them to the highest available option.

Warning about over-refining: very high mesh resolution (millions of triangles) produces extremely large STL files that are slow to import and compile in DeScribe. For most structures, the settings above produce files under 50 MB, which compile quickly. If your structure involves a very large number of features (thousands of lenses or pillars), monitor file size — above approximately 200 MB, DeScribe performance degrades.

---

## Checking Surface Normals

Surface normals are vectors that point outward from each triangle face, indicating which side is the outside of the solid. DeScribe uses normals to determine which regions are inside (to be printed) and which are outside (to be left as liquid resin).

If normals are flipped (pointing inward instead of outward), DeScribe will print the inverse of your model — the empty space will become solid and the solid will become empty. This is one of the most common causes of prints that produce a solid block instead of the expected structure.

How to check normals in Meshmixer:
1. Open the STL in Meshmixer
2. Analysis > Inspector
3. Red pins indicate open boundaries or flipped normals
4. Edit > Normals > Recalculate to fix all normals automatically

How to check normals in SolidWorks:
View > Display > Surface Normals. Arrows should all point away from the solid body.

In OpenSCAD:
If using the default CSG modeling workflow, normals are always correct. If importing external mesh files, verify before use.

---

## Watertight Check

A watertight model has no holes or gaps in its surface. Every edge must be shared by exactly two triangles. If any edge is shared by only one triangle, that edge is a boundary (a hole in the mesh), which makes the model non-manifold.

DeScribe will either fail to import a non-manifold STL or will produce incorrect toolpaths.

Quick watertight check using Windows 3D Builder:
1. Open the STL in 3D Builder
2. If 3D Builder shows a repair prompt, the model is not watertight
3. Click Repair to fix automatically
4. Export the repaired file as STL

Quick watertight check using Meshmixer:
1. Analysis > Inspector
2. Any red pins indicate mesh errors
3. Edit > Repair Tolerance = 0.001 mm > Auto Repair

---

## Units in STL Files

STL files have no intrinsic units — the numbers in the file are dimensionless. DeScribe interprets the numbers as millimeters by default.

If your CAD model was designed in micrometers, the numbers in the STL will be 1000 times smaller than expected. For example, a 10 um tall structure designed in a tool set to um units will appear as 0.01 mm in DeScribe — which may display as an invisible dot.

Solutions:
- Always design in millimeters in your CAD tool, even when your features are measured in micrometers. A 10 um feature should be entered as 0.01 mm.
- Or: use DeScribe's scaling function to scale the imported model. A model designed in um units needs to be scaled by 0.001 in DeScribe.

Before exporting, confirm your CAD model dimensions in the unit you intend. After importing into DeScribe, confirm the model bounding box dimensions before proceeding to slice.

---

## STL Export Procedures by Software

SolidWorks:
File > Save As > change file type to STL > Options > Resolution: Custom > Deviation: 0.0001 mm, Angle: 0.5 degrees > OK > Save

Fusion 360:
File > Export > STL > Refinement: Custom > Surface Deviation: 0.001 mm, Normal Deviation: 0.5 degrees > OK

FreeCAD:
Switch to Mesh Design workbench > Meshes > Create Mesh from Shape > Max edge length: 0.0001 mm > Apply > File > Export > STL

OpenSCAD:
Set $fn = 100 or higher for all cylindrical/spherical features > Design > Export as STL (binary)

Blender:
Apply all modifiers > File > Export > STL > uncheck ASCII > export

---

## File Naming

Use simple filenames with no spaces or special characters. DeScribe and NanoWrite can have problems with filenames containing spaces, parentheses, or non-ASCII characters.

Good filename: lens_array_63x_v3.stl
Problematic filename: Lens Array (63x) - version 3 final.stl

---

Proceed to: gwl_scripting_intro.md
