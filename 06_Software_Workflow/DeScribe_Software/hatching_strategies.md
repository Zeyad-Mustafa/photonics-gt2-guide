# DeScribe — Hatching Strategies

---

## What Is a Hatching Strategy

The hatching strategy determines how DeScribe fills the interior of each layer cross-section with scan lines. It also determines whether additional outer shell passes are written around the perimeter of each layer. The choice of strategy affects print time, mechanical strength, surface quality, and optical properties of the printed structure.

---

## Strategy 1 — Solid Fill

In solid fill mode, the entire interior of every layer cross-section is filled with parallel hatch lines at the hatch distance spacing. The result is a fully dense solid.

When to use solid fill:
- Mechanical structures where maximum stiffness and strength are needed
- Structures that will undergo further processing (etching, deposition, electroforming)
- Small structures where the total volume is not a concern for print time
- Structures that need to be optically opaque

Disadvantage: slowest mode — every interior voxel is written.

---

## Strategy 2 — Shell and Scaffold

In shell and scaffold mode, only the outer shell of the structure (a few voxels thick) is written as a dense solid. The interior is filled with a sparse scaffold — a coarse hatch at much larger spacing than the shell, typically 5 to 10 times the solid fill hatch distance.

The result is a hollow structure with a solid exterior wall and a loose internal framework. After development, the scaffold provides structural rigidity while dramatically reducing the total number of written lines.

When to use shell and scaffold:
- Large structures where print time is the primary concern
- Structures where optical transparency of the interior is desired
- Mechanical metamaterials where low density is a design goal
- Any structure where full solid density is not needed

Print time reduction: shell and scaffold typically reduces print time by 60 to 90 percent compared to solid fill, with only moderate reduction in mechanical stiffness.

Shell thickness: typically set to 2 to 4 voxel diameters. Thinner shells are fragile; thicker shells reduce the time savings.

---

## Strategy 3 — Contour Only

In contour mode, only the outermost shell is written — one or two scan lines around the perimeter of each layer cross-section. No interior fill is written at all.

The result is a hollow shell structure.

When to use contour only:
- Optical elements where a thin polymer shell is the entire device (micro-shells, micro-containers)
- When the structure will be filled with another material after printing (metal electrodeposition, infiltration with a second resin)
- Extremely time-sensitive prints where only the outline is needed
- Research into surface-quality-optimized printing

Limitations: contour-only structures are mechanically fragile and may collapse during development if the shell is too thin. They work best for closed convex shapes (spheres, cylinders, closed boxes).

---

## Strategy 4 — Shell with Solid Infill Regions

Some versions of DeScribe allow custom infill density by region — a high-density fill near critical surfaces and low-density fill in non-critical interior regions. This is an advanced setting. If your DeScribe version supports it, consult the in-software help for the specific implementation.

---

## Hatch Orientation

The angle of hatch lines relative to the X axis can be set in DeScribe. For most structures, the default 0 or 45-degree orientation is fine.

For structures with long thin features aligned in one direction, rotating the hatch by 45 or 90 degrees can improve surface quality on those faces by ensuring scan lines cross the feature boundary at an angle rather than running parallel to it.

---

## Choosing the Right Strategy

| Situation | Recommended strategy |
|---|---|
| Small high-detail structures (63x) | Solid fill |
| Large fast prints (10x) | Shell and scaffold |
| Thin-walled optical shells | Contour only |
| Mechanical structures needing strength | Solid fill |
| Scaffold or lattice structures | Shell and scaffold or solid fill depending on strut size |
| First test print to check dimensions | Contour only (fast) |

---

Proceed to: scaling_and_orientation.md
