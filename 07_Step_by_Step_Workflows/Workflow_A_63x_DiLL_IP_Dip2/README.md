# Workflow A — 63x Objective, DiLL Mode, IP-Dip2

> This is the highest-resolution workflow available on the GT2. Use it when you need sub-200 nm lateral features, maximum structural fidelity, or when your application demands the smallest possible voxel size.

---

## Workflow Overview

| Parameter | Value |
|---|---|
| Objective | 63x (NA 1.4) |
| Resist | IP-Dip2 |
| Printing mode | DiLL (Dip-In Laser Lithography) |
| Sample holder | Universal Sample Holder |
| Typical substrate | Quartz, silicon, or 170 um borosilicate glass |
| Lateral resolution | ~160 nm |
| Axial resolution | ~500 nm |
| Typical structure size | Up to ~200 x 200 x 400 um per print field |
| Scanning mode | Piezo (standard) or galvo (for larger fields) |
| Developer | PGMEA, followed by IPA rinse |

---

## When to Use This Workflow

Use Workflow A when:

- You need the smallest possible feature size (< 500 nm lateral)
- Your structure requires sub-micron precision in placement or dimensions
- You are printing photonic devices, nanostructures, or high-NA optical elements
- Your application requires the refractive index match that IP-Dip2 provides (n = 1.511)

Do not use this workflow when:

- Your structure is larger than ~400 um in any dimension (use Workflow B or C instead)
- You need flexible or elastic output material (use IP-PDMS)
- You need biocompatible output (use IP-Visio with Workflow B)
- Print speed is the primary concern (the 63x is slower than the 25x or 10x for equivalent volume)

---

## Steps in This Workflow

| Step | File | Summary |
|---|---|---|
| 1 | step_01_design_your_structure.md | Design your 3D structure in CAD |
| 2 | step_02_export_stl.md | Export a clean STL file |
| 3 | step_03_slice_in_describe.md | Slice the STL in DeScribe for the 63x |
| 4 | step_04_prepare_substrate.md | Clean your substrate |
| 5 | step_05_apply_resist.md | Apply IP-Dip2 to the substrate |
| 6 | step_06_install_63x_objective.md | Install the 63x objective with fiber ring |
| 7 | step_07_load_sample_holder.md | Load the Universal Sample Holder |
| 8 | step_08_find_interface.md | Run interface detection |
| 9 | step_09_run_print_job.md | Execute the GWL print job |
| 10 | step_10_development.md | Develop the structure in PGMEA then IPA |
| 11 | step_11_uv_curing.md | UV post-cure for full crosslinking |
| 12 | step_12_characterization.md | Inspect and document the result |
| — | troubleshooting.md | Workflow-specific problems and fixes |

---

## Estimated Time

| Phase | Estimated Duration |
|---|---|
| Laser warm-up (if starting cold) | 45 minutes |
| DeScribe slicing | 5–30 minutes depending on structure complexity |
| Substrate preparation | 15–20 minutes |
| Sample loading and interface detection | 10–15 minutes |
| Print time | Varies — check NanoWrite estimate before starting |
| Development | 20–30 minutes |
| UV curing | 10–20 minutes |
| Total (excluding warm-up and print) | ~60–90 minutes hands-on |

Always check the estimated print time in NanoWrite before committing to a job. A large structure with piezo mode can take hours.

---

## Related Files

- [04_Resists_and_Materials/IP_Dip2/overview.md](../../04_Resists_and_Materials/IP_Dip2/overview.md)
- [03_Objectives/63x_objective/overview.md](../../03_Objectives/63x_objective/overview.md)
- [08_Development_and_Post_Processing/development_solvents.md](../../08_Development_and_Post_Processing/development_solvents.md)
- [troubleshooting.md](./troubleshooting.md)
