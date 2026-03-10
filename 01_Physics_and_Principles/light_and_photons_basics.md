# 💡 Light and Photons — The Basics

> Everything in the GT2 starts with light. This page explains exactly what light is, what a photon is, and why wavelength matters — in plain English.

---

## What Is Light?

Light is a form of **electromagnetic radiation** — energy that travels as a wave through space. It doesn't need air or any medium to travel (it moves through the vacuum of space at 300,000 km/s).

What makes different types of light different from each other is their **wavelength** — the distance between one wave peak and the next.

```
Short wavelength = high energy = UV / X-ray
Long wavelength  = low energy  = infrared / radio
```

The human eye can only detect wavelengths between roughly **380 nm** (violet) and **700 nm** (red). Everything outside that range is invisible to us.

---

## The Electromagnetic Spectrum

```
← Higher Energy                                    Lower Energy →
← Shorter Wavelength                          Longer Wavelength →

 X-ray    UV      Visible      NIR       IR       Microwave
  │        │    ┌──────────┐    │         │           │
  │        │    │ 380–700nm│    │         │           │
  │        │    └──────────┘    │         │           │
 0.01nm  100nm  380nm  700nm  780nm     1000nm      1cm

                              ▲
                      GT2 laser is here
                         (780 nm, NIR)
```

The GT2 uses **780 nm near-infrared (NIR) light** — just beyond what your eye can see. This wavelength is special because:
1. It passes through most optical resins **without reacting** with them (too low energy for one-photon absorption)
2. It can be focused to an extremely tight spot
3. It is safe to work with compared to UV lasers (though still Class IV — see Safety section)

---

## What Is a Photon?

Light behaves both as a wave and as a stream of tiny energy packets called **photons**. Each photon carries a fixed amount of energy that depends on its wavelength:

```
Energy of a photon = h × c / λ

Where:
  h = Planck's constant (6.626 × 10⁻³⁴ J·s)
  c = speed of light (3 × 10⁸ m/s)
  λ = wavelength

Shorter wavelength → Higher energy photon
Longer wavelength  → Lower energy photon
```

You don't need to memorize this formula. The key takeaway:

> **A 780 nm photon (NIR) carries exactly HALF the energy of a 390 nm photon (UV)**

This is the entire basis of Two-Photon Polymerization — if two 780 nm photons arrive at the same molecule simultaneously, together they provide the same energy as one 390 nm UV photon.

---

## Why Does Wavelength Affect Resolution?

When you focus a beam of light through a lens, you can never focus it to a perfect point. The smallest spot you can achieve is limited by the wavelength itself — this is called the **diffraction limit**.

The formula (simplified):

```
Minimum spot size ≈ λ / (2 × NA)

Where:
  λ = wavelength
  NA = numerical aperture of the objective
```

This means:
- Shorter wavelength → smaller spot → better resolution
- Higher NA → smaller spot → better resolution

This seems to suggest UV light (shorter wavelength) would give better resolution than NIR. And for one-photon processes, that's true. But 2PP changes the game entirely — more on this in [diffraction_limit_and_beyond.md](diffraction_limit_and_beyond.md).

---

## Intensity vs Energy

Two important concepts that often get confused:

**Energy** = total amount of light delivered (like total water in a bucket)
**Intensity** = energy delivered per unit area per unit time (like water pressure from a hose)

The 2PP process depends on **intensity** — specifically, getting an extremely high intensity at one tiny point for an extremely short time. This is achieved by:
1. Focusing the beam tightly (small area)
2. Compressing the energy into ultrashort pulses (short time)

Both together create peak intensities at the focal point that are billions of times higher than the average beam intensity — enough to trigger two-photon absorption.

---

## Summary

| Concept | Key Point |
|---|---|
| Wavelength | Determines photon energy; GT2 uses 780 nm NIR |
| Photon | Smallest packet of light energy |
| 780 nm photon energy | Half of a 390 nm UV photon |
| Diffraction limit | Minimum spot size ≈ λ / (2 × NA) |
| Intensity | What triggers 2PP — not total energy, but energy per area per time |

---

> 🔗 **Next:** [One-Photon vs Two-Photon Absorption →](one_photon_vs_two_photon_absorption.md)