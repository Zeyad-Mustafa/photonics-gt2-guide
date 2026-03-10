# 🧪 20× Objective — Compatible Resists

---

## Compatible Resists

| Resist | Status | Notes |
|---|---|---|
| **Standard i-line photoresists** | ✅ Primary | AZ series, Shipley, SU-8 (thin layers) |
| All IP-series resins | ❌ Not compatible | Require DiLL immersion objectives |

---

## What Are i-line Photoresists?

**i-line** refers to the 365 nm mercury arc lamp emission line commonly used in semiconductor photolithography. These are single-photon resists — they react to UV light, not to two-photon NIR.

Wait — the GT2 uses a 780 nm NIR laser. How does it expose i-line resists?

The answer: through **two-photon absorption** at 780 nm, which is equivalent to single-photon absorption at 390 nm (~i-line wavelength). The GT2's femtosecond pulses provide enough peak intensity to trigger two-photon exposure in i-line resists.

This is different from using the GT2's IP-series resins — i-line resists were not designed for 2PP, but they respond to it.

---

## Common i-line Resists Used With GT2 20×

| Resist | Type | Typical Thickness | Use Case |
|---|---|---|---|
| AZ 1500 series | Positive | 0.5–2 µm | Fine 2D patterns |
| AZ 4000 series | Positive | 2–10 µm | Thicker 2D patterns |
| Shipley S1800 series | Positive | 0.5–3 µm | Standard lithography |
| SU-8 (thin) | Negative | 1–20 µm | High-aspect-ratio 2D walls |

---

## Spin Coating for 20× Use

1. Clean substrate thoroughly (piranha or O₂ plasma)
2. Spin coat resist at manufacturer's recommended speed (typically 3000–5000 RPM)
3. Soft bake on hotplate (follow resist datasheet)
4. Load into GT2 and expose with 20× objective
5. Post-expose bake if required (SU-8)
6. Develop with appropriate developer (AZ developer, PGMEA for SU-8)

---

> 🔗 Next: [limitations.md](limitations.md)