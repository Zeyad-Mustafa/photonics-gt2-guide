# Print Taking Too Long

> DeScribe estimates 12 hours. The machine is booked for 4. Or the print started 8 hours ago and is 30% done. This file explains what drives print time and how to reduce it.

---

## Why 2PP Printing Is Slow

Every voxel in the structure must be individually exposed by the laser. Unlike inkjet or FDM printing (which deposits material) or SLA (which exposes an entire layer at once with a projector), 2PP traces every point serially. Print time scales directly with the number of voxels and inversely with scan speed.

For a 200 x 200 x 100 um structure at 0.5 um slice distance and 0.3 um hatch distance:
- Number of layers: 200
- Lines per layer: ~667
- Time per line: depends on scan speed and line length
- Total scan length: approximately 267 mm
- At 10 mm/s (piezo): ~26,700 seconds = 7.4 hours
- At 100 mm/s (galvo): ~2,670 seconds = 45 minutes

The choice of scan mode (piezo vs. galvo) is the single largest factor in print time.

---

## How to Estimate Print Time Before Committing

Always check the estimated print time in DeScribe after slicing, before generating the GWL file. DeScribe shows this in the slice output summary. Do not load a job without checking this first.

If the estimate is longer than your booking allows, use the fixes below before generating GWL.

---

## Fixes — Ordered by Impact

### Fix 1 — Switch to Galvo Scan Mode

This is the highest-impact change available. Galvo scan runs at 50,000–100,000 um/s versus piezo's typical 10,000–50,000 um/s. For the same structure:

| Mode | Typical speed | Approximate time ratio |
|---|---|---|
| Piezo | 10,000–20,000 um/s | 1x (baseline) |
| Galvo | 50,000–100,000 um/s | 5–10x faster |

Switch to galvo mode in DeScribe if your structure fits within the 400 x 400 um galvo field and your application does not require < 1 um positional accuracy. This is the correct scan mode for the 25x and 10x objectives in most cases.

---

### Fix 2 — Increase Slice Distance

Slice distance is the Z step between layers. Halving the number of layers halves the print time for Z-dominated structures.

| Objective | Minimum slice | Standard slice | Coarse slice |
|---|---|---|---|
| 63x | 0.3 um | 0.5 um | 1.0 um |
| 25x | 0.5 um | 1.0 um | 2.0 um |
| 10x | 1.0 um | 2.0 um | 5.0 um |

Increasing slice distance reduces Z resolution but does not significantly affect XY resolution. If your structure does not require fine vertical detail, use the coarse slice value.

---

### Fix 3 — Increase Hatch Distance

Hatch distance is the spacing between scan lines within each layer. Wider hatch = fewer scan lines per layer = faster print.

For the 25x + IP-S at standard 0.5 um hatch: doubling to 1.0 um hatch reduces scan lines per layer by 50%. The resulting structure will have a slightly coarser surface finish, but for most mechanical and biological structures this is acceptable.

Maximum recommended hatch distance: approximately 60–70% of the voxel diameter. At 25x, voxels are approximately 500 nm wide, so maximum useful hatch is ~300–350 nm. Beyond this, the scan lines do not overlap and the structure will have visible gaps.

---

### Fix 4 — Use Scaffold and Shell Printing Instead of Solid Infill

For solid bulk structures, the interior does not need to be fully solid. A scaffold (sparse internal lattice) or shell (outer skin only, hollow interior) provides mechanical integrity with a fraction of the printed volume:

| Infill strategy | Material printed | Time vs. solid |
|---|---|---|
| Solid (100% fill) | All voxels | 1x |
| Shell + sparse scaffold | ~20–40% | 0.2–0.4x |
| Shell only | ~5–15% | 0.05–0.15x |

In DeScribe, enable the scaffold/shell option and set the shell thickness (typically 5–15 um) and scaffold density. After printing and development, UV flood cure for 20 minutes to ensure complete polymerization of the shell.

---

### Fix 5 — Reduce the Structure Volume

If the structure is larger than required, scale it down in DeScribe before slicing. A structure that is 10% smaller in each dimension prints in approximately 73% of the original time (0.9^3 = 0.729).

If you need a large structure but it does not need to be a single print, split it into multiple smaller prints using stitching.

---

### Fix 6 — Increase Scan Speed

Increasing scan speed reduces dose per voxel. If the current parameters are over-exposing (bloated features, structure larger than CAD dimensions), scan speed can be increased while maintaining adequate polymerization. Increase speed in 20% increments and evaluate with a calibration structure.

Do not increase scan speed beyond the point where features are under-exposed (voids or incomplete polymerization appear).

---

## Print Time Reference

Approximate print times for common structure sizes (25x, galvo, 1.0 um slice, 0.5 um hatch):

| Structure size | Approx. print time |
|---|---|
| 100 x 100 x 50 um | 5–15 minutes |
| 200 x 200 x 100 um | 20–40 minutes |
| 400 x 400 x 200 um | 1.5–3 hours |
| 400 x 400 x 400 um | 3–6 hours |
| > 400 x 400 um (stitched) | Add ~20 min per additional field |

---

## Related Files

- [09_Printing_Modes/galvo_scan_mode.md](../09_Printing_Modes/galvo_scan_mode.md)
- [09_Printing_Modes/piezo_scan_mode.md](../09_Printing_Modes/piezo_scan_mode.md)
- [08_Development_and_Post_Processing/scaffold_and_shell_printing.md](../08_Development_and_Post_Processing/scaffold_and_shell_printing.md)
- [06_Software_Workflow/DeScribe_Software/slicing_parameters.md](../06_Software_Workflow/DeScribe_Software/slicing_parameters.md)
