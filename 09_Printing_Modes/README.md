# Module 09 — Printing Modes

> The GT2 is not a single-mode machine. It supports multiple distinct printing configurations, each combining a specific beam delivery method, objective type, and substrate geometry. Choosing the wrong mode for your setup will either prevent printing entirely or degrade your results without obvious explanation.

---

## What Is a Printing Mode?

A printing mode describes how the laser beam reaches the resist and how the focal point moves through it. Two separate axes determine the mode:

**Axis 1: How the beam contacts the resist**

| Mode | Description |
|---|---|
| DiLL (Dip-In Laser Lithography) | Objective tip submerged directly in liquid resist |
| Oil Immersion | Thin film of immersion oil between objective and substrate; resist is on the other side |
| Air Mode | Objective separated from resist by an air gap; used with spin-coated resists |
| Inverted Immersion | Spin-coated resist on top of substrate; objective accesses from below through oil or air |

**Axis 2: How the focal point scans**

| Mode | Description |
|---|---|
| Piezo Scan | Sample moves; beam is fixed; ~10 nm accuracy, 300 x 300 x 300 um range |
| Galvo Scan | Beam steered by mirrors; sample is fixed; high speed, 400 x 400 um field |
| Tilt Correction | Piezo scan with active Z correction for non-flat substrate surfaces |

These two axes combine. For example: DiLL + Galvo scan is the most common configuration for the 25x. Oil Immersion + Piezo scan is standard for 63x through-glass printing.

---

## Files in This Module

| File | What It Covers |
|---|---|
| `dill_mode.md` | Dip-In Laser Lithography — the primary mode for all IP-series resists |
| `oil_immersion_mode.md` | Through-glass printing with the 63x and immersion oil |
| `air_mode.md` | 20x air objective for 2D patterning on spin-coated resists |
| `piezo_scan_mode.md` | Piezo stage scanning — precision, range, and when to use it |
| `galvo_scan_mode.md` | Galvo mirror scanning — speed, field size, and when to use it |
| `inverted_immersion_mode.md` | 25x or 63x printing on spin-coated i-line resists |
| `tilt_correction_mode.md` | Active Z correction for non-flat or tilted substrates |

---

## Mode Selection Quick Reference

| Your Setup | Beam Mode | Scan Mode |
|---|---|---|
| 63x + IP-Dip2 + quartz/silicon | DiLL | Piezo |
| 25x + IP-S + ITO glass | DiLL | Galvo |
| 10x + IP-Q + silicon wafer | DiLL | Galvo |
| 63x + IP-Dip2 + 170 um glass (through-glass) | Oil Immersion | Piezo |
| 20x + i-line resist + spin-coated wafer | Air | Piezo or Galvo |
| 25x + i-line resist + spin-coated wafer | Inverted Immersion | Galvo |
| Any + non-flat substrate | DiLL or Oil | Piezo + Tilt Correction |

---

## Related Modules

- [02_Machine_Components/galvo_vs_piezo_scanning.md](../02_Machine_Components/galvo_vs_piezo_scanning.md)
- [03_Objectives/](../03_Objectives/README.md)
- [04_Resists_and_Materials/](../04_Resists_and_Materials/README.md)
- [07_Step_by_Step_Workflows/](../07_Step_by_Step_Workflows/README.md)
