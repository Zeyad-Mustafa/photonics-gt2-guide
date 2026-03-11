# Substrate Quick Reference

## Delta-n Values (Resin vs Substrate at 780 nm)

Higher delta-n = more reliable interface detection. Minimum required: 0.04.

| Substrate | n at 780 nm | Delta-n vs IP-Dip2 (1.511) | Delta-n vs IP-S (1.478) | Delta-n vs IP-Q (1.480) | Detection reliability |
|---|---|---|---|---|---|
| Silicon | ~3.5 | ~1.99 | ~2.02 | ~2.02 | Excellent |
| ITO-coated glass (ITO surface) | ~1.8 to 2.0 | ~0.3 to 0.5 | ~0.3 to 0.5 | ~0.3 to 0.5 | Excellent |
| Quartz (fused silica) | ~1.457 | ~0.054 | ~0.021 | ~0.023 | Good (IP-Dip2), marginal (IP-S) |
| Standard borosilicate | ~1.515 | ~0.004 | ~0.037 | ~0.035 | Poor — avoid |
| 170 um borosilicate (oil mode) | ~1.515 | N/A (oil immersion, different detection) | N/A | N/A | Manual detection |
| Gold-coated substrate | Highly reflective | Very high | Very high | Very high | Excellent |
| Polymer film | ~1.45 to 1.55 | Variable | Variable | Variable | Test before use |

---

## Substrate Selection by Objective and Resin

| Objective + Resin | Standard substrate | Alternative | Avoid |
|---|---|---|---|
| 63x + IP-Dip2 (DiLL) | Quartz or silicon | Gold-coated glass | Standard borosilicate (poor delta-n) |
| 63x + IP-Dip2 (oil immersion) | 170 um borosilicate | — | Any other thickness |
| 25x + IP-S | ITO glass (25x25 mm) | Silicon | Quartz (marginal delta-n with IP-S) |
| 25x + IP-Visio | ITO glass | Silicon | — |
| 25x + IP-PDMS | ITO glass | Silicon | — |
| 10x + IP-Q | Silicon (25x25 mm) | Nanoscribe borosilicate slide | ITO glass |
| 20x + i-line resist | Silicon wafer | Any flat wafer | IP-series resin substrates |

---

## Substrate Cleaning Method by Type

| Substrate | Acetone | IPA | DI water | N2 dry | O2 plasma | Notes |
|---|---|---|---|---|---|---|
| Silicon | Yes | Yes | Yes | Yes | Recommended (100 W, 90 to 120 s) | Most tolerant substrate |
| ITO glass | Yes | Yes | Yes | Yes | Yes (100 W, 60 s max) | Excess plasma raises sheet resistance |
| Quartz | Yes | Yes | Yes | Yes | Recommended (100 W, 90 to 120 s) | Piranha also acceptable |
| 170 um borosilicate | Gentle rinse only | Gentle rinse | Gentle rinse | Low pressure only | 50 W, 30 s max | Handle by edges; very fragile |
| Gold-coated | Yes | Yes | Yes | Yes | Yes (100 W, 60 s) | Apply thiol adhesion promoter after plasma if adhesion is poor |
| Polymer film | IPA only (test acetone first) | Yes | Yes | Gentle | 50 W, 60 s | Test chemical compatibility before full clean |

---

## Substrate Size Requirements

| Holder | Required size |
|---|---|
| Standard DiLL holder | 25 x 25 mm |
| Multi-substrate holder | 25 x 25 mm pieces |

Substrates smaller than 25 x 25 mm may not clamp securely and can shift during printing.

---

## Substrate Flatness and Roughness Requirements

| Parameter | Required value |
|---|---|
| Surface flatness across print area | Less than 5 um variation |
| Surface roughness (Ra) | Less than 10 nm |
| Minimum substrate thickness | Check holder Z clearance — typically 0.3 mm minimum |

---

## ITO Orientation Reminder

ITO glass: ITO-coated side faces DOWN toward the objective.
How to identify ITO side: measure resistance with multimeter. ITO side reads 10 to 100 ohms per square. Bare glass reads open circuit.
