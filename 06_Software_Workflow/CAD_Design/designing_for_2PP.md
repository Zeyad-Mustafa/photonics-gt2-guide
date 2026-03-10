# Designing for Two-Photon Polymerization

---

## Overview

Two-photon polymerization imposes a specific set of design constraints that differ significantly from conventional 3D printing or microfabrication. This file documents every design rule you need to follow before exporting your model for the GT2.

---

## Rule 1 — Minimum Feature Sizes

Every element in your design must be at or above the minimum printable and stable feature size for your chosen objective. There are two distinct minimums: the physical printing minimum (the smallest voxel that can be written) and the practical stability minimum (the smallest feature that survives development without collapsing).

The stability minimum is always larger than the printing minimum. A feature that is physically printed does not automatically survive the development step — solvent forces, surface tension during drying, and resin shrinkage all act on the structure and can break or collapse features that are too small or too slender.

Minimum wall thickness by objective:

| Objective | Minimum printable wall | Minimum stable free-standing wall |
|---|---|---|
| 63x | ~300 nm | ~500 nm |
| 25x | ~800 nm | ~1.5 um |
| 10x | ~3 um | ~5 um |

Minimum pillar diameter by objective:

| Objective | Minimum stable isolated pillar |
|---|---|
| 63x | ~400 nm diameter |
| 25x | ~1 um diameter |
| 10x | ~4 um diameter |

If your design contains features at or near these minimums, expect some failure rate even with perfect printing parameters. Build in redundancy where possible — print arrays of small features rather than single isolated ones.

---

## Rule 2 — Aspect Ratio of Tall Structures

Aspect ratio is the ratio of height to the smallest lateral dimension of a feature. Very high aspect ratio structures are mechanically fragile and prone to collapse.

Recommended maximum aspect ratios:

| Feature type | Maximum recommended aspect ratio |
|---|---|
| Free-standing pillar | 10:1 (height to diameter) |
| Thin wall | 20:1 (height to thickness) |
| Cantilevered beam | 5:1 (length to thickness) |

Beyond these ratios, the structure may print successfully but collapse under its own weight, under surface tension during solvent drying, or under the mechanical force of the development solvent flow.

Strategies for high-aspect-ratio structures:
- Add temporary support pillars alongside tall features. These supports must touch the main structure and can be designed to snap off or dissolve after development.
- Use a critical point dryer (CPD) after development instead of air drying. CPD eliminates surface tension forces during drying, which is the main collapse mechanism for very tall thin structures.
- Use IP-S or IP-Dip2 (low shrinkage resins) rather than IP-Q for high-aspect-ratio features.

---

## Rule 3 — Overhanging Features

Overhangs are portions of the structure that extend horizontally beyond the structure below them, with no support beneath.

In two-photon polymerization, moderate overhangs are possible because the resin itself provides temporary support during printing — the uncured resin surrounding the focal point holds up the freshly polymerized voxels while the laser continues. Once development removes the liquid resin, the overhang must be self-supporting.

Practical overhang guidelines:

| Objective | Maximum recommended unsupported overhang span |
|---|---|
| 63x | ~10 to 20 um |
| 25x | ~50 to 100 um |
| 10x | ~200 um |

For overhangs longer than these values, add support columns below the overhanging region. The columns should be at least 2 to 3 voxel diameters wide.

Overhang angle also matters. A gentle slope (less than 45 degrees from horizontal) prints better than a near-horizontal overhang, because each new layer has more voxel overlap with the layer below, providing better mechanical continuity before the resin is developed away.

---

## Rule 4 — Anchor Structures for Substrate Adhesion

Any structure that has a small contact footprint with the substrate is at risk of detaching during development or during UV post-curing. The development solvent flows around and under the structure, and if the adhesion force is smaller than the drag force, the structure lifts off.

Design rules for adhesion:
- The substrate contact area should be at least 5 to 10 percent of the total projected area of the structure.
- Isolated pillars should have a wider base (a foot or flange) with 2 to 3 times the pillar diameter.
- Long thin walls should have periodic widened anchor pads along their length to increase contact area.
- If the structure must have a small footprint by design, surround it with a perimeter wall (a box frame) that is printed first and adheres firmly, then connect the main structure to the frame with struts.

