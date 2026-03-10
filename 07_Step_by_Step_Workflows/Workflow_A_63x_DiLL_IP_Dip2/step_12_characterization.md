# Step 12 — Characterization

> Characterization is how you confirm the print succeeded, measure what you actually made, and generate the documentation that makes your work reproducible.

---

## Why This Step Matters

A print job that completes and a structure that meets your design specifications are two different things. Characterization closes the loop. It tells you whether your laser power, scan speed, slice distance, and hatch distance produced the intended result — and if not, exactly how to adjust them next time.

---

## Characterization Methods by Application

| Method | What It Reveals | Minimum Feature Visible |
|---|---|---|
| Optical microscopy (brightfield) | Overall shape, gross defects, development quality | ~1–2 um |
| Optical microscopy (DIC/Nomarski) | Surface topology, layer structure | ~500 nm |
| Scanning electron microscopy (SEM) | Fine feature dimensions, surface roughness, voxel boundaries | ~10 nm |
| Atomic force microscopy (AFM) | Surface roughness, height profiles | ~1 nm |
| Confocal fluorescence microscopy | Internal structure (if using fluorescent resist or staining) | ~200 nm |
| Profilometry | Height and step height measurements | ~10 nm (vertical) |

For most Workflow A structures (63x + IP-Dip2), optical microscopy first, followed by SEM for precision measurement, is the standard approach.

---

## Optical Microscopy — First Inspection

1. Place the substrate on an upright or inverted optical microscope stage.
2. Start at low magnification (5x or 10x) to locate the structure on the substrate.
3. Increase to 20x, 40x, or 100x depending on feature size.
4. Use brightfield for overall morphology. Use DIC (differential interference contrast) to reveal surface relief and layer structure.
5. Take calibrated images. Record the magnification, scale bar, and objective used.
6. Compare to your CAD model. Are the proportions correct? Are walls and features where they should be?

---

## SEM Imaging

For structures requiring dimensional measurement at the nanoscale:

1. The substrate may need to be sputter-coated with a thin (5–10 nm) conductive layer (gold, platinum, or carbon) if the substrate is non-conductive (glass) or if the polymer structure charges under the electron beam. Ask your SEM facility staff.
2. Load the sample into the SEM.
3. Image at progressively higher magnification.
4. Use the SEM measurement tool to measure critical dimensions and compare to design values.
5. Account for shrinkage: IP-Dip2 structures are typically 10–15% smaller than the designed dimensions. Document the actual shrinkage ratio for your specific parameters — this informs future design scaling.

---

## Documentation

For every print, record:

| Item | Record |
|---|---|
| Date and time | — |
| Objective | 63x |
| Resist | IP-Dip2, lot number |
| Substrate | Type, cleaning method |
| Laser power | % used in DeScribe |
| Scan speed | um/s |
| Slice distance | um |
| Hatch distance | um |
| Scan mode | Piezo or galvo |
| Development | PGMEA time, IPA rinse time |
| UV cure | Duration |
| Result | Pass/fail, measured dimensions, observations |

A structured lab notebook entry after each print will save significant time when troubleshooting or repeating the experiment.

---

## Related Files

- [troubleshooting.md](./troubleshooting.md)
- [13_Key_Parameters_Reference/feature_size_limits.md](../../13_Key_Parameters_Reference/feature_size_limits.md)
- [13_Key_Parameters_Reference/objective_specs_full_table.md](../../13_Key_Parameters_Reference/objective_specs_full_table.md)
