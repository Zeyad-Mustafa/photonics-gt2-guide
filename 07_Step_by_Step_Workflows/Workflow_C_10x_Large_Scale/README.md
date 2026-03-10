# Workflow C — 10x Objective, DiLL Mode, IP-Q

> Use this workflow when you need millimeter-scale structures and print speed matters more than fine resolution. The 10x objective is the fastest printing configuration on the GT2 and can build structures that would be impractical with the 25x or 63x.

---

## Workflow Overview

| Parameter | Value |
|---|---|
| Objective | 10x (NA 0.3) |
| Resist | IP-Q |
| Printing mode | DiLL |
| Sample holder | Multi-DiLL Silicon Wafer Holder |
| Typical substrate | Silicon wafer piece (25 x 25 mm or smaller) |
| Lateral resolution | ~2–5 um |
| Axial resolution | ~5–10 um |
| Typical structure size | 0.5–5 mm in XY, up to 8 mm Z with stage |
| Scanning mode | Galvo |
| Developer | PGMEA, followed by IPA rinse |

---

## When to Use This Workflow

Use Workflow C when:
- Your structure is larger than 500 um and does not require sub-micron resolution
- You need to print multiple identical structures quickly
- Your application is large-scale scaffolds, mechanical testing specimens, or rapid prototyping at the mesoscale
- Feature sizes are 5 um or larger

Do not use when:
- You need sub-5 um features (use Workflow A or B)
- Your substrate is ITO glass (the Multi-DiLL holder is optimized for silicon; use the Universal Holder and 25x instead)

---

## Steps in This Workflow

| Step | File | Summary |
|---|---|---|
| 1 | step_01_design.md | Design for 10x constraints |
| 2 | step_02_prepare_silicon_substrate.md | Dice and clean silicon |
| 3 | step_03_apply_IP_Q.md | Apply IP-Q correctly (1-2 drops only) |
| 4 | step_04_install_10x.md | Install the 10x objective |
| 5 | step_05_run_print.md | Execute the print |
| 6 | step_06_development.md | Develop in PGMEA then IPA |
| — | troubleshooting.md | Workflow C specific problems |

---

## Related Files

- [04_Resists_and_Materials/IP_Q/overview.md](../../04_Resists_and_Materials/IP_Q/overview.md)
- [03_Objectives/10x_objective/overview.md](../../03_Objectives/10x_objective/overview.md)
