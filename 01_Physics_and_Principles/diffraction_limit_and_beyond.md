# 🌊 The Diffraction Limit — and How 2PP Breaks It

> One of the most remarkable things about the GT2 is that it routinely achieves feature sizes smaller than what classical optics says should be possible. This page explains the diffraction limit and the tricks that allow 2PP to go beyond it.

---

## What Is the Diffraction Limit?

When light passes through a circular aperture (like a lens), it doesn't form a perfect sharp point on the other side. Instead, it spreads out into a pattern of concentric rings called an **Airy disk** — this spreading is called **diffraction**.

No matter how perfect a lens you build, diffraction is a fundamental physical law. It sets a hard limit on how small a spot you can focus light to:

```
Rayleigh criterion (lateral):
  d_lateral = 0.61 × λ / NA

Rayleigh criterion (axial):
  d_axial = 2 × n × λ / NA²

Where:
  λ  = wavelength
  NA = numerical aperture of lens
  n  = refractive index of medium
```

For the GT2's 63× objective (NA = 1.4) at 780 nm:

```
d_lateral = 0.61 × 780 nm / 1.4 ≈ 340 nm
d_axial   = 2 × 1.515 × 780 nm / 1.4² ≈ 604 nm
```

These numbers are the classical diffraction limit — the smallest spot the optics can physically form. Classical lithography cannot cure a region smaller than this.

---

## Why 2PP Can Beat the Diffraction Limit

The GT2 routinely achieves **~160 nm lateral features** — less than half the 340 nm diffraction limit. How?

### The Threshold Effect

Polymerization does not occur at every point within the focal volume. It only occurs where the intensity **exceeds the polymerization threshold** of the resin.

```
Intensity profile across focal volume:

        │    ╭─────╮
        │   ╱       ╲
        │  ╱         ╲
 Thresh.│─╱─────────────╲──────────────  ← threshold line
        │╱               ╲
        └─────────────────────────────
                Position

        │←── Full focal ──→│
        │        volume

        │←─ Cured ─→│
            region
        (smaller than focal volume!)
```

By carefully tuning laser power to just barely exceed the threshold only at the very center of the focal volume, the cured region is **smaller than the focal spot itself**.

This is the key insight: **the cured voxel size is determined by where threshold is crossed, not by the total focal volume size.**

---

## The Quadratic Advantage (Again)

Recall from [one_photon_vs_two_photon_absorption.md](one_photon_vs_two_photon_absorption.md) that 2PA follows intensity²:

```
One-Photon:   Exposure ∝ I     (linear)
Two-Photon:   Exposure ∝ I²   (quadratic)
```

This quadratic relationship makes the effective exposure profile much sharper than the actual intensity profile:

```
Intensity profile (I):          Effective 2PP exposure (I²):

    ╭───────────────╮                  ╭──╮
   ╱                 ╲               ╱    ╲
  ╱                   ╲            ╱       ╲
 ╱                     ╲         ╱           ╲
╱                       ╲      ╱               ╲
───────────────────────────────────────────────

(wide, gradual Gaussian)         (narrower, sharper peak)
```

When you square the intensity distribution, the peak sharpens and the tails drop much faster. This gives 2PP an inherently sharper exposure profile than the physical focal spot.

---

## STED-Inspired Techniques (Advanced)

Some labs push 2PP even further using **stimulated emission depletion (STED)**-inspired concepts:

A second "depletion" beam is used alongside the writing beam. It suppresses polymerization in the outer ring of the focal volume, leaving only the very center active. This technique has demonstrated features below 100 nm with specialized resins.

This is not standard GT2 operation but shows how far 2PP can theoretically be pushed.

---

## Practical Limits vs Theoretical Limits

| Limit Type | Lateral | Axial |
|---|---|---|
| Classical diffraction (63×) | ~340 nm | ~604 nm |
| 2PP threshold effect | ~160 nm | ~500 nm |
| Theoretical (STED-2PP) | < 100 nm | < 200 nm |
| Practical stable feature | ~400–500 nm | ~500–800 nm |

Note: The **practical stable feature** is larger than the theoretical minimum because:
- Very small features collapse during development (solvent forces)
- Adhesion to substrate becomes unreliable at sub-200 nm
- Resin shrinkage distorts features below ~500 nm

---

## Resolution vs Print Volume Trade-off

You cannot have maximum resolution AND large build volume at the same time. Higher NA objectives that give better resolution have shorter working distances and smaller print fields:

```
Resolution vs Volume trade-off:

High resolution │ 63× ●
                │      \
                │       \
                │        ● 25×
                │         \
                │          \
Low resolution  │           ● 10×
                └────────────────
               Small            Large
                       Print Volume
```

This is a fundamental physical constraint. Choose your objective based on which matters more for your specific application.

---

## Summary

| Concept | Key Point |
|---|---|
| Diffraction limit | Fundamental optical law: minimum spot ≈ 0.61λ/NA |
| GT2 diffraction limit (63×) | ~340 nm lateral, ~604 nm axial |
| How 2PP beats it | Polymerization threshold + quadratic I² exposure |
| Achieved minimum (GT2) | ~160 nm lateral, ~500 nm axial |
| Cost of high resolution | Smaller build volume, slower printing |

---

> 🔗 **Next:** [Polymerization Chemistry →](polymerization_chemistry.md)