The perimeter wall strategy is particularly important for structures printed with the 63x objective, where features are very small and contact areas are minimal.

---

## Rule 5 — Orientation in the Build Volume

The GT2 prints from the bottom of the structure upward (Z = 0 at the substrate, increasing Z away from the substrate). Lateral dimensions (X and Y) have better resolution than the axial dimension (Z). This means:

- Features whose critical dimension runs in X or Y will print more accurately than features whose critical dimension runs in Z.
- A horizontal gap (opening in the XY plane) can be smaller than a vertical gap (opening in the Z direction).
- Surfaces facing sideways (vertical walls) will show layer stairstepping at the slice distance interval.
- Surfaces facing upward or downward (horizontal faces) will be smooth at the lateral voxel scale.

Design implication: if your structure has a critical dimension — a gap, a channel, a feature width — orient the structure in DeScribe so that dimension lies in the XY plane rather than in Z. This is especially important for the 63x objective, where the axial voxel (~500 nm) is over three times larger than the lateral voxel (~160 nm).

---

## Rule 6 — Account for Shrinkage

All IP-series resins shrink during and after polymerization. The shrinkage occurs because monomer molecules pack closer together when they form polymer chains.

Typical volumetric shrinkage values:

| Resin | Approximate volumetric shrinkage |
|---|---|
| IP-Dip2 | 8 to 12 percent |
| IP-S | 5 to 8 percent (lowest shrinkage) |
| IP-Q | 8 to 12 percent |
| IP-PDMS | 5 to 10 percent |

Shrinkage is not uniform. The base of the structure adheres to the substrate and cannot shrink downward, so most shrinkage is expressed in the height (Z direction) and inward at the walls. The result is that printed structures are typically slightly shorter and slightly narrower than designed.

For most research applications, the dimensional error from shrinkage is acceptable. For precision optical devices or structures with tight dimensional tolerances, compensate by scaling up the design:

- Scale Z by a factor of 1.1 to 1.15 (10 to 15 percent taller in CAD to account for Z shrinkage)
- Scale XY by a factor of 1.05 to 1.10

The exact compensation depends on the specific resin, laser parameters, and structure geometry. Determine your calibration factors empirically with test prints before scaling critical designs.

In DeScribe, you can apply scaling factors directly during import — you do not need to modify the CAD file. See scaling_and_orientation.md.

---

## Rule 7 — Watertight Geometry

The STL file format requires a closed, watertight solid — every surface must be a closed shell with no holes, gaps, or self-intersecting faces. DeScribe cannot slice a model that has open boundaries or incorrect surface normals, because it cannot determine which side of each surface is inside and which is outside.

A watertight model means:
- Every edge is shared by exactly two faces
- All surface normals point consistently outward (away from the solid interior)
- No faces intersect each other
- No faces are zero-thickness (coincident faces)

Most professional CAD tools (SolidWorks, Fusion 360, Inventor) produce watertight solids by default when modeling correctly. Mesh-based tools (Blender, Meshmixer) require explicit watertight checks before export.

Always validate the STL before importing into DeScribe. Tools for validation are covered in stl_export_guide.md.

---

## Rule 8 — Minimum Wall Separation

Two walls that are very close together but not touching will either merge into one wall (if too close, due to voxel overlap) or leave a gap that is too small to develop properly (the solvent cannot flow into very narrow gaps to remove uncured resin).

Minimum gap between two features:

| Objective | Minimum gap for complete development |
|---|---|
| 63x | ~500 nm |
| 25x | ~2 um |
| 10x | ~8 um |

If two features must be closer than these gaps, design them as a single connected feature.

---

## Summary Table

| Rule | Key Number |
|---|---|
| Minimum stable wall (63x) | 500 nm |
| Minimum stable wall (25x) | 1.5 um |
| Minimum stable wall (10x) | 5 um |
| Maximum pillar aspect ratio | 10:1 (height to diameter) |
| Maximum overhang span (25x) | 50 to 100 um |
| Shrinkage compensation (Z) | Scale up 10 to 15 percent |
| Minimum gap for development (25x) | 2 um |
| Geometry requirement | Watertight, consistent normals |

---

Proceed to: recommended_cad_tools.md
