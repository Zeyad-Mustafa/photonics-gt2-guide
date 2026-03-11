# Tilt Correction Mode

> Tilt correction mode compensates for substrates that are not perfectly flat or level relative to the piezo scan plane. Without correction, a tilted substrate causes printed layers to drift in Z, producing structures with wedge-shaped cross-sections instead of uniform vertical walls.

---

## The Problem Tilt Correction Solves

Ideally, every substrate sits perfectly horizontal — parallel to the XY plane of the piezo stage. In practice, no substrate is perfectly flat, and no holder seats with perfect repeatability. A substrate that is tilted by even 0.01 degrees (0.17 mrad) will show a Z-height variation of approximately 0.5 um across a 300 um XY scan field.

For structures where layer registration is critical — photonic crystals, precision optical elements, nanostructured arrays — this 0.5 um Z error causes each layer to be slightly offset from the previous one, progressively degrading the structure as height increases.

```
WITHOUT tilt correction (exaggerated):

desired layers (horizontal):         actual layers (tilted substrate):
___________________________          ___________________________
___________________________            ___________________________
___________________________              ___________________________
|                          |           <- layers drift in Z across field
substrate (flat)                       substrate (tilted)


WITH tilt correction:

___________________________          ___________________________
___________________________          ___________________________
___________________________          ___________________________
                                     <- layers follow the substrate plane
substrate (tilted)                   substrate (tilted, but correction applied)
```

Tilt correction actively adjusts the Z position of each voxel based on its X, Y location, so that all printed layers conform to the actual substrate plane rather than the ideal horizontal plane.

---

## How Tilt Correction Works

Before the print begins, the system measures the substrate tilt by sampling the Z-position of the substrate surface at multiple X, Y points. From these measurements, a plane equation is fit to the substrate surface:

```
Z_corrected = Z_nominal + a*X + b*Y
```

Where a and b are the tilt coefficients (in um/um) determined from the surface sampling. During printing, every Z command in the GWL is offset by this correction term based on the current X, Y position of the focal point.

The result: even though the substrate is tilted, the printed layers are always the correct distance from the substrate surface at every point in the field.

---

## Requirements for Tilt Correction

**Piezo scan mode is required.** Tilt correction adjusts Z in real time based on XY position. This requires the piezo stage to make continuous small Z adjustments while scanning in XY. Galvo scan mode cannot do this — the galvo controls XY, but the Z correction requires the piezo, and the two cannot be independently coordinated in this way.

Tilt correction is therefore only available when piezo scan mode is selected in DeScribe and NanoWrite.

**The substrate surface must be detectable.** The tilt measurement uses the same reflection-based surface sensing as standard interface detection. If the substrate has very low delta-n with the resist (< 0.04), neither standard interface detection nor tilt measurement will work reliably.

**The tilt must be within the piezo Z range.** If the substrate is so severely tilted that the required Z correction exceeds the piezo range (300 um) across the print field, the correction cannot be applied fully. In practice, physical substrates in properly maintained holders rarely exceed a tilt of a few micrometers per hundred micrometers — well within the piezo correction range.

---

## When Tilt Correction Is Needed

Tilt correction is not required for most prints. It becomes important for:

| Application | Reason |
|---|---|
| Photonic crystals | Layer registration errors of even 100 nm degrade band structure |
| Diffraction gratings | Grating lines must be uniform depth across the full field |
| Flat optical elements (metasurfaces) | All features must be at the same Z to function correctly |
| Multi-layer stacked structures | Each layer must align precisely with those below |
| Large-area precision patterns | Tilt error accumulates with field size |

For routine printing of microstructures, scaffolds, or mechanical objects where dimensional tolerance is 1–2 um, tilt correction is typically unnecessary.

---

## Enabling Tilt Correction in NanoWrite

1. Ensure piezo scan mode is selected for your print job.
2. After loading the sample and finding the interface, locate the tilt correction panel in NanoWrite.
3. Click "Measure Tilt" or equivalent. NanoWrite will sample the substrate surface at a grid of X, Y points (typically 3 x 3 or 5 x 5) and calculate the tilt coefficients.
4. Review the measured tilt values. Typical values for a well-loaded sample: < 0.005 um/um in X and Y. Values > 0.02 um/um indicate the holder is not seated correctly — consider removing and reloading the sample.
5. Enable tilt correction and confirm the coefficients are applied.
6. Proceed with the print job normally.

---

## Interpreting Tilt Values

The tilt is reported as a slope: um of Z change per um of XY travel.

| Tilt Value | Z variation across 300 um field | Action |
|---|---|---|
| < 0.002 um/um | < 0.6 um | Acceptable for most applications; correction optional |
| 0.002–0.01 um/um | 0.6–3 um | Enable tilt correction for precision applications |
| 0.01–0.05 um/um | 3–15 um | Enable tilt correction; consider reseating the holder |
| > 0.05 um/um | > 15 um | Reseat substrate — tilt this large usually indicates a seating problem |

---

## Tilt Correction Cannot Fix Everything

Tilt correction addresses **linear tilt** — a single planar slope across the field. It cannot correct:

- **Substrate bow or warp** — if the substrate is curved rather than flat, the tilt correction (which fits a plane) will only partially compensate. Curved substrates require segmented printing with separate tilt measurements per zone.
- **Rough or uneven surfaces** — tilt correction models a smooth plane. Surface roughness at the nm scale is not corrected.
- **Dynamic tilt** — if the substrate shifts during a long print due to thermal drift, the tilt measurement taken at the start is no longer accurate.

---

## Related Files

- [piezo_scan_mode.md](./piezo_scan_mode.md)
- [galvo_scan_mode.md](./galvo_scan_mode.md)
- [05_Substrates/interface_detection_requirements.md](../05_Substrates/interface_detection_requirements.md)
- [06_Software_Workflow/NanoWrite_Software/sample_approach.md](../06_Software_Workflow/NanoWrite_Software/sample_approach.md)
