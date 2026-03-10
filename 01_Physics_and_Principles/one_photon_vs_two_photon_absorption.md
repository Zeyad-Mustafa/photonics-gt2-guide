# ☀️ One-Photon vs Two-Photon Absorption

> This is the most important concept in the entire guide. Understanding this explains everything about why the GT2 can print at nanoscale resolution.

---

## One-Photon Absorption (How Regular Light Works)

In standard photolithography and UV resin printing, a **single photon** of UV light hits a photoinitiator molecule and gives it enough energy to start a chemical reaction (polymerization).

```
ONE UV photon (390 nm, high energy)
        +
Photoinitiator molecule
        =
Chemical reaction → polymerization
```

This works, but has a critical problem:

> **UV light reacts with the resin everywhere it travels — not just at the focal point.**

When a UV beam enters the resin, it starts curing material the moment it enters. By the time it reaches the intended focal point, it has already cured a column of material above it. You cannot selectively cure just one point inside a 3D volume.

This limits UV-based methods to **surface or layer-by-layer** printing, never true 3D.

---

## The Probability Problem

Absorption of one photon follows a **linear** relationship with intensity:

```
Absorption rate ∝ Intensity¹

Double the intensity → double the absorption
```

This means: wherever the beam has any intensity at all (which is everywhere along its path), some absorption occurs. You cannot restrict it to just the focal point.

---

## Two-Photon Absorption (How the GT2 Works)

Two-Photon Absorption (2PA) is a fundamentally different process:

```
TWO NIR photons (780 nm, low energy each)
arrive at the SAME MOLECULE at the SAME TIME
        +
Photoinitiator molecule
        =
Combined energy = equivalent to one UV photon
        =
Chemical reaction → polymerization
```

The key word is **simultaneously** — both photons must arrive within roughly 10⁻¹⁵ seconds of each other (a femtosecond timescale). If they arrive even slightly apart, no reaction occurs.

---

## Why This Gives 3D Resolution

Two-photon absorption follows a **quadratic** relationship with intensity:

```
Absorption rate ∝ Intensity²

Double the intensity → FOUR TIMES the absorption
Half the intensity → ONE QUARTER the absorption
```

This quadratic dependence is the key to everything.

At the focal point: intensity is maximum → absorption rate is very high → polymerization happens

Just outside the focal point: intensity drops rapidly → absorption rate drops by the SQUARE of that reduction → essentially zero polymerization

```
VISUALIZATION:

One-Photon (UV):          Two-Photon (NIR):
                                
█████████████████         ░░░░░░░░░░░░░░░░░
█████████████████         ░░░░░░░░░░░░░░░░░
█████████████████    vs   ░░░░░░▓▓▓░░░░░░░░
█████████████████         ░░░░░░░░░░░░░░░░░
█████████████████         ░░░░░░░░░░░░░░░░░

Reacts everywhere         Reacts ONLY at focal point
```

This is why the GT2 can cure a voxel inside a 3D volume of liquid resin without curing anything above or below it.

---

## The Threshold Effect

Another crucial property of 2PP: it has a **polymerization threshold**.

```
              │
Polymerization│                    ████ Cured region
   rate       │                 ▄▄▄
              │              ▄▄▄
              │           ▄▄▄
──────────────┼────────▄▄▄──────────────────
 Threshold ──►│      ▄▄▄
              │   ▄▄▄
              └─────────────────────────────
                        Intensity
```

Below the threshold → no curing (even with some two-photon events)
Above the threshold → rapid, complete polymerization

This threshold can be exploited to print features **smaller than the diffraction limit** — by using just enough laser power to exceed the threshold only at the very center of the focal volume (where intensity is highest), the effective cured spot is smaller than the full focal volume.

---

## Side-by-Side Comparison

| Property | One-Photon (UV) | Two-Photon (NIR) |
|---|---|---|
| Wavelength | 365–405 nm (UV) | 780 nm (NIR) |
| Photons needed | 1 | 2 (simultaneous) |
| Absorption law | Linear (∝ I) | Quadratic (∝ I²) |
| 3D selectivity | ❌ None | ✅ Excellent |
| Resolution | ~1–10 µm | ~160 nm |
| True 3D printing | ❌ No | ✅ Yes |
| Penetration depth | Limited (absorbs in UV) | Deep (resin transparent to NIR) |
| Laser type needed | CW or pulsed UV | Femtosecond pulsed NIR |

---

## Why Femtosecond Pulses Are Essential

For two photons to arrive at the same molecule simultaneously, you need an **extremely high instantaneous intensity** — so high that the probability of two photons hitting the same molecule within a femtosecond becomes significant.

This is achieved not by increasing average power (which would heat and damage the sample) but by compressing all the energy into incredibly short pulses:

```
Average power:  ~50 mW (safe, low)
Pulse duration: 100 femtoseconds
Repetition:     80 MHz

Peak power during pulse = Average power / (pulse duration × repetition rate)
                        = 0.05 / (100×10⁻¹⁵ × 80×10⁶)
                        ≈ 6,250 W peak power during each pulse
```

That 6,250 W exists only for 100 femtoseconds — then nothing until the next pulse. The sample never heats up because the average power is only 50 mW. But during each pulse, the intensity at the focal point is high enough to guarantee two-photon events.

---

## Summary

| Concept | Key Point |
|---|---|
| 1PA | Linear absorption — reacts everywhere light travels |
| 2PA | Quadratic absorption — reacts ONLY at focal point |
| Why quadratic helps | Intensity drops fast → absorption drops even faster outside focus |
| Threshold effect | Only very center of focal volume cures → sub-diffraction features |
| Why femtosecond pulses | Creates extreme peak intensity without heating the sample |

---

> 🔗 **Next:** [Femtosecond Laser Explained →](femtosecond_laser_explained.md)