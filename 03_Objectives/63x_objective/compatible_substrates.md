# 🧱 63× Objective — Compatible Substrates

---

## Primary Substrates

| Substrate | Δn vs IP-Dip2 | Notes |
|---|---|---|
| **Quartz (fused silica)** | ~0.05 | Best optical quality, UV transparent |
| **Silicon wafer** | ~2.0 | Very high contrast — most reliable detection |
| **170 µm borosilicate glass** | ~0.004 | For oil immersion mode only |

---

## Quartz — Best for Optical Applications

Fused silica (quartz) substrates are ideal when:
- The substrate must be optically transparent (e.g., for transmission measurements)
- UV transparency is needed for downstream characterization
- Low autofluorescence is required

Δn between quartz (n ≈ 1.46) and IP-Dip2 (n = 1.511) is ~0.05 — just above the minimum detection threshold. Interface detection usually works but may require careful resin drop geometry (semi-spherical is essential).

---

## Silicon — Most Reliable Interface Detection

Silicon has a very high refractive index (n ≈ 3.5), giving Δn ≈ 2.0 vs IP-Dip2. This large contrast makes interface detection extremely reliable.

Use silicon when:
- Optical transparency of substrate is not needed
- Maximum reliability of interface detection is important
- Downstream processing involves silicon etching or deposition

---

## 170 µm Borosilicate Glass — Oil Immersion Mode Only

The 170 µm glass coverslip is specifically designed for oil immersion mode (not DiLL):
- Must be exactly 170 µm ± 5 µm thick
- The 63× objective is designed to correct for exactly this glass thickness in oil mode
- Using thicker or thinner glass introduces spherical aberration
- Δn between glass and oil is ~0 → interface between objective and substrate is invisible to interface finder in oil mode — requires manual focus

---

## Substrate Cleaning (63×)

Extra care needed — at 160 nm resolution, a single dust particle ruins your print:

1. Acetone rinse — 30 seconds
2. IPA rinse — 30 seconds
3. DI water rinse — 30 seconds
4. Nitrogen blow dry
5. **Inspect under optical microscope** — no particles > 500 nm should be visible in the print area
6. Optional: O₂ plasma 60 s — excellent for adhesion and surface cleanliness

---

> 🔗 Next: [voxel_dimensions.md](voxel_dimensions.md)