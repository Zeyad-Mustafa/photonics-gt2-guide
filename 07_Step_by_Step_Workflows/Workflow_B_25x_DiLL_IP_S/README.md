# Workflow B — 25x Objective, DiLL Mode, IP-S

> This is the recommended first workflow for new GT2 users. The 25x objective is more forgiving than the 63x, IP-S has very low shrinkage and excellent surface quality, and the print speed is faster than the 63x for equivalent volumes.

---

## Workflow Overview

| Parameter | Value |
|---|---|
| Objective | 25x (NA 0.8) |
| Resist | IP-S |
| Printing mode | DiLL (Dip-In Laser Lithography) |
| Sample holder | Universal Sample Holder |
| Typical substrate | ITO-coated glass (ITO side facing objective) |
| Lateral resolution | ~500 nm |
| Axial resolution | ~1 um |
| Typical structure size | Up to ~1 x 1 x 1 mm with stitching |
| Scanning mode | Galvo (standard) or piezo (precision) |
| Developer | PGMEA, followed by IPA rinse |

---

## When to Use This Workflow

Use Workflow B when:

- You are printing for the first time and want a reliable, forgiving workflow
- Your structure is between 100 um and 1 mm in size
- Low shrinkage is important (IP-S has ~5% shrinkage vs. ~15% for IP-Dip2)
- You need smooth surfaces without visible layer artifacts
- You are printing microfluidic channels, scaffolds, or mechanical structures at the mesoscale

Do not use this workflow when:
- You need sub-200 nm features (use Workflow A instead)
- Your structure exceeds 1 mm and you need fast throughput (use Workflow C)
- You need flexible/elastic output (use IP-PDMS)

---

## Steps in This Workflow

| Step | File | Summary |
|---|---|---|
| 1 | step_01_design_your_structure.md | Design for 25x constraints |
| 2 | step_02_export_stl.md | Export a clean STL |
| 3 | step_03_slice_in_describe.md | Slice with 25x parameters in DeScribe |
| 4 | step_04_prepare_ITO_substrate.md | Clean and orient ITO-coated glass |
| 5 | step_05_apply_IP_S_resist.md | Apply IP-S to the substrate |
| 6 | step_06_install_25x_objective.md | Install the 25x with correct adjustment ring |
| 7 | step_07_load_sample_holder.md | Load the Universal Sample Holder |
| 8 | step_08_find_interface.md | Run interface detection |
| 9 | step_09_run_print_job.md | Execute the print |
| 10 | step_10_development.md | Develop in PGMEA then IPA |
| 11 | step_11_uv_curing.md | UV post-cure |
| — | troubleshooting.md | Workflow B specific problems |

---

## Related Files

- [04_Resists_and_Materials/IP_S/overview.md](../../04_Resists_and_Materials/IP_S/overview.md)
- [03_Objectives/25x_objective/overview.md](../../03_Objectives/25x_objective/overview.md)
- [troubleshooting.md](./troubleshooting.md)
