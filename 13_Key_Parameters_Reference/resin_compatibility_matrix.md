# Resin Compatibility Matrix

## Resin — Objective Compatibility

| Resin | 63x | 25x | 10x | 20x |
|---|---|---|---|---|
| IP-Dip2 | Primary | Compatible | Not recommended | No |
| IP-S | Not standard | Primary | Compatible | No |
| IP-Visio | Not standard | Primary | Not recommended | No |
| IP-PDMS | No | Primary (only) | No | No |
| IP-Q | Compatible | Compatible | Primary | No |
| IPX-Q | No | Compatible | Primary | No |
| IPX-Clear | Primary | Primary | Compatible | No |
| GP-Silica | Primary | No | No | No |
| i-line photoresists | No | No | No | Primary (only) |

Primary = the intended and most common combination
Compatible = works but not the standard choice
Not recommended = technically possible but produces poor results or requires unusual procedures
No = not compatible

---

## Resin — Substrate Compatibility

| Resin | ITO glass | Silicon wafer | Quartz | 170 um borosilicate | Polymer film |
|---|---|---|---|---|---|
| IP-Dip2 | Not standard | Yes | Yes (primary) | Oil immersion only | With prep |
| IP-S | Yes (primary) | Yes | Marginal delta-n | No | With prep |
| IP-Visio | Yes | Yes | Yes | No | With prep |
| IP-PDMS | Yes | Yes | Yes | No | With prep |
| IP-Q | Not recommended | Yes (primary) | Yes | No | With prep |
| IPX-Clear | Yes | Yes | Yes | No | With prep |
| GP-Silica | No | Yes | Yes (primary) | No | No |

Marginal delta-n = interface detection may be unreliable; test before committing to critical sample
With prep = possible after O2 plasma and adhesion layer; test adhesion first
Oil immersion only = 170 um borosilicate is only used in 63x oil immersion mode, not DiLL

---

## Resin — Application Quick Match

| Application | First choice | Alternative |
|---|---|---|
| Micro-optics, lenses | IPX-Clear + 63x or 25x | IP-Dip2 + 63x |
| Microfluidics | IP-S + 25x | IP-Visio + 25x (biocompatible) |
| MEMS, mechanical | IP-S + 25x | IP-Dip2 + 63x (high res) |
| Biomedical scaffolds | IP-Visio + 25x | IP-PDMS + 25x (soft) |
| Photonic crystals | IP-Dip2 + 63x | IPX-Clear + 63x |
| Microrobots | IP-Dip2 + 63x | IP-PDMS + 25x (soft) |
| Nanostructures below 500 nm | IP-Dip2 + 63x | IPX-Clear + 63x |
| Soft actuators, membranes | IP-PDMS + 25x | — |
| Large volume (mm scale) | IP-Q + 10x | IPX-Q + 10x |
| Glass structures (final material) | GP-Silica + 63x | — |
| Traction force microscopy posts | IP-PDMS + 25x | — |
| Waveguides, photonics | IPX-Clear + 25x or 63x | IP-Dip2 + 63x |

---

## Resin Properties Summary

| Resin | Young's modulus | Transparency | Biocompatibility tested | Shrinkage | Special notes |
|---|---|---|---|---|---|
| IP-Dip2 | ~1 to 2 GPa | Good | Limited | ~10% | Highest resolution |
| IP-S | ~1.5 to 2.5 GPa | Good | Limited | ~5 to 8% (lowest) | Most commonly used |
| IP-Visio | ~1 to 2 GPa | Very good (low autofluorescence) | Yes (ISO 10993) | ~8% | Required for cell contact |
| IP-PDMS | ~1 to 5 MPa | Good | Limited | ~5 to 10% | Only soft resin; 25x only |
| IP-Q | ~1.5 to 2.5 GPa | Good | Limited | ~8 to 12% | Large volume |
| IPX-Clear | ~1 to 2 GPa | Excellent (highest) | Limited | ~8% | Best optical clarity |
| GP-Silica | Glass after sintering | Excellent | Silica biocompatible | ~25% (sintering) | 8 hr time limit; furnace required |

---

## Critical Incompatibilities to Memorize

IP-PDMS is only compatible with the 25x objective. No other objective.

GP-Silica is only compatible with the 63x objective. No other objective.

i-line photoresists (used in semiconductor lithography) are only compatible with the 20x objective. IP-series resins are not used with the 20x.

170 um borosilicate glass is only used in 63x oil immersion mode. It is not a standard DiLL substrate and cannot be used with other objectives in the standard workflow.

ITO glass is not recommended with the 10x + IP-Q combination. Silicon is the standard 10x substrate.
