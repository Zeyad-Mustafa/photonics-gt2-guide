# 🔵 Voxel Formation — The Building Block of Every GT2 Print

> Every structure the GT2 ever prints — from a microscopic lens to a swimming microrobot — is made of millions of overlapping voxels. Understanding what a voxel is and how it forms is the foundation of understanding print quality.

---

## What Is a Voxel?

**Voxel = Volume + Pixel**

Just as a pixel is the smallest unit of a 2D image, a voxel is the smallest unit of a 3D printed object. In the GT2, one voxel is the tiny region of polymerized material created by a single stationary laser exposure at the focal point.

Every 3D structure you print is built by writing millions of these voxels in a programmed path, overlapping each other slightly, until the full shape is filled in.

---

## The Shape of a Voxel

A GT2 voxel is **not a sphere** — it is shaped like a **prolate ellipsoid** (like a rugby ball or an egg standing upright):

```
        Side view:              Top view:
        
           │                      
        ───┼───  ← narrow         ●  ← circular
           │     (lateral)
        ───┼───                   
           │                      
        ─────── ← wide         (symmetric)
        ───────   (axial)
        ─────── 
        ───────
        ───────
```

**Lateral dimension (X, Y):** The narrow width — this is the resolution in the horizontal plane
**Axial dimension (Z):** The elongated height — always larger than the lateral dimension

---

## Why Is the Axial Dimension Always Larger?

This comes from the physics of how a lens focuses light. Even a perfect lens cannot focus light to a perfect point — it creates a **focal volume** that is elongated along the beam axis.

The mathematical relationship:

```
Lateral resolution  ≈  0.61 × λ / NA
Axial resolution    ≈  2 × λ × n / NA²

Where:
  λ  = wavelength (780 nm)
  NA = numerical aperture
  n  = refractive index of immersion medium
```

Because NA appears **squared** in the axial formula but only to the first power in the lateral formula, the axial dimension is always significantly larger — typically **3–4× larger** than the lateral dimension.

---

## Voxel Sizes by Objective

| Objective | NA | Lateral Voxel (approx.) | Axial Voxel (approx.) | Aspect Ratio |
|---|---|---|---|---|
| 63× (oil immersion) | 1.4 | ~160 nm | ~500 nm | ~3:1 |
| 25× (immersion) | 0.8 | ~400 nm | ~1.5 µm | ~3.7:1 |
| 10× (immersion) | 0.3 | ~1.6 µm | ~12 µm | ~7.5:1 |

Notice that the 10× objective has a much worse aspect ratio — its voxels are very tall and relatively narrow. This limits fine vertical resolution at large scales.

---

## What Controls Voxel Size?

### 1. Objective (NA)
Higher NA → smaller, rounder voxels → better resolution. This is the most important factor and cannot be changed without swapping objectives.

### 2. Laser Power
More power → larger effective voxel (because more of the surrounding focal volume exceeds the polymerization threshold).

```
Low power:   ●  (small voxel — only center exceeds threshold)
Med power:   ◉  (normal voxel)
High power:  ⬤  (large voxel — large region exceeds threshold)
```

### 3. Scan Speed
Slower speed → focal point spends more time at each position → more cumulative exposure → effectively larger voxel.

### 4. Resin Properties
Different resins have different polymerization thresholds and sensitivities. IP-Dip2 is more sensitive than IP-Q, so it achieves finer voxels at lower power.

---

## Voxel Overlap — How Structures Are Built

Individual voxels are written in overlapping lines and layers to build solid structures:

```
Hatch pattern (top view):           Layer stack (side view):

→→→→→→→→→→→→→→→                    Layer 3: ══════════
←←←←←←←←←←←←←←                    Layer 2: ══════════
→→→→→→→→→→→→→→→                    Layer 1: ══════════
←←←←←←←←←←←←←←                    Substrate
```

**Hatch distance** = spacing between scan lines in X/Y (set in DeScribe)
**Slice distance** = spacing between layers in Z (set in DeScribe)

If hatch/slice distance is too large → gaps between voxels → porous, weak structure
If hatch/slice distance is too small → excessive overlap → over-curing, loss of detail, slow print

Typical overlap for solid structures: **50–70% voxel diameter**

---

## The Voxel and Feature Size

The minimum printable feature size is NOT exactly equal to the voxel size. It also depends on:

- **Structure geometry:** Isolated pillars need ~2× voxel width to be stable
- **Aspect ratio:** Very tall thin pillars (height:width > 10:1) tend to collapse during development
- **Resin shrinkage:** Voxels shrink 5–15% during and after polymerization — design slightly oversized
- **Development:** Solvent flow can push over sub-micron features if they are isolated

**Practical minimum feature sizes (stable, free-standing):**

| Objective | Min wall thickness | Min pillar diameter |
|---|---|---|
| 63× | ~500 nm | ~400 nm |
| 25× | ~1.5 µm | ~1 µm |
| 10× | ~5 µm | ~4 µm |

---

## Voxel Engineering — Using Voxel Shape to Your Advantage

Because voxels are elongated vertically, certain orientations print better than others:

**Design your structure so critical dimensions are in the lateral (XY) plane** — that's where resolution is best.

For example:
- A horizontal channel (opening facing sideways) → use lateral dimension for channel width ✅
- A vertical channel (opening facing up) → axial dimension limits depth accuracy ⚠️

Also useful: by tilting the print orientation in DeScribe, you can align your most critical features with the lateral axis.

---

## Summary

| Property | Key Point |
|---|---|
| Shape | Prolate ellipsoid (egg-shaped) |
| Lateral size | Smaller — determines XY resolution |
| Axial size | Larger — always 3–8× bigger than lateral |
| Controls size | Objective NA, laser power, scan speed, resin |
| Building principle | Overlapping voxels in a hatch pattern |
| Practical minimum | ~500 nm wall (63×), ~1.5 µm wall (25×) |

---

> 🔗 **Next:** [Diffraction Limit and Beyond →](diffraction_limit_and_beyond.md)