# Inverted Immersion Mode

> Inverted immersion mode combines the optical performance of a high-NA objective with spin-coated resist layers. It is used when you need better resolution or 3D capability than air mode provides, but your resist must be spin-coated rather than drop-cast.

---

## What Inverted Immersion Mode Is

Inverted immersion mode uses the **25x or 63x objective** with a liquid immersion medium (oil or water) between the objective and the substrate, while the resist is on the **top surface** of the substrate as a spin-coated film.

```
        [ spin-coated resist ]    <- i-line or IP-series thin film on top
        [    substrate       ]    <- glass or silicon
        [ immersion medium   ]    <- oil (63x) or glycerol (25x) or water
        [ objective tip      ]    <- 25x or 63x, pointing up
              |
         laser beam
         (from below)
```

This is geometrically similar to oil immersion mode, but the resist is a solid film rather than a liquid pool, and the objective used can be the 25x (not just the 63x).

The name "inverted immersion" distinguishes this from standard DiLL (where the objective is in the resist) and from oil immersion (where the objective is in oil and the resist is a liquid pool above the glass).

---

## When to Use Inverted Immersion Mode

Inverted immersion is appropriate when:

| Situation | Detail |
|---|---|
| Resist must be spin-coated | Some applications require uniform, controlled-thickness resist films that cannot be formed by drop casting |
| Higher resolution than air mode | NA 0.8 (25x) or NA 1.4 (63x) gives smaller voxels than air mode (NA 0.5) |
| Limited 3D depth in thin film | Film is typically 1–20 um thick; freeform 3D is possible within this range |
| Compatibility with existing wafer process | Spin-coated substrates from a clean room process can be loaded directly |

---

## Immersion Media by Objective

| Objective | Immersion Medium | Application |
|---|---|---|
| 25x | Glycerol (or glycerol-water mixture, n ~ 1.45) | Spin-coated IP-series or i-line resists |
| 63x | Zeiss Immersol 518F (oil, n = 1.518) | Highest resolution on spin-coated substrates |

For the 25x in inverted immersion, the adjustment ring must still be set to the Glyc position — the same as in DiLL mode.

---

## Resist Film Preparation

The substrate must be spin-coated before loading into the GT2. This step is done outside the GT2, in a spin coater (typically in a cleanroom or yellow-room environment).

General spin coating procedure (details depend on the specific resist — see your resist datasheet and [04_Resists_and_Materials/i_line_photoresists/spin_coating_guide.md](../04_Resists_and_Materials/i_line_photoresists/spin_coating_guide.md)):

1. Clean the substrate by the standard procedure (acetone > IPA > DI water > N2).
2. Apply a few drops of resist to the center of the substrate.
3. Spin at the appropriate speed for the desired film thickness (typically 1000–5000 rpm for 1–10 um films).
4. Soft bake the resist to remove solvent (typically 65–95 degrees C on a hot plate for 1–5 minutes).
5. Allow to cool to room temperature before loading into the GT2.

The soft-baked film should be tacky or solid to the touch — not liquid. It should not flow when the substrate is tilted.

---

## Loading and Approach

1. Load the spin-coated substrate into the appropriate holder with the resist-coated surface facing the objective (downward, toward the 25x or 63x).
2. Apply the immersion medium (glycerol or oil) to the objective tip or to the substrate back surface.
3. Use the Exchange Holder dialog to load the holder.
4. Run interface detection — the system will find the back surface of the substrate (the glass-immersion-medium interface) or the front surface of the resist (the resist-air interface when the resist is on top).
5. Set Z = 0 at the resist-substrate interface (bottom of the resist film). This defines the printing plane.

---

## Depth and Resolution

In inverted immersion mode, printing depth is limited by resist film thickness:

| Resist Film Thickness | Maximum Structure Height |
|---|---|
| 5 um | ~4–5 um (leave ~1 um margin above substrate) |
| 10 um | ~8–9 um |
| 20 um | ~15–18 um |

Resolution within the film is determined by the objective NA:
- 25x (NA 0.8): ~500 nm lateral, ~1 um axial
- 63x (NA 1.4): ~160 nm lateral, ~500 nm axial

This is significantly better than air mode (25x/63x vs. 20x), which is the main reason to use inverted immersion over air mode.

---

## Key Differences from Other Modes

| Feature | Air Mode | Inverted Immersion | DiLL |
|---|---|---|---|
| Objective | 20x (air) | 25x or 63x | 10x, 25x, or 63x |
| Immersion medium | None (air) | Oil or glycerol | Resist itself |
| Resist type | Spin-coated | Spin-coated | Drop-cast liquid |
| Max Z depth | Film thickness | Film thickness | Full working distance |
| Lateral resolution | ~1–2 um | ~160–500 nm | ~160–500 nm |
| 3D capability | Pseudo-3D | Limited 3D within film | Full 3D |

---

## Related Files

- [air_mode.md](./air_mode.md)
- [oil_immersion_mode.md](./oil_immersion_mode.md)
- [dill_mode.md](./dill_mode.md)
- [03_Objectives/25x_objective/adjustment_ring_guide.md](../03_Objectives/25x_objective/adjustment_ring_guide.md)
- [04_Resists_and_Materials/i_line_photoresists/spin_coating_guide.md](../04_Resists_and_Materials/i_line_photoresists/spin_coating_guide.md)
