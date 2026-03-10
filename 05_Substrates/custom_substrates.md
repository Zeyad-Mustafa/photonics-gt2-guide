# Custom Substrates

---

## Overview

The GT2 is not limited to the four standard substrates (ITO glass, silicon, quartz, and 170 um borosilicate). Researchers frequently print on non-standard materials when the application requires it. This file covers the considerations and requirements for using custom substrates, and describes specific non-standard materials that have been successfully used with the GT2.

---

## Requirements for Any Custom Substrate

Before attempting to print on a non-standard substrate, verify that it meets all of the following requirements:

**Requirement 1 — Minimum delta-n**
The substrate must have a refractive index at least 0.04 different from the resin being used. Without this, the interface finder cannot detect the substrate surface and the print cannot begin. If delta-n is too low, there are two options: choose a different resin with a more different refractive index, or add a thin coating to the substrate (gold, ITO, or chrome) to increase the optical contrast.

**Requirement 2 — Surface flatness**
The substrate surface must be flat to within approximately 5 um across the entire print area. Variation larger than this causes the focal point to drift out of the resin during printing, resulting in incomplete structures or interface detection failure when the stage moves between tiles.

**Requirement 3 — Chemical compatibility**
The substrate must not dissolve, swell, delaminate, or change shape when exposed to the development solvents (PGMEA, IPA) for the required development time. Test a small piece in PGMEA for 30 minutes before attempting a full print.

**Requirement 4 — Thermal and mechanical stability**
The substrate must remain dimensionally stable at room temperature throughout the print. This is rarely an issue for rigid substrates but can be a concern for polymer films and soft materials.

**Requirement 5 — Fit in the sample holder**
The substrate must be 25x25 mm or smaller, and thin enough to fit within the holder's Z clearance with the objective at its maximum approach position.

---

## Polymer Film Substrates

Flexible polymer films such as polyimide (Kapton), PDMS, and parylene have been used as GT2 substrates for flexible device fabrication.

Challenges with polymer films:
- Surface flatness: polymer films are often not flat when unsupported. They must be mounted under tension or adhered to a rigid backing substrate before printing.
- Chemical compatibility: check that PGMEA does not swell or dissolve the film. Most polyimides are resistant. PDMS absorbs organic solvents and swells — test before use.
- Delta-n: most transparent polymers have refractive indices of 1.45 to 1.55, similar to the IP resins. Delta-n may be marginal. Consider adding a thin metal coating on one side to improve detection.
- Adhesion: IP-series resins may not adhere well to smooth polymer surfaces. O2 plasma treatment for 60 to 120 seconds before printing typically improves adhesion significantly.

Recommended preparation for polymer film substrates:
1. Tape the film under tension onto a rigid silicon or glass carrier wafer using thermally stable tape (Kapton tape or UV-release tape)
2. O2 plasma treat the assembly
3. Apply resin and print as normal
4. After development, carefully peel the film from the carrier

---

## Crystalline Substrates

Single crystal substrates such as lithium niobate (LiNbO3), gallium arsenide (GaAs), sapphire (Al2O3), and calcium fluoride (CaF2) have been used for integrated photonic devices where the crystal provides specific optical, electro-optic, or piezoelectric functionality.

Key considerations:
- Refractive index: crystals typically have high or anisotropic refractive indices, giving good delta-n vs IP-series resins.
- Surface preparation: many crystals require specific polishing procedures to achieve the flatness needed for GT2 printing. Confirm Ra less than 5 nm before use.
- Chemical compatibility: test in PGMEA before use. Some crystals (notably KTP and KNbO3) are slightly soluble in organic solvents over long development times.
- Orientation: some crystals cleave preferentially along crystal planes. If cuts are needed, use a dicing saw rather than scribe-and-cleave.

---

## Metal-Coated Substrates

Thin metal coatings on glass or silicon are commonly used when:
- A conductive surface is needed for electrodeposition after printing
- The base substrate has too low delta-n and needs an optically reflective coating
- Gold or platinum surfaces are needed for biosensing applications

Common metal coating stacks for GT2 substrates:
- Titanium (5 nm adhesion layer) + Gold (50 nm) on glass — highly reflective, excellent delta-n, good adhesion for IP resins after O2 plasma
- Chrome (5 nm) + Gold (50 nm) — alternative adhesion layer
- ITO (100 to 200 nm) on glass — conductive and transparent

These coatings are typically deposited by electron beam evaporation or sputtering in a cleanroom before the GT2 printing step.

Adhesion of IP-series resins to gold is poor without surface treatment. Before printing on gold:
- O2 plasma for 60 seconds (cleans and activates gold surface)
- Or apply a monolayer of 11-mercaptoundecanoic acid (MUA) or other thiol-based adhesion promoter — thiols bond strongly to gold and provide an organic surface layer that improves polymer adhesion

---

## Pre-Patterned Substrates

It is often desirable to print GT2 structures on substrates that already have features — photolithography-defined metal pads, etched trenches, waveguide structures, or other components. This enables integration of GT2 3D structures with conventionally fabricated devices.

Considerations for pre-patterned substrates:
- Surface topology: existing features create height variation on the substrate surface. If the height variation is comparable to or larger than the working distance of the objective, the interface finder may detect the wrong surface, or the print may run out of working distance part-way through.
- Step coverage: when printing a structure that bridges over a step (for example, a waveguide crossing an etched trench), the structure in the unsupported region prints in air or in resin with no underlying substrate. Adhesion is provided only by the surrounding anchors. Design accordingly.
- Alignment: GT2 alignment to existing features is done by eye using the AxioVision camera. Alignment accuracy of approximately 2 to 5 um is achievable with care. For sub-2 um alignment, external fiducial markers and custom alignment procedures are required.

---

## Adding a Thin Reflective Coating to Improve Interface Detection

If your substrate has insufficient delta-n for reliable interface detection, deposit a thin semitransparent metal film on the print surface before use:

- Chromium: 5 to 10 nm at 550 nm is semitransparent but highly reflective. Excellent for improving interface detection. Deposited by e-beam or sputtering.
- Gold: 5 to 10 nm. Slightly lower reflectivity than chromium but biocompatible. Use titanium or chromium as adhesion layer.
- The metal layer must be thin enough that the laser can still focus through it to print at the surface. For layers above approximately 20 nm, the laser is fully blocked and printing at the surface becomes impossible. Use 5 to 10 nm only.

---

Proceed to: interface_detection_requirements.md
