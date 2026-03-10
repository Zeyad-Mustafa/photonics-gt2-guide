# 📏 10× Objective — Print Field and Limits

---

## Print Field

| Scan Mode | Field Size |
|---|---|
| Galvo scanning | 400 × 400 µm per field |
| Piezo scanning | 300 × 300 × 300 µm |
| Total addressable area (stage) | 100 × 100 mm |
| Max structure height (WD limit) | ~700 µm |
| Max practical structure volume | ~10 mm³ |

For structures larger than 400×400 µm in XY, the GT2 automatically **stitches multiple fields** together by moving the coarse stage between exposures. The 10× is the best objective for stitched large-area prints because its large voxels make stitching seams less visible.

---

## Stitching

When your structure is wider than 400 µm, DeScribe automatically splits it into a grid of 400×400 µm tiles. The stage moves between tiles and prints each one sequentially.

**Stitching considerations for the 10×:**
- Stitching errors (misalignment between tiles) are ~100–200 nm — invisible at 10× voxel scale (~1.6 µm)
- Very large arrays (e.g. 5×5 mm) are practical with the 10× — they would be impractical with 63×
- Ensure the substrate is flat across the entire print area — height variations > 50 µm may cause focus drift between tiles

---

## Hard Limits

| Limit | Value | Reason |
|---|---|---|
| Max height | 700 µm | Working distance of objective |
| Min feature | ~5 µm | Voxel size limit |
| Min wall thickness | ~5 µm | Stability + voxel size |
| Max volume (practical) | ~10 mm³ | Print time becomes days above this |
| Substrate size | 25×25 mm | Sample holder constraint |

---

> 🔗 Next: [installation_steps.md](installation_steps.md)