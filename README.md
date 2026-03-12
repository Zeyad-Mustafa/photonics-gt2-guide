# 🔬 Nanoscribe Photonic Professional GT2 — Complete Beginner's Guide
![gt2](https://github.com/user-attachments/assets/75f09c94-a9b1-40b2-9c01-82a8d28a8948)

> **A comprehensive, zero-to-expert resource for learning 3D nanofabrication with the Nanoscribe Photonic Professional GT2.**  
> Built for students, researchers, and engineers who have never touched a two-photon polymerization system before.

---

## 📌 What Is This Project?

The **Nanoscribe Photonic Professional GT2** is one of the world's most advanced 3D micro/nanoprinters. It uses a technology called **Two-Photon Polymerization (2PP)** to write 3D structures with feature sizes as small as **160 nanometers** — that's roughly 500 times thinner than a human hair.

This GitHub project is your **complete beginner's handbook**. Every folder below contains a deep-dive into one specific aspect of the machine — from the physics behind it, to the objectives you use, to the resists (photosensitive materials) you print with, all the way to real workflows, troubleshooting, and advanced techniques.

---

## 🗺️ Project Map — Folder Structure
 
```
photonics-gt2-guide/
│
├── README.md                        ← You are here — project overview
│
├── 00_Introduction/
│   ├── README.md                    ← What is the GT2? Who should use this guide?
│   ├── what_is_2PP.md               ← Two-Photon Polymerization explained simply
│   ├── how_it_differs_from_regular_3D_printing.md
│   ├── key_terms_glossary.md        ← Voxel, GWL, DiLL, STL, hatch, slice...
│   └── machine_overview_diagram.md ← Labeled diagram of the physical machine
│
├── 01_Physics_and_Principles/
│   ├── README.md                    ← Module overview & learning objectives
│   ├── light_and_photons_basics.md
│   ├── one_photon_vs_two_photon_absorption.md
│   ├── femtosecond_laser_explained.md   ← 780 nm NIR laser, 100 fs pulses, 80 MHz
│   ├── voxel_formation.md               ← What a voxel is, how it's shaped, aspect ratio
│   ├── diffraction_limit_and_beyond.md  ← How 2PP breaks the diffraction limit
│   └── polymerization_chemistry.md      ← How the resin solidifies at the focal point
│
├── 02_Machine_Components/
│   ├── README.md
│   ├── laser_system.md              ← NIR femtosecond fiber laser specs
│   ├── microscope_module.md         ← Objective turret, sample stage, piezo
│   ├── galvo_vs_piezo_scanning.md   ← Speed vs precision — when to use which
│   ├── sample_holder_types.md       ← Universal, Multi-DiLL, 5" mask holder
│   ├── safety_enclosure_and_sps.md  ← SPS panel, green Process light, top hatch
│   └── camera_and_axiovision.md     ← Live monitoring during printing
│
├── 03_Objectives/
│   ├── README.md                    ← Overview of all 4 objectives
│   ├── objective_comparison_table.md
│   │
│   ├── 10x_objective/
│   │   ├── overview.md              ← NA 0.3, 700 µm WD — large-scale printing
│   │   ├── when_to_use.md           ← mm-sized structures, fast printing
│   │   ├── compatible_resists.md    ← IP-Q, IPX-Q, IPX-Clear
│   │   ├── compatible_substrates.md ← Silicon wafers, 25×25 mm Nanoscribe slides
│   │   ├── voxel_dimensions.md      ← Largest voxel, lowest resolution
│   │   ├── print_field_and_limits.md
│   │   └── installation_steps.md   ← How to physically mount the 10x
│   │
│   ├── 25x_objective/
│   │   ├── overview.md              ← NA 0.8, 380 µm WD — mesoscale printing
│   │   ├── when_to_use.md           ← 1 mm³ structures, balanced speed/resolution
│   │   ├── adjustment_ring_guide.md ← Critical: set to "Glyc" (3 longest bars)
│   │   ├── compatible_resists.md    ← IP-S, IP-Visio, IP-PDMS, IP-Q, IPX-Clear
│   │   ├── compatible_substrates.md ← ITO-coated glass, silicon
│   │   ├── voxel_dimensions.md
│   │   ├── dill_mode_explained.md   ← Dip-In Laser Lithography with 25x
│   │   └── installation_steps.md
│   │
│   ├── 63x_objective/
│   │   ├── overview.md              ← NA 1.4, 360 µm WD — highest resolution
│   │   ├── when_to_use.md           ← Sub-200 nm features, highest precision
│   │   ├── oil_immersion_mode.md    ← Immersion oil 518F, refractive index matching
│   │   ├── compatible_resists.md    ← IP-Dip2, IP-Dip, IPX-Clear
│   │   ├── compatible_substrates.md ← Quartz, silicon, 170 µm borosilicate glass
│   │   ├── voxel_dimensions.md      ← ~160 nm lateral, ~500 nm axial
│   │   ├── fiber_ring_installation.md ← The 63x uses a fiber ring (not silicone)
│   │   └── installation_steps.md
│   │
│   └── 20x_objective/
│       ├── overview.md              ← Air objective — 2D and pseudo-3D only
│       ├── when_to_use.md           ← Spin-coated i-line resists, 2D patterning
│       ├── compatible_resists.md    ← Standard i-line photoresists
│       └── limitations.md          ← Air mode, no DiLL, limited z-range
│
├── 04_Resists_and_Materials/
│   ├── README.md                    ← What is a resist? How do you choose one?
│   ├── resist_selection_guide.md    ← Decision tree: what resist for my project?
│   │
│   ├── IP_Dip2/
│   │   ├── overview.md              ← Highest resolution, refractive index 1.511
│   │   ├── properties.md            ← Viscosity, sensitivity, shrinkage
│   │   ├── use_with_63x.md
│   │   └── handling_and_storage.md
│   │
│   ├── IP_S/
│   │   ├── overview.md              ← Low shrinkage, smooth surfaces, n=1.478
│   │   ├── properties.md
│   │   ├── use_with_25x.md
│   │   └── handling_and_storage.md
│   │
│   ├── IP_Q/
│   │   ├── overview.md              ← Fast large prints, n=1.48, use with 10x
│   │   ├── properties.md
│   │   ├── drop_casting_technique.md ← Only 1–2 drops on the polished side
│   │   └── handling_and_storage.md
│   │
│   ├── IP_Visio/
│   │   ├── overview.md              ← Biocompatible, very low fluorescence
│   │   ├── bio_applications.md      ← Cell scaffolds, lab-on-chip
│   │   └── handling_and_storage.md
│   │
│   ├── IP_PDMS/
│   │   ├── overview.md              ← Soft, flexible, elastic structures
│   │   ├── applications.md          ← Microfluidics, soft robotics
│   │   └── handling_and_storage.md
│   │
│   ├── IPX_Q/
│   │   ├── overview.md              ← Better resolution than IP-Q, slight color
│   │   └── comparison_with_IP_Q.md
│   │
│   ├── IPX_Clear/
│   │   ├── overview.md              ← Highly transparent, all objectives compatible
│   │   ├── optical_applications.md  ← Lenses, waveguides, photonic devices
│   │   └── handling_and_storage.md
│   │
│   ├── GP_Silica/
│   │   ├── overview.md              ← Fused silica beads — prints glass structures
│   │   ├── workflow_special_steps.md ← 8-hour time limit, furnace sintering at 1500°C
│   │   └── debinding_and_sintering.md
│   │
│   └── i_line_photoresists/
│       ├── overview.md              ← For use with 20x air objective
│       └── spin_coating_guide.md
│
├── 05_Substrates/
│   ├── README.md                    ← What substrates can the GT2 print on?
│   ├── substrate_compatibility_table.md
│   ├── ITO_coated_glass.md          ← Standard for 25x DiLL, ITO side facing down
│   ├── silicon_wafers.md            ← Cutting 25mm squares with DISCO saw
│   ├── borosilicate_glass_170um.md  ← For 63x through-glass oil immersion
│   ├── quartz_substrates.md
│   ├── custom_substrates.md         ← Polymers, crystals, flexible films
│   ├── interface_detection_requirements.md ← Δn > 0.04 minimum for auto-focus
│   └── substrate_cleaning_procedure.md     ← Acetone → IPA → water (or oxygen plasma)
│
├── 06_Software_Workflow/
│   ├── README.md                    ← Software stack: CAD → DeScribe → NanoWrite
│   │
│   ├── CAD_Design/
│   │   ├── README.md
│   │   ├── designing_for_2PP.md     ← Design rules: min feature size, overhangs
│   │   ├── recommended_cad_tools.md ← AutoCAD, SolidWorks, Fusion 360, OpenSCAD
│   │   ├── stl_export_guide.md      ← STL format, ASCII vs binary, checking normals
│   │   ├── gwl_scripting_intro.md   ← Writing GWL code directly for automation
│   │   └── design_rules_checklist.md
│   │
│   ├── DeScribe_Software/
│   │   ├── README.md                ← What DeScribe does (STL → GWL)
│   │   ├── installation_and_setup.md ← Use CNF GPU computer, NOT the Nanoscribe PC
│   │   ├── importing_stl.md
│   │   ├── slicing_parameters.md    ← Slice distance, hatch distance, laser power
│   │   ├── hatching_strategies.md   ← Shell & scaffold, solid fill, contour
│   │   ├── scaling_and_orientation.md ← Lock aspect ratio, structure scaling
│   │   ├── 3d_preview_guide.md      ← F5 to compile, play animation, color by height
│   │   ├── generating_gwl_files.md  ← _data.gwl and _job.gwl explained
│   │   ├── multi_print_jobs.md      ← Master job.gwl, multiple parts per job
│   │   ├── stagegoTo_commands.md    ← StageGoToX / StageGoToY for custom center
│   │   └── common_errors.md        ← "box instead of model" → change rendering mode
│   │
│   └── NanoWrite_Software/
│       ├── README.md                ← Operating the machine in real time
│       ├── startup_procedure.md     ← 45-minute laser warm-up, power sequence
│       ├── exchange_holder_dialog.md
│       ├── sample_approach.md       ← Interface finder, fringe detection
│       ├── loading_gwl_job.md
│       ├── monitoring_print.md      ← AxioVision live camera feed
│       ├── estimating_print_time.md ← Check BEFORE starting
│       └── shutdown_procedure.md
│
├── 07_Step_by_Step_Workflows/
│   ├── README.md                    ← Choose your workflow path
│   │
│   ├── Workflow_A_63x_DiLL_IP_Dip2/
│   │   ├── README.md                ← Highest resolution workflow
│   │   ├── step_01_design_your_structure.md
│   │   ├── step_02_export_stl.md
│   │   ├── step_03_slice_in_describe.md
│   │   ├── step_04_prepare_substrate.md    ← Clean quartz/silicon
│   │   ├── step_05_apply_resist.md         ← Drop cast IP-Dip2
│   │   ├── step_06_install_63x_objective.md ← With fiber ring
│   │   ├── step_07_load_sample_holder.md
│   │   ├── step_08_find_interface.md
│   │   ├── step_09_run_print_job.md
│   │   ├── step_10_development.md          ← Remove unpolymerized resin
│   │   ├── step_11_uv_curing.md            ← 405 nm, up to 20 min
│   │   ├── step_12_characterization.md     ← SEM, optical microscopy
│   │   └── troubleshooting.md
│   │
│   ├── Workflow_B_25x_DiLL_IP_S/
│   │   ├── README.md                ← Mesoscale balanced workflow
│   │   ├── step_01_design_your_structure.md
│   │   ├── step_02_export_stl.md
│   │   ├── step_03_slice_in_describe.md    ← Select 25x in dropdown, click Slice
│   │   ├── step_04_prepare_ITO_substrate.md ← ITO side facing objective (down)
│   │   ├── step_05_apply_IP_S_resist.md
│   │   ├── step_06_install_25x_objective.md ← Set adjustment ring to "Glyc"
│   │   ├── step_07_load_sample_holder.md
│   │   ├── step_08_find_interface.md
│   │   ├── step_09_run_print_job.md
│   │   ├── step_10_development.md
│   │   ├── step_11_uv_curing.md
│   │   └── troubleshooting.md
│   │
│   ├── Workflow_C_10x_Large_Scale/
│   │   ├── README.md                ← mm-scale fast printing
│   │   ├── step_01_design.md
│   │   ├── step_02_prepare_silicon_substrate.md
│   │   ├── step_03_apply_IP_Q.md    ← Only 1–2 drops! Semi-spherical drop preferred
│   │   ├── step_04_install_10x.md   ← Use Multi-DiLL Si Wafer holder setting
│   │   ├── step_05_run_print.md     ← Do NOT use other objectives with 10x
│   │   ├── step_06_development.md
│   │   └── troubleshooting.md
│   │
│   └── Workflow_D_Glass_Structures_GP_Silica/
│       ├── README.md
│       ├── special_requirements.md  ← 8-hour time limit, 1500°C furnace needed
│       ├── print_steps.md
│       └── post_processing.md       ← Debinding and sintering stages
│
├── 08_Development_and_Post_Processing/
│   ├── README.md
│   ├── what_is_development.md       ← Removing uncured resin after printing
│   ├── development_solvents.md      ← PGMEA, IPA, SU-8 developer by resist type
│   ├── development_times_table.md
│   ├── ipa_rinse_procedure.md
│   ├── uv_curing_station.md         ← 405 nm, ≤40 min, auto shutoff, yellow filter
│   ├── oxygen_plasma_treatment.md   ← Improves wettability but changes surface
│   ├── scaffold_and_shell_printing.md ← Reduce print time with smart infill
│   └── secondary_fabrication.md     ← Using prints as molds for PVD, CVD, ALD, electrodeposition
│
├── 09_Printing_Modes/
│   ├── README.md
│   ├── dill_mode.md                 ← Dip-in Laser Lithography — main mode
│   ├── oil_immersion_mode.md        ← 3D SF Oil for 63x through-glass
│   ├── air_mode.md                  ← 20x for 2D/pseudo-3D on spin-coated resists
│   ├── piezo_scan_mode.md           ← 300×300×300 µm range, ~10 nm accuracy
│   ├── galvo_scan_mode.md           ← 400×400 µm range, high speed layer printing
│   ├── inverted_immersion_mode.md   ← 25x/63x with spin-coated i-line resists
│   └── tilt_correction_mode.md      ← For non-flat substrates (piezo mode only)
│
├── 10_Applications/
│   ├── README.md
│   ├── micro_optics.md              ← Lenses, beam splitters, waveguides
│   ├── microfluidics.md             ← Channels, chambers, mixers
│   ├── mems_structures.md           ← Actuators, cantilevers, sensors
│   ├── biomedical.md                ← Cell scaffolds, tissue engineering, drug delivery
│   ├── photonic_devices.md          ← Photonic crystals, resonators, couplers
│   ├── micro_robotics.md            ← Swimming microrobots, untethered devices
│   ├── nanostructures.md            ← Sub-500 nm features, metamaterials
│   ├── soft_structures.md           ← IP-PDMS flexible devices
│   └── metallic_structures.md       ← Using printed polymer as mold for electroplating
│
├── 11_Troubleshooting/
│   ├── README.md
│   ├── structure_not_adhering.md    ← Substrate prep, oxygen plasma tips
│   ├── structure_washed_off.md      ← Add protective walls around thin features
│   ├── flat_resist_drop_problem.md  ← Semi-spherical drop = better interface finding
│   ├── interface_not_found.md       ← Δn too low, refractive index mismatch
│   ├── model_shows_as_box.md        ← Change rendering mode in DeScribe
│   ├── print_taking_too_long.md     ← Use galvo mode, scaffold printing, lower fill
│   ├── overexposure_and_blooming.md
│   ├── underexposure_and_voids.md
│   ├── sps_safe_state_error.md      ← Green Process light issue, hatch not closed
│   ├── objective_crashing.md        ← Safety procedures, do not overtighten
│   ├── thin_features_collapsing.md
│   └── gp_silica_print_timeout.md   ← 8-hour limit management
│
├── 12_Safety/
│   ├── README.md
│   ├── laser_safety_overview.md     ← NIR femtosecond Class IV laser hazards
│   ├── chemical_safety.md           ← Resists, developers, IPA — fume hood use
│   ├── uv_curing_eye_safety.md      ← 405 nm not harmful but very bright
│   ├── sps_safety_system.md         ← What the safety precedence sequence does
│   ├── emergency_procedures.md
│   └── required_training_checklist.md
│
├── 13_Key_Parameters_Reference/
│   ├── README.md
│   ├── objective_specs_full_table.md   ← NA, WD, voxel size, print field, volume
│   ├── resist_properties_table.md      ← n, viscosity, shrinkage, compatibility
│   ├── laser_parameters.md            ← 780 nm, 100 fs, 80 MHz, power range
│   ├── stage_ranges_table.md          ← Piezo: 300 µm³, Galvo: 400×400 µm
│   ├── build_volume_table.md          ← Total: 100×100×8 mm³
│   ├── feature_size_limits.md         ← Min 160 nm lateral, ~500 nm axial
│   └── scanning_speed_table.md
│
├── 14_Glossary/
│   ├── README.md
│   └── full_glossary.md             ← 60+ terms: 2PP, voxel, DiLL, GWL, STL, NA, WD...
│
├── 15_Resources_and_Further_Reading/
│   ├── README.md
│   ├── official_nanoscribe_links.md
│   ├── university_SOPs.md           ← Cornell, Purdue, EPFL, Stanford, UMD SOPs
│   ├── key_papers.md                ← Foundational 2PP research papers
│   ├── video_tutorials.md           ← Recommended YouTube and NanoGuide videos
│   ├── community_forums.md
│   └── courses_and_certifications.md ← OP-TEC, IEEE Photonics, Stonehill, CU Boulder
│
└── 16_Contributing/
    ├── README.md
    ├── how_to_contribute.md
    ├── content_guidelines.md
    └── issue_templates/
        ├── new_section_request.md
        ├── correction.md
        └── add_application_example.md
```

---

## 🚀 Where to Start (Recommended Learning Path)

### If you have ZERO background in photonics or microscopy:
```
00_Introduction → 01_Physics_and_Principles → 14_Glossary → 03_Objectives → 04_Resists
```

### If you understand the basics and want to run your first print:
```
03_Objectives → 04_Resists → 05_Substrates → 06_Software_Workflow → 07_Step_by_Step_Workflows
```

### If you're troubleshooting a specific issue:
```
11_Troubleshooting → 13_Key_Parameters_Reference
```

### If you want to explore applications:
```
10_Applications → 08_Development_and_Post_Processing
```

---

## 🔑 Key Concepts at a Glance

| Concept | Plain English |
|---|---|
| **2PP** | Two photons hit a point simultaneously → tiny spot cures, nothing else does |
| **Voxel** | The 3D equivalent of a pixel — the smallest printable unit |
| **DiLL** | The objective dips directly into the liquid resin for best focus |
| **GWL** | The printer's native language — like G-code for nanoscale printing |
| **DeScribe** | Nanoscribe's software that converts STL files into GWL code |
| **Slicing** | Cutting your 3D model into layers the printer can follow |
| **Hatching** | The fill pattern inside each layer |
| **Development** | The chemistry step that washes away uncured resin after printing |

---

## 🧪 Objective Quick-Pick Guide

| Your Goal | Use This Objective | Paired Resist |
|---|---|---|
| Highest resolution < 200 nm | **63×** (NA 1.4) | IP-Dip2 |
| Balanced precision + speed | **25×** (NA 0.8) | IP-S or IP-Visio |
| Large mm-scale structures fast | **10×** (NA 0.3) | IP-Q or IPX-Q |
| 2D patterning on spin-coated wafer | **20×** (air) | i-line photoresist |

---

## 📂 How to Use This Repository

Each folder contains its own `README.md` that explains the **learning objective** of that section, **what you will be able to do** after reading it, and **links to all the files within it**.

Files are written in Markdown. They include:
- ✅ Plain-English explanations (no assumed prior knowledge)
- 📊 Tables for quick comparison
- 🔢 Step-by-step numbered procedures
- ⚠️ Warnings and common mistakes
- 🔗 Links to official SOPs, datasheets, and videos
- 🧠 "Why does this matter?" context boxes

---

## 📋 Section Content Preview

### `03_Objectives/README.md` will contain:
- What an objective is and why it matters
- How the numerical aperture (NA) determines resolution
- How to physically install and remove each objective
- A complete comparison table of all 4 objectives
- Decision guide: which objective for which job?

### `04_Resists_and_Materials/README.md` will contain:
- What a photoresist is (explained from scratch)
- Why the resin matters as much as the objective
- Full resist selection decision tree
- Handling, storage, and safety for each resist
- A comparison table of all IP-series resists

### `07_Step_by_Step_Workflows/` will contain:
- 4 complete end-to-end workflows (A through D)
- Each workflow has 10–13 individually numbered steps
- Each step specifies: what to do, why you do it, and what can go wrong
- Photographs and diagrams embedded at each step

---

## 🤝 Contributing

This project is open to contributions! If you:
- Spot an error or outdated information
- Want to add a new application example
- Have a real print from a GT2 to share
- Want to translate content

Please read `16_Contributing/how_to_contribute.md` before opening a pull request.

---

## 📜 License

This project is released under the [MIT License](LICENSE). All third-party SOPs and documentation are linked by reference and are © their respective institutions.

---

> *Built with ❤️ for anyone who has ever stood in front of a Nanoscribe and thought: "Where do I even begin?"*
