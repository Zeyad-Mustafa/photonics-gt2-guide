# 📐 10× Objective — Voxel Dimensions

---

## Voxel Size

| Dimension | Size |
|---|---|
| Lateral (X/Y) | ~1.6 µm |
| Axial (Z) | ~12 µm |
| Aspect ratio (axial:lateral) | ~7.5 : 1 |

The 10× has by far the **largest aspect ratio** of all GT2 objectives. Its voxels are very tall relative to their width. This has significant design implications.

---

## What the Large Aspect Ratio Means for Your Designs

```
10× voxel shape (to scale):

Side view:
┌──┐
│  │
│  │
│  │
│  │  ← 12 µm tall
│  │
│  │
│  │
└──┘
1.6µm

Compare to 63× voxel:
┌─┐
└─┘
160nm × 500nm
```

**Consequences:**
- Vertical surfaces (walls parallel to Z axis) will show visible stairstepping at ~12 µm intervals
- Horizontal surfaces (floors and ceilings) are smooth — the lateral voxel controls these
- Very tall thin pillars (height:width > 5:1) are unreliable — the large axial voxel means each layer overlaps heavily with the next

---

## How Power and Speed Affect Voxel Size

Voxel size is not fixed — it varies with your laser settings:

| Setting | Effect on Lateral Voxel | Effect on Axial Voxel |
|---|---|---|
| Increase laser power | Grows (more of focal volume exceeds threshold) | Grows significantly |
| Decrease laser power | Shrinks | Shrinks |
| Decrease scan speed | Grows | Grows |
| Increase scan speed | Shrinks | Shrinks |

For the 10× objective, **axial voxel size is particularly sensitive to power**. Even small increases in laser power can significantly increase the axial dimension, causing layer merging and loss of Z-resolution.

---

## Minimum Printable Feature Sizes (10×)

| Feature Type | Minimum Size |
|---|---|
| Wall thickness | ~5 µm |
| Pillar diameter | ~4 µm |
| Gap / channel width | ~5 µm |
| Layer height (practical) | ~3–6 µm |
| Minimum overhang span | ~20 µm |

---

## DeScribe Recommended Parameters (10× + IP-Q)

| Parameter | Recommended Starting Value |
|---|---|
| Slice distance | 1–3 µm |
| Hatch distance | 0.8–2 µm |
| Laser power | 35–60% |
| Scan speed | 50,000–100,000 µm/s |
| Objective in DeScribe | Select "10×" from dropdown |

Always run a **calibration test print** with your specific resin lot before starting a critical structure — these values are starting points only.

---

> 🔗 Next: [print_field_and_limits.md](print_field_and_limits.md)