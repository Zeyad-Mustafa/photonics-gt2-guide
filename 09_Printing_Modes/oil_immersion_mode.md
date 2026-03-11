# Oil Immersion Mode

> Oil immersion mode uses the 63x objective to print through a thin glass substrate. It is the correct configuration when your application requires printing on a pre-existing surface, working with opaque substrates, or accessing resist from the opposite side of a cover glass.

---

## What Oil Immersion Mode Is

In oil immersion mode, the 63x objective is not submerged in resist. Instead:

- A thin film of **immersion oil** (Zeiss Immersol 518F, n = 1.518) sits between the objective front element and the bottom surface of a **170 um borosilicate glass coverslip**
- The resist (IP-Dip2 or IPX-Clear) sits on **top** of the coverslip
- The laser travels upward through the oil, through the coverslip, and focuses in the resist above

```
        [  resist (IP-Dip2)  ]    <- printing happens here (above glass)
        [ 170 um glass       ]    <- coverslip
        [  immersion oil     ]    <- n = 1.518, fills the gap
        [ objective tip      ]    <- 63x, not touching resist
              |
         laser beam
         (from below)
```

The resist is accessed from the opposite side of the glass relative to the objective. This is sometimes called "3D SF Oil" mode in Nanoscribe documentation (3D Substrate-Focused, Oil immersion).

---

## Why Use Oil Immersion Instead of DiLL?

DiLL is simpler and gives better depth performance for most applications. Oil immersion mode is specifically needed when:

| Situation | Why Oil Immersion Is Required |
|---|---|
| Printing on a pre-patterned surface | The substrate top surface has existing features — the objective cannot be submerged without damaging them |
| Substrate is fragile or thin | Some substrates cannot be flipped or handled in the DiLL orientation |
| Opaque substrate (silicon) with resist on top | DiLL would require the objective to approach through silicon, which blocks the beam |
| Large-area spin-coated resist layer | Spin-coated resist layers cannot form the drop shape needed for DiLL |
| Precise depth control in thick resist layers | Oil immersion gives well-corrected focus from the coverslip surface upward |

For most standard printing on clean substrates with IP-Dip2, use DiLL. Oil immersion is the specialist configuration.

---

## Hardware Requirements

**Objective:** 63x (NA 1.4) only. The 63x is designed for oil immersion. The 25x cannot be used in oil immersion mode — its NA and correction are wrong for this geometry.

**Immersion oil:** Zeiss Immersol 518F. Refractive index n = 1.518. Do not substitute generic immersion oils — the refractive index must match the coverslip (borosilicate n ~ 1.515) to avoid aberration.

**Substrate:** 170 um borosilicate glass coverslip (No. 1.5 coverslip). This specific thickness is required. Thicker or thinner glass shifts the focal plane and introduces spherical aberration. The 63x objective's optical correction assumes 170 um glass between objective and sample.

**Sample holder:** Universal Sample Holder. The coverslip is loaded with the resist-coated (top) surface facing upward and the bare glass surface facing the objective. Oil is applied to the objective tip or to the glass bottom surface before loading.

---

## Applying Immersion Oil

1. With the sample holder loaded and the 63x in position, open the top hatch.
2. Place one small drop of Zeiss Immersol 518F on the center of the coverslip's bottom surface (the side that will face the objective), or apply it to the 63x objective front element.
3. When the stage approaches the sample, the oil will form a continuous film between the objective and the glass.
4. The oil film must be bubble-free. Any bubble in the oil is in the direct beam path and will scatter the laser.

Inspect the oil film through the AxioVision camera after approach — it should appear as a uniform, featureless region. A bubble appears as a bright circular artifact.

---

## Refractive Index Matching in Oil Immersion Mode

The power of oil immersion mode lies in refractive index matching:

| Layer | Material | Refractive Index |
|---|---|---|
| Objective front element | Glass | ~1.515 |
| Immersion oil | Zeiss Immersol 518F | 1.518 |
| Coverslip | Borosilicate glass | ~1.515 |
| Resist | IP-Dip2 | 1.511 |

From the objective through the oil and coverslip to the resist, the refractive index varies by only ~0.007. This near-perfect match means the laser travels through this stack with minimal aberration or beam distortion.

Compare this to printing through a standard glass slide (n ~ 1.515) into water (n = 1.33) — a delta-n of 0.185 that would cause severe spherical aberration. Oil immersion eliminates this.

---

## Depth Limit in Oil Immersion Mode

In oil immersion mode, the maximum printable depth into the resist is limited by:

1. **Working distance of the 63x** — nominally 360 um, but in oil immersion mode the glass coverslip consumes 170 um of this, leaving approximately 190 um of working distance within the resist.
2. **Spherical aberration accumulation with depth** — unlike DiLL (which has a homogeneous medium from objective to focal point), oil immersion mode involves printing into a resist layer on top of glass. As depth into the resist increases, any residual refractive index mismatch between the coverslip and the resist accumulates. For IP-Dip2 (delta-n = 0.004 from glass), this is very small and allows printing up to ~100–150 um deep before aberration becomes noticeable.

For structures taller than 100–150 um, DiLL mode with the 63x or the 25x is a better choice.

---

## Interface Detection in Oil Immersion Mode

Interface detection works differently from DiLL:

- In DiLL, the system detects the resist-substrate interface from below (objective looking up through resist at the substrate)
- In oil immersion, the system detects the **glass-resist interface** — the top surface of the 170 um coverslip, where the glass meets the resist above it

The delta-n between borosilicate glass (1.515) and IP-Dip2 (1.511) is approximately 0.004 — at the minimum threshold for reliable detection. If detection is unreliable, switching to a resist with a larger delta-n from glass (such as IPX-Clear, n ~ 1.50, delta-n = 0.015) can help.

---

## Cleaning After Oil Immersion Mode

After printing, the objective tip will have residual immersion oil and possibly trace resist. Clean in order:

1. Gently wipe the objective front element with a lens tissue dampened with PGMEA to remove any resist traces.
2. Follow with a fresh lens tissue dampened with IPA to remove PGMEA and oil residue.
3. Final wipe with a dry lens tissue.
4. Inspect under bright light. The front element should be perfectly clean and clear.

Do not leave immersion oil on the objective for extended periods — it can dry and leave a residue that is harder to remove.

---

## Common Mistakes

| Mistake | Consequence | Fix |
|---|---|---|
| Using wrong coverslip thickness | Spherical aberration; degraded resolution | Use No. 1.5 (170 um) coverslip only |
| Bubble in immersion oil | Laser scatter; void in structure | Remove oil, reapply bubble-free, re-approach |
| Using wrong immersion oil | Refractive index mismatch; aberration | Use Zeiss Immersol 518F only |
| Applying oil to resist side instead of glass side | Oil contacts the resist, contaminating it | Apply oil to the glass bottom surface |
| Attempting oil immersion with 25x | 25x is not corrected for this geometry | Use 63x only for oil immersion |

---

## Related Files

- [dill_mode.md](./dill_mode.md)
- [03_Objectives/63x_objective/oil_immersion_mode.md](../03_Objectives/63x_objective/oil_immersion_mode.md)
- [05_Substrates/borosilicate_glass_170um.md](../05_Substrates/borosilicate_glass_170um.md)
- [04_Resists_and_Materials/IP_Dip2/use_with_63x.md](../04_Resists_and_Materials/IP_Dip2/use_with_63x.md)
