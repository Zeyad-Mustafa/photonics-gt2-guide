# 📐 63× Objective — Voxel Dimensions

---

## Voxel Size

| Dimension | Size |
|---|---|
| Lateral (X/Y) | ~160 nm |
| Axial (Z) | ~500 nm |
| Aspect ratio (axial:lateral) | ~3.1 : 1 |

The 63× has the **smallest voxel and best aspect ratio** of all GT2 objectives. Its ~3:1 aspect ratio means vertical surfaces are relatively smooth — step heights of only ~500 nm between layers.

---

## Minimum Feature Sizes (63×)

| Feature Type | Minimum Reliable Size |
|---|---|
| Wall thickness | ~400–500 nm |
| Isolated pillar diameter | ~300–400 nm |
| Gap / trench width | ~400 nm |
| Layer height (practical) | ~200–400 nm |
| Overhang span (unsupported) | ~5–10 µm |

---

## DeScribe Recommended Parameters (63× + IP-Dip2)

| Parameter | Recommended Starting Value |
|---|---|
| Slice distance | 0.3–0.5 µm |
| Hatch distance | 0.2–0.4 µm |
| Laser power | 15–30% |
| Scan speed | 10,000–25,000 µm/s |
| Objective in DeScribe | Select "63×" from dropdown |

**Note:** The 63× requires significantly lower laser power than the 25× or 10× because the tighter focal volume creates much higher intensity at the same power setting. Starting too high will cause severe overexposure.

---

## Power Calibration Strategy

Because the 63× + IP-Dip2 combination is the most sensitive in the GT2 lineup, always begin with a **power sweep test print**:

1. Design a simple test structure: array of 10 µm × 10 µm × 5 µm blocks
2. Print the array at powers from 10% to 35% in 2.5% steps
3. Develop and inspect under SEM or optical microscope
4. Choose the power that gives clean, well-defined edges without blooming

This calibration takes ~30 minutes and saves hours of failed prints.

---

> 🔗 Next: [fiber_ring_installation.md](fiber_ring_installation.md)