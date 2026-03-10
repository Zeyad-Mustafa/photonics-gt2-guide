# Substrate Compatibility Table

---

## Full Compatibility Matrix

| Substrate | 10x + IP-Q | 25x + IP-S | 25x + IP-Visio | 63x + IP-Dip2 | 20x + i-line |
|---|---|---|---|---|---|
| ITO-coated glass (25x25 mm) | Not recommended | Primary | Primary | Not standard | No |
| Silicon wafer pieces | Primary | Yes | Yes | Yes | Yes |
| Quartz (fused silica) | Yes | Yes | Yes | Primary | Yes |
| 170 um borosilicate glass | No | No | No | Oil mode only | No |
| Standard borosilicate glass | Yes (check delta-n) | Yes | Yes | Not ideal | Yes |
| Flexible polymer film | Not recommended | Special prep needed | Not recommended | No | No |
| Crystal substrates | Case by case | Case by case | Case by case | Case by case | No |

---

## Delta-n Reference Table

Delta-n is the difference in refractive index between the substrate and the resin sitting on top of it. A minimum delta-n of 0.04 is required for the GT2 interface finder to detect the substrate surface.

| Substrate | Refractive Index (n) | Delta-n vs IP-Dip2 (1.511) | Delta-n vs IP-S (1.478) | Delta-n vs IP-Q (1.48) |
|---|---|---|---|---|
| Silicon | ~3.5 | 1.99 — excellent | 2.02 — excellent | 2.02 — excellent |
| ITO-coated glass | ~1.52 (ITO layer) | 0.009 | 0.04 — marginal | 0.04 — marginal |
| Quartz (fused silica) | ~1.46 | 0.051 — acceptable | 0.018 — marginal | 0.02 — marginal |
| Standard borosilicate | ~1.52 | 0.009 — too low | 0.04 — marginal | 0.04 — marginal |
| 170 um borosilicate | ~1.515 | 0.004 — too low for DiLL | N/A | N/A |
| Gold-coated substrate | N/A (reflective) | Very high — excellent | Very high — excellent | Very high — excellent |
| Photoresist on silicon | Depends on resist | Depends | Depends | Depends |

Notes:
- ITO on glass: the ITO layer (n ~ 2.0) is what creates the contrast, not the underlying glass. The effective delta-n depends on ITO layer thickness and quality.
- Quartz with IP-S: delta-n is only ~0.018, which is below the 0.04 minimum. Use silicon instead for 25x + IP-S combinations on quartz.
- 170 um borosilicate: used only in oil immersion mode where interface detection works differently.

---

## Substrate Size Requirements

| Holder Type | Required Substrate Size |
|---|---|
| Universal DiLL holder | 25 x 25 mm |
| Multi-DiLL Si Wafer holder | 25 x 25 mm wafer piece |
| 5-inch mask holder | 5-inch (127 mm) round wafer or mask |

The GT2 sample holders are designed for 25x25 mm substrates in most standard configurations. Substrates that are too small may not be clamped securely and can shift during printing. Substrates that are too large will not fit in the holder.

---

## Thermal and Mechanical Requirements

| Requirement | Minimum Specification |
|---|---|
| Surface flatness | Less than 5 um variation across print area |
| Surface roughness | Less than 10 nm Ra for reliable adhesion |
| Thermal stability | Must not deform at room temperature during printing |
| Chemical compatibility | Must not dissolve in PGMEA or IPA during development |

---

After selecting your substrate from this table, see the individual substrate file for full preparation instructions.
