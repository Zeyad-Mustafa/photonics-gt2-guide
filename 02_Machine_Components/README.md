# 🖥️ Module 02 — Machine Components

> **"You can't operate what you don't understand."**  
> This module breaks down every physical part of the Nanoscribe GT2 — what it is, what it does, and why it matters for your print.

---

## 🎯 What You Will Learn in This Module

After reading all the files in this folder, you will be able to:

- ✅ Identify every major subsystem of the GT2 by name and function
- ✅ Explain what the femtosecond laser does and why its pulse length matters
- ✅ Describe the difference between galvo scanning and piezo scanning — and know when to use each
- ✅ List the three types of sample holders and which workflows they belong to
- ✅ Understand the Safety Precedence Sequence (SPS) and what it protects
- ✅ Use the AxioVision camera to monitor a live print

---

## 🗂️ Files in This Module

| File | What It Covers |
|---|---|
| `laser_system.md` | The NIR femtosecond fiber laser — wavelength, pulse length, repetition rate |
| `microscope_module.md` | The inverted microscope body, objective turret, sample stage, and piezo actuator |
| `galvo_vs_piezo_scanning.md` | Speed vs. precision — when to use galvo mode, when to use piezo mode |
| `sample_holder_types.md` | Universal holder, Multi-DiLL holder, 5-inch mask holder |
| `safety_enclosure_and_sps.md` | The safety enclosure, SPS panel, green Process light, and top hatch |
| `camera_and_axiovision.md` | Live monitoring camera and AxioVision software during printing |

---

## 🏗️ The GT2 at a Glance — System Overview

The Nanoscribe GT2 is not a single device — it's an **integrated system** made of several subsystems that work together:

```
┌─────────────────────────────────────────────────────┐
│              NANOSCRIBE GT2 SYSTEM                  │
│                                                     │
│  [Femtosecond Laser] ──► [Beam Path & Optics]       │
│                                │                    │
│                          [Galvo Scanner]             │
│                                │                    │
│                    [Inverted Microscope Body]        │
│                     ┌──────────┴──────────┐         │
│              [Objective Turret]     [Piezo Stage]   │
│                     │                    │          │
│              [Sample Holder]      [XY Motor Stage]  │
│                                                     │
│  [AxioVision Camera] ──► [Live View Monitor]        │
│  [SPS Safety Panel]  ──► [Laser + Enclosure Lock]   │
│  [NanoWrite PC]      ──► [Process Control]          │
└─────────────────────────────────────────────────────┘
```

Each component has one job. Understanding all of them makes troubleshooting infinitely easier.

---

## 📐 Why This Module Comes Before Everything Else (Operationally)

You completed **00_Introduction** (what the GT2 is) and **01_Physics_and_Principles** (why it works).  
Now it's time to answer: **what are you actually looking at when you stand in front of the machine?**

Every workflow step in **07_Step_by_Step_Workflows** references physical components of the machine. If you don't know what the piezo stage is, "piezo scan mode" in NanoWrite will be confusing. If you don't know what the SPS is, a safety interlock error will stop you cold.

Read this module first. Operate the machine later.

---

## 🔗 What Comes Next

After this module, proceed to:

- **[03_Objectives/](../03_Objectives/README.md)** — Deep dive into the 10×, 25×, 63×, and 20× objectives
- **[04_Resists_and_Materials/](../04_Resists_and_Materials/README.md)** — Choosing the right photopolymer resin
- **[06_Software_Workflow/](../06_Software_Workflow/README.md)** — DeScribe and NanoWrite software

---

> *Every part of the GT2 was designed to solve a specific physics problem. As you read each file, ask yourself: "What problem does this component solve?"*