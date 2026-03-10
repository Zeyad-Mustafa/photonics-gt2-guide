# ⚡ What Is Two-Photon Polymerization (2PP)?

> **Plain English first, science second.** This file explains the core technology behind the GT2 without assuming any prior knowledge.

---

## The Simple Version

Imagine you have a swimming pool filled with a special liquid. Normally, light passing through the liquid does nothing to it. But if you focus a very powerful laser to a **tiny single point** inside the liquid, something magical happens — the liquid turns solid **only at that exact point**, and nowhere else.

That's Two-Photon Polymerization. The GT2 uses this trick to "draw" 3D objects inside a liquid resin, point by point, layer by layer, from the bottom up.

---

## Why "Two-Photon"?

A **photon** is the smallest possible packet of light energy.

Most light-sensitive materials (like the resin in the GT2) react when they absorb **one photon** of high-energy UV light. The problem is UV light scatters everywhere — you can't focus it to a tiny point without curing a big blob of material.

The GT2 uses a clever trick instead:
- It uses **near-infrared (NIR) light** at 780 nm wavelength — this is invisible, low-energy light that normally does **nothing** to the resin
- The laser fires in ultra-short bursts (**100 femtosecond pulses** — a femtosecond is 0.000000000000001 seconds)
- At the focal point, the intensity is so extreme that **two photons arrive simultaneously** at the same molecule
- Together, those two photons have enough energy to trigger a chemical reaction — **polymerization**
- Outside the focal point, the light is too weak for two photons to ever arrive at the same time → **nothing happens**

This is why 2PP achieves resolutions far beyond what regular UV lithography can do.

---

## What Is Polymerization?

**Polymerization** is a chemical reaction where small molecules (called **monomers**) link together into long chains (called **polymers**).

Think of it like snapping LEGO bricks together:
- Before: loose individual bricks = liquid monomer
- After: a connected structure = solid polymer

The GT2's resin is a **photopolymer** — it only polymerizes when it receives enough light energy. The 2PP trick ensures that energy is delivered only at one tiny point in 3D space.

---

## The Focal Volume = The Voxel

The tiny 3D region where polymerization occurs is called a **voxel** (Volume + Pixel = Voxel).

- The voxel is **egg-shaped** (elongated in the vertical direction)
- Its size depends on the objective lens you use
- With the 63× objective: ~160 nm wide × ~500 nm tall
- With the 10× objective: ~1 µm wide × ~3 µm tall

By moving the focal point through the resin in a programmed path, the GT2 builds up your 3D structure voxel by voxel.

---

## Step-by-Step: What Happens During a Print

```
1. Liquid resin sits on a substrate (glass, silicon, etc.)
2. The objective lens focuses the laser beam inside the resin
3. At the focal point → two photons absorbed simultaneously → polymerization
4. A tiny solid voxel forms at that point
5. The stage moves the focal point to the next position
6. Thousands to millions of voxels are written in a programmed path
7. After printing → the sample is washed in solvent (development)
8. The unsolidified liquid resin washes away
9. Only your 3D solid structure remains
```

---

## Why Is This Better Than Regular 3D Printing?

| Feature | Regular 3D Printer (FDM) | GT2 (2PP) |
|---|---|---|
| Smallest feature | ~100 µm | ~160 nm |
| Resolution | Low | Extremely high |
| Materials | Plastic filament | Specialized liquid resins |
| 3D freedom | Layer-by-layer, visible steps | True smooth 3D, no layer lines |
| Speed | Fast for large objects | Slow for large objects |
| Applications | Prototypes, models | Optics, MEMS, biology, photonics |

---

## Key Numbers to Remember

| Parameter | Value |
|---|---|
| Laser wavelength | 780 nm (near-infrared) |
| Pulse duration | 100 femtoseconds |
| Pulse repetition rate | 80 MHz |
| Minimum feature size | ~160 nm (lateral) |
| Minimum voxel height | ~500 nm (axial) |

---

> 🔗 **Next:** [One-Photon vs Two-Photon Absorption →](../01_Physics_and_Principles/one_photon_vs_two_photon_absorption.md)