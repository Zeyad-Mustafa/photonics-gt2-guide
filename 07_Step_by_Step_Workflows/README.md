# Module 07 — Step-by-Step Workflows

> This module is where everything you have learned becomes action. Each workflow is a complete, numbered procedure from blank substrate to finished printed structure. Follow the steps in order. Do not skip ahead.

---

## What This Module Is

Modules 00 through 06 gave you the knowledge — the physics, the machine components, the objectives, the resists, the substrates, and the software. This module gives you the procedure.

There are four workflows, each built around a different objective and resist combination. Each workflow covers every step from CAD design to post-print characterization. Every step specifies:

- What to do
- Why you are doing it
- What can go wrong and how to fix it

---

## Choose Your Workflow

| Workflow | Objective | Resist | Best For |
|---|---|---|---|
| A | 63x (NA 1.4) | IP-Dip2 | Highest resolution, sub-200 nm features, nanoscale precision |
| B | 25x (NA 0.8) | IP-S | Mesoscale structures, balanced speed and resolution, low shrinkage |
| C | 10x (NA 0.3) | IP-Q | Large mm-scale structures, fast printing, coarse features |
| D | 25x or 63x | GP-Silica | True glass structures requiring furnace sintering |

If you are printing for the first time, start with Workflow B (25x + IP-S). It is the most forgiving combination — the 25x objective has a longer working distance than the 63x, IP-S is less sensitive to small parameter errors than IP-Dip2, and the print speed is manageable.

---

## Files in This Module

```
07_Step_by_Step_Workflows/
|
|-- README.md                              <- This file
|
|-- Workflow_A_63x_DiLL_IP_Dip2/
|   |-- README.md
|   |-- step_01_design_your_structure.md
|   |-- step_02_export_stl.md
|   |-- step_03_slice_in_describe.md
|   |-- step_04_prepare_substrate.md
|   |-- step_05_apply_resist.md
|   |-- step_06_install_63x_objective.md
|   |-- step_07_load_sample_holder.md
|   |-- step_08_find_interface.md
|   |-- step_09_run_print_job.md
|   |-- step_10_development.md
|   |-- step_11_uv_curing.md
|   |-- step_12_characterization.md
|   `-- troubleshooting.md
|
|-- Workflow_B_25x_DiLL_IP_S/
|   |-- README.md
|   |-- step_01_design_your_structure.md
|   |-- step_02_export_stl.md
|   |-- step_03_slice_in_describe.md
|   |-- step_04_prepare_ITO_substrate.md
|   |-- step_05_apply_IP_S_resist.md
|   |-- step_06_install_25x_objective.md
|   |-- step_07_load_sample_holder.md
|   |-- step_08_find_interface.md
|   |-- step_09_run_print_job.md
|   |-- step_10_development.md
|   |-- step_11_uv_curing.md
|   `-- troubleshooting.md
|
|-- Workflow_C_10x_Large_Scale/
|   |-- README.md
|   |-- step_01_design.md
|   |-- step_02_prepare_silicon_substrate.md
|   |-- step_03_apply_IP_Q.md
|   |-- step_04_install_10x.md
|   |-- step_05_run_print.md
|   |-- step_06_development.md
|   `-- troubleshooting.md
|
`-- Workflow_D_Glass_Structures_GP_Silica/
    |-- README.md
    |-- special_requirements.md
    |-- print_steps.md
    `-- post_processing.md
```

---

## Before You Begin Any Workflow

These conditions must be true before starting any workflow:

1. You have completed the required safety training for your institution.
2. The GT2 laser has been powered on and has completed its 45-minute warm-up.
3. You have confirmed which objective is installed and which holder is loaded.
4. Your GWL job file has been generated in DeScribe and transferred to the NanoWrite PC.
5. Your resist and developer chemicals are available at the bench.
6. Your substrate has been cleaned according to the procedure in [05_Substrates/substrate_cleaning_procedure.md](../05_Substrates/substrate_cleaning_procedure.md).

If any of these conditions is not met, stop and complete it before proceeding.

---

## How Steps Are Formatted

Each step file follows this structure:

- A one-sentence summary of the step at the top
- A "Why this step matters" section explaining the purpose
- A numbered procedure (what to do, in order)
- A "What can go wrong" table listing common errors and fixes
- Links to related files for deeper reading

Read the full step file before executing it. Do not skim.

---

## Related Modules

- [03_Objectives/](../03_Objectives/README.md) — Objective installation and specifications
- [04_Resists_and_Materials/](../04_Resists_and_Materials/README.md) — Resist properties and handling
- [05_Substrates/](../05_Substrates/README.md) — Substrate preparation
- [06_Software_Workflow/](../06_Software_Workflow/README.md) — DeScribe and NanoWrite procedures
- [08_Development_and_Post_Processing/](../08_Development_and_Post_Processing/README.md) — Development chemicals and UV curing
- [11_Troubleshooting/](../11_Troubleshooting/README.md) — When things go wrong
