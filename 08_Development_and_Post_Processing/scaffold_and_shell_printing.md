# Scaffold and Shell Printing — Development Implications

## Overview

The hatching strategy chosen in DeScribe directly affects how the structure behaves during development. Shell and scaffold mode and contour-only mode produce structures with internal geometry very different from solid fill, and this affects how the development solvent must penetrate, how long development takes, and what failure modes to expect.

This file focuses specifically on the development implications of different hatching strategies. For a description of how to configure these strategies in DeScribe, see Section 06 — hatching_strategies.md.

---

## Solid Fill Structures and Development

A solid fill structure is a fully dense polymer block. The uncured resin that must be removed during development is only on the exterior surfaces — there is no uncured resin inside the structure because the laser has scanned every voxel of the interior.

Development of solid fill structures is straightforward:
- PGMEA contacts the exterior surfaces and washes away the surrounding uncured resin pool
- The only development challenge is ensuring solvent reaches into any fine external features (narrow gaps, undercuts)
- Development time is determined by the external geometry, not internal volume

The solid fill structure is the most mechanically robust and the most resistant to development-related failure. Because there are no internal voids, collapse during development is primarily a surface-tension problem at fine external features.

---

## Shell and Scaffold Structures and Development

A shell and scaffold structure has:
- A dense outer shell (typically 2 to 4 voxels thick)
- A sparse internal scaffold printed at much larger hatch spacing (5 to 10 times the shell hatch distance)
- Significant uncured resin in the interior (in the regions between scaffold struts)

Development of shell and scaffold structures requires the PGMEA to penetrate into the structure interior through any openings in the shell and dissolve the uncured resin trapped inside. If the shell has no openings, the interior cannot be developed and will remain filled with hardened but not fully cured resin.

Design considerations for developable shell and scaffold structures:

Opening the shell: for enclosed shell structures (a closed box or sphere), at least one opening must be present to allow solvent ingress and egress. In DeScribe, this can be created by leaving one face of the shell unprinted, or by designing vent holes into the CAD model.

Scaffold strut spacing: if the scaffold struts are too closely spaced, the narrow channels between them are difficult to develop. Maintain at least 5 um of open space between scaffold struts (for 25x), or at least 1 um (for 63x) to ensure adequate solvent flow.

Development time: shell and scaffold structures require longer development times than solid fill structures of the same external dimensions, because the solvent must diffuse through the scaffold to reach all uncured regions. Add 30 to 50 percent to the standard development time for enclosed shell-and-scaffold structures.

Signs of incomplete internal development: the structure appears milky or hazy under optical microscopy even after development, indicating uncured resin is still present internally. Return to fresh PGMEA for additional time.

---

## Contour-Only Structures and Development

A contour-only structure is a thin polymer shell — typically one to three voxels thick — with the entire interior unfilled. After development, PGMEA must flow inside the shell and dissolve the liquid resin that fills it.

Development of contour-only structures:
- Requires openings in the shell for solvent entry — a completely sealed contour structure cannot be developed internally
- Is typically fast once solvent enters — the interior is pure liquid resin with no scaffold to slow solvent penetration
- Is dominated by the mechanical fragility of the thin shell — handle with extreme care during all transfers

The thin shell of a contour-only structure is the most fragile geometry the GT2 produces. Development forces, capillary forces during drying, and the IPA rinse flow all pose collapse risks. Use gentle, slow handling throughout.

For contour structures that will be filled with another material (metal by electrodeposition, a second resin by infiltration), development removes the interior resin while the outer shell provides the mold geometry.

---

## Drying Implications by Strategy

| Strategy | Internal voids | Drying risk | Recommended drying method |
|---|---|---|---|
| Solid fill | None | Low — only external surface features at risk | Nitrogen blow dry is sufficient |
| Shell and scaffold | Significant internal open volume | Medium — capillary forces in scaffold channels | Nitrogen blow dry; CPD if scaffold channels below 2 um |
| Contour only | Large interior void | High — thin shell is mechanically fragile | CPD strongly recommended for shells below 1 um thickness |

---

Proceed to: secondary_fabrication.md
