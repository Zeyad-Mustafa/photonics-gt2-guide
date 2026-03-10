# 🔄 25× Objective — Adjustment Ring Guide

> This is one of the most commonly missed steps for new GT2 users. An incorrectly set adjustment ring will silently ruin your print quality without any obvious error message.

---

## What Is the Adjustment Ring?

The 25× objective has a rotating collar near its base called the **correction collar** or **adjustment ring**. It compensates for spherical aberration introduced when focusing through different media (air, water, glycerin, oil).

In DiLL mode, the objective dips directly into the IP-series resin. The resin has a refractive index close to glycerin (n ≈ 1.47–1.48). Therefore the ring must be set to the **glycerin position**.

---

## How to Set It Correctly

### The Ring Scale

The ring has a scale with markings. You are looking for the position labeled **"Glyc"** or the equivalent position marked with the **3 longest bars** on the scale:

```
Ring scale (schematic):

  Water  Glyc   Oil
    │      │     │
────┼──┬───┼──┬──┼────
    │  │   │  │  │
   short  LONG short
   bars   bars  bars

                ▲
         Set ring HERE
         (3 longest bars = Glyc)
```

### Step-by-Step

1. Hold the objective body firmly
2. Locate the rotating adjustment ring (it's the collar that can spin independently)
3. Rotate it until the line on the ring aligns with **"Glyc"** or the **longest-bar position**
4. You should feel slight detents (clicks) at each position — "Glyc" has a clear click
5. Confirm visually before installing the objective

---

## What Happens If Set Wrong

| Ring Position | Effect |
|---|---|
| Correct (Glyc) | Sharp focus, correct voxel size, good interface detection |
| Too low (Water) | Undercorrected spherical aberration → blurry voxels, larger axial size |
| Too high (Oil) | Overcorrected → voxels distorted, structures appear stretched vertically |
| Random position | Unpredictable print quality, failed interface detection |

---

## Check This Every Session

The ring can accidentally rotate during handling or storage. **Check it every time you install the 25×** — even if you used it correctly last time.

---

> 🔗 Next: [compatible_resists.md](compatible_resists.md)