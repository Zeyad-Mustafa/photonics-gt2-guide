# ⚠️ 20× Objective — Limitations

---

## Hard Limitations

| Limitation | Detail |
|---|---|
| **No true 3D printing** | Air objective cannot do DiLL — no volumetric printing |
| **No IP-series resins** | All Nanoscribe IP resins require immersion objectives |
| **Resolution limited by air NA** | Cannot achieve sub-micron features without immersion |
| **Z-range limited to resist thickness** | Typically < 50 µm; most applications < 10 µm |
| **No interface finder in same way** | Substrate detection works differently than DiLL objectives |

---

## Resolution Limits

Without immersion, the numerical aperture is limited to < 1.0 (air). At NA < 1.0 and 780 nm:

```
Lateral resolution ≥ 0.61 × 780 nm / NA ≥ ~475 nm (at NA = 1.0)
```

In practice, the 20× air objective achieves lateral resolution of ~1–2 µm — fine for 2D lithography but far below what the 63× DiLL achieves.

---

## Why the 20× Is Rarely the First Choice

For most GT2 users, the machine's key advantage is **true 3D printing**. The 20× bypasses this advantage entirely. If you only need 2D patterning, a standard mask aligner or UV laser writer might be faster and cheaper.

The 20× exists for users who need to combine 2D lithography with the GT2's precise stage positioning and stitching capability, or who are integrating into an existing semiconductor workflow.

---

## Summary Table

| Can Do | Cannot Do |
|---|---|
| 2D flat patterning | True 3D structures |
| Large area stitched exposure | Sub-500 nm features |
| Standard i-line resists | IP-series resins |
| Pseudo-3D grayscale | Tall structures > 50 µm |

---

> 🔗 Return to: [03_Objectives/README.md](../README.md)