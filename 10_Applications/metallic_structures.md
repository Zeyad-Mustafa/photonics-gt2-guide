# Metallic Structures

## Overview

IP-series polymers are electrical insulators and have limited mechanical stiffness compared to metals. Many applications require metal structures — conductive, high-stiffness, plasmonic, or catalytic — at the microscale and nanoscale. The GT2 enables these metal structures indirectly: the polymer is printed to define the geometry, and metal is deposited or grown to fill or coat that geometry, using the polymer as a mold or template.

This section describes the main routes from a GT2 polymer print to a metallic structure.

---

## Route 1 — Metal Coating by Physical Vapor Deposition

The simplest route to a metallic GT2 structure is conformal metal coating of the printed polymer by PVD (electron beam evaporation or sputtering).

Result: a polymer core coated with a thin metal shell. The polymer remains inside; the metal provides the surface properties.

Applications:
- Magnetic microrobots: nickel or iron coating provides magnetic moment for actuation
- Plasmonic structures: gold or silver coating produces localized surface plasmon resonance
- Conductive MEMS: gold coating provides electrical conductivity for sensor applications
- Reflective optical elements: gold or aluminum coating for mirrors and retroreflectors

Process:
1. Print the GT2 structure and UV cure
2. Bake at 60 degrees C for 30 minutes to remove residual solvent
3. Deposit metal by PVD at low deposition rate to minimize thermal load on the polymer
4. Total metal thickness typically 50 to 200 nm

Limitation: PVD is a line-of-sight process. Surfaces that are shadowed from the vapor source do not receive coating. For structures with complex geometry, rotate the substrate during deposition or deposit from multiple angles to improve coverage. Complete coating of interior surfaces (hollow structures, channels) is not achievable by PVD.

---

## Route 2 — Electrodeposition Into a Polymer Mold

Electrodeposition grows a thick metal body from a conductive surface. The polymer acts as the mold, defining the outer boundary of the metal structure. After metal deposition, the polymer mold is removed to reveal a freestanding metal structure.

Result: a solid metal structure whose geometry is the inverse of the polymer print.

Applications:
- High-aspect-ratio metal pillars and walls
- Metal spring and cantilever structures
- Complex 3D metal scaffolds
- Microelectrode arrays
- Plasmonic nanostructure arrays at the 10x or 25x scale

Process:
1. Deposit a conductive seed layer on the substrate by PVD (titanium 5 nm + gold 50 nm is standard)
2. Print the GT2 polymer mold on the seed layer surface
3. Develop and UV cure the polymer mold
4. Electrodeposit metal to fill the spaces between polymer features
5. Optionally planarize the top surface (polishing or CMP) if a flat top face is needed
6. Remove the polymer mold by immersion in PGMEA (if the mold is not UV-cured) or by O2 plasma ashing (for fully cured polymer)
7. Remove the seed layer in the exposed areas by wet etching (gold etch, followed by titanium etch) if an isolated metal structure is required

Common electrodeposition metals for GT2 templates:
- Gold: low resistance, biocompatible, stable. Standard plating bath: gold sulfite or gold cyanide at pH 9 to 10.
- Nickel: higher stiffness than gold, magnetic. Standard bath: nickel sulfamate or Watts nickel bath.
- Copper: highest conductivity, inexpensive. Standard bath: copper sulfate.
- Platinum: catalytic, corrosion-resistant, biocompatible. Specialized plating chemistry required.

Mold height and aspect ratio: the polymer mold must be tall enough to confine the metal during deposition. If the metal grows above the top of the mold walls, it spreads laterally (mushrooming), producing features wider than designed. Monitor deposition time and current to stop before the metal reaches the mold top, or design the mold slightly taller than the target metal height.

---

## Route 3 — Nanocasting

Nanocasting uses the GT2 polymer structure as a master mold for casting another material at the nanoscale.

Process for metal nanocasting:
1. Print the GT2 polymer master structure
2. UV cure and apply release agent (fluorosilane vapor treatment)
3. Cast a hard stamp material (for example, h-PDMS or UV-curable epoxy) against the master
4. Cure the stamp and peel it off — this produces a negative replica
5. Use the stamp to cast a second material (for example, polyurethane, epoxy, or UV-curable polymer)
6. Deposit metal by PVD onto the final polymer replica to produce a metal-surface structure

This multi-step process is used when the required metal structure geometry cannot be achieved directly by PVD or electrodeposition, or when many copies of the same structure are needed.

---

## Route 4 — Metallic Glass Structures Via GP-Silica

GP-Silica is not a metal, but it is the closest the GT2 comes to printing a hard inorganic material directly. After debinding and sintering, GP-Silica produces pure fused silica (glass) structures with the mechanical and optical properties of glass rather than polymer.

For metal-functional glass: the sintered silica structure can then be coated by PVD with any metal, producing glass-core metal-shell structures with higher thermal stability and lower polymer background fluorescence than polymer-core alternatives.

See Workflow D (Section 07) and the GP-Silica resin files (Section 04) for the complete GP-Silica process.

---

## Design Considerations for Metallic Structure Routes

For PVD coating:
- Design all surfaces to have clear line-of-sight to the vapor source, or plan for multi-angle deposition
- Avoid re-entrant (undercut) geometries that trap shadow regions
- Minimum polymer feature size is unchanged from standard design rules — the metal coating thickness (50 to 200 nm) adds to all external dimensions

For electrodeposition:
- The seed layer must be continuous under the entire print area — gaps in the seed layer produce regions where metal cannot deposit
- Design the polymer mold with the conductive substrate as the mold floor — features must be attached to the substrate so the mold cavity is accessible from below
- Plan for seed layer removal: the etch step for gold (potassium iodide / iodine solution) is selective to gold over most metals but will also etch any exposed gold on your final metal structure if over-etched

For nanocasting:
- The polymer master must be designed for releasability — avoid extreme undercuts that lock the mold material in place
- Surface roughness of the master transfers to the cast replica. Optimize printing parameters for smooth surfaces before committing to a nanocasting workflow.

---

## Summary Table

| Route | Final material | 3D capability | Resolution limit | Key constraint |
|---|---|---|---|---|
| PVD coating | Metal shell on polymer core | Full 3D | Objective-limited | Line-of-sight deposition only |
| Electrodeposition into mold | Solid metal | Limited by mold geometry | Objective-limited | Requires conductive substrate and seed layer |
| Nanocasting | Metal surface on cast polymer | Limited by stamp release | Objective-limited | Multi-step, release agent required |
| GP-Silica + PVD | Glass core, metal shell | Full 3D | Objective-limited, plus 25 percent sintering shrinkage | Requires high-temperature furnace for sintering |

---

This is the final file in Section 10 — Applications.
Proceed to Section 11 — Troubleshooting.
