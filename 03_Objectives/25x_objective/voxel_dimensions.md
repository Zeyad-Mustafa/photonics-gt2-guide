# 📐 25× Objective — Voxel Dimensions

---

## Voxel Size

| Dimension | Size |
|---|---|
| Lateral (X/Y) | ~400 nm |
| Axial (Z) | ~1.5 µm |
| Aspect ratio (axial:lateral) | ~3.7 : 1 |

---

## Voxel Shape

```
Side view (to scale):

  ┌──────────┐
  │          │  ← 1.5 µm tall
  │          │
  └──────────┘
   ~400 nm wide

Compare to 63× (~160 nm × 500 nm) and 10× (~1.6 µm × 12 µm)
```

The 25× voxel has a reasonable aspect ratio — about 3.7:1. This means vertical surfaces have noticeable but fine stairstepping (~1.5 µm step height), which is acceptable for most applications but would be too coarse for precision optics.

---

## Minimum Feature Sizes (25×)

| Feature Type | Minimum Reliable Size |
|---|---|
| Wall thickness | ~1.5 µm |
| Pillar diameter | ~1 µm |
| Channel width | ~2 µm |
| Gap between features | ~2 µm |
| Layer height (practical) | ~0.5–1 µm |

---

## DeScribe Recommended Parameters (25× + IP-S)

| Parameter | Recommended Starting Value |
|---|---|
| Slice distance | 0.5–1 µm |
| Hatch distance | 0.3–0.5 µm |
| Laser power | 25–40% |
| Scan speed | 25,000–75,000 µm/s |
| Objective in DeScribe | Select "25×" from dropdown |

---

## Effect of Power and Speed

| Adjustment | Lateral Effect | Axial Effect |
|---|---|---|
| +10% laser power | +50–100 nm voxel growth | +200–400 nm voxel growth |
| −10% laser power | −50–100 nm voxel shrink | −200–400 nm voxel shrink |
| Halve scan speed | Equivalent to moderate power increase | Same |
| Double scan speed | Equivalent to moderate power decrease | Same |

Always calibrate with a test print (array of pillars or walls at varying power/speed) for your specific resin lot before printing critical structures.

---

> 🔗 Next: [dill_mode_explained.md](dill_mode_explained.md)