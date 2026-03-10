# Section 05 — Substrates

## Overview

A substrate is the solid surface on which you print your structure. In the GT2, the substrate sits above the objective lens, and the laser focuses up through the resin and into or onto the substrate surface. Every decision you make about substrates — material, thickness, surface preparation, and orientation — directly affects whether your print succeeds or fails.

This section covers every substrate type compatible with the GT2, how to prepare them, how to choose between them, and why certain substrates only work with certain objectives.

---

## Why the Substrate Matters

The substrate is not passive. It plays three active roles in every print:

**Interface detection:** The GT2 finds the substrate surface by detecting reflected light at the resin-substrate boundary. This requires a measurable difference in refractive index (delta-n) between the resin and the substrate. If delta-n is too small, the interface finder fails and the print cannot begin.

**Structural adhesion:** Your printed structure must stick to the substrate surface throughout printing and development. Poor adhesion causes the structure to detach and wash away in the development solvent.

**Downstream compatibility:** Many GT2 prints are not the final device — they are steps in a larger fabrication process. The substrate must be compatible with whatever comes next: electron beam evaporation, atomic layer deposition, wet etching, electrodeposition, or SEM characterization.

---

## Files in This Section

| File | Contents |
|---|---|
| substrate_compatibility_table.md | Full matrix of substrates vs objectives vs resists |
| ITO_coated_glass.md | Standard substrate for 25x DiLL workflow |
| silicon_wafers.md | Cutting, cleaning, and using silicon pieces |
| borosilicate_glass_170um.md | For 63x oil immersion mode |
| quartz_substrates.md | UV-transparent, for optical applications |
| custom_substrates.md | Polymers, crystals, flexible films, unusual materials |
| interface_detection_requirements.md | Delta-n requirements, how detection works, failure modes |
| substrate_cleaning_procedure.md | Full cleaning protocol for all substrate types |

---

## Quick Selection Guide

| Objective | Standard Substrate | Alternative |
|---|---|---|
| 10x + IP-Q | Silicon wafer (25x25 mm) | Nanoscribe borosilicate glass slides |
| 25x + IP-S | ITO-coated glass (25x25 mm) | Silicon wafer |
| 63x + IP-Dip2 | Quartz or silicon | 170 um borosilicate (oil mode only) |
| 20x + i-line resist | Spin-coated silicon wafer | Any flat wafer |

---

## The Most Important Rule

Always orient the substrate so the resin-contact surface faces down toward the objective. Printing through the bulk of the substrate instead of at the surface will fail — the laser cannot focus correctly through mismatched materials.

---

After this section, proceed to Section 06 — Software Workflow.
