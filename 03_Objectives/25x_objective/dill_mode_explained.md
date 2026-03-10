# 💧 DiLL Mode — Dip-in Laser Lithography (25× Context)

---

## What Is DiLL?

**DiLL (Dip-in Laser Lithography)** is the primary printing mode of the GT2. The name describes exactly what happens: the objective lens physically **dips into** the liquid photoresin on the substrate.

In conventional microscopy, a lens focuses through a cover glass into a sample. In DiLL, there is no cover glass — the objective dips directly into the liquid resin, which acts as both the printing medium and the immersion fluid.

---

## Why DiLL Works Better Than Focusing Through Glass

```
Conventional (non-DiLL):          DiLL mode:

  Objective lens                   Objective lens
       │                                │
  ─────┴─────  ← glass               ▼ dips into
  ═════════════ ← resin          ~~~~~~~~~~~  ← liquid resin
                                  ─────────── ← substrate
```

In conventional mode, the laser must pass through:
1. The objective front element
2. Air gap (or immersion oil)
3. The glass substrate
4. Then into the resin

Each interface introduces reflections and aberrations. For high-NA objectives, focusing through glass introduces **spherical aberration** that blurs the focal volume and degrades resolution.

In DiLL mode, the only interfaces are:
1. Objective front element
2. Resin (continuous immersion from lens to substrate)
3. Substrate

This eliminates the glass-resin interface entirely, giving a sharper, smaller focal volume and better resolution.

---

## How DiLL Works With the 25× in Practice

1. Substrate sits in the holder with the **ITO side facing DOWN** (toward the objective)
2. A drop of IP-S resin sits on top of the ITO surface
3. When the stage raises the sample toward the objective, the objective **dips into the drop**
4. The resin fills the space between the front lens element and the substrate surface
5. The laser focuses through the resin directly to the substrate interface and into the resin above

---

## The Refractive Index Matching Requirement

For DiLL to work correctly, the resin's refractive index must be close to what the objective was designed for. The 25× DiLL objective is designed for:

- n ≈ 1.47–1.52 immersion medium (matches IP-series resins and glycerin)

This is why the **adjustment ring must be set to "Glyc"** — it corrects for the slight difference between the resin's refractive index and the design value.

---

## What Happens During the DiLL Approach

1. NanoWrite lowers the objective toward the sample
2. The objective tip contacts the resin drop and dips in
3. The **Interface Finder** scans for the substrate surface using reflected light intensity
4. When interference fringes appear → substrate surface found → Z=0 defined
5. Printing begins from this reference point upward into the resin

---

> 🔗 Next: [installation_steps.md](installation_steps.md)