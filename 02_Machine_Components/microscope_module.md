# 🔭 The Microscope Module

> The GT2 is built around an **inverted microscope**. Understanding the microscope's anatomy explains why samples are loaded the way they are, why certain objectives need oil, and how the system achieves nanoscale positional accuracy.

---

## 🧠 Why an Inverted Microscope?

In a standard ("upright") microscope, the objective sits above the sample and looks down. The GT2 uses an **inverted** design — the objective sits *below* the sample stage and looks **upward**.

This inversion is critical for 2PP printing:

| Inverted Design Advantage | Explanation |
|---|---|
| **Gravity keeps the resin in place** | The resist drop sits on top of the substrate, held down by gravity — no risk of it sliding off |
| **Objective contacts the resin from below** | In DiLL mode, the objective tip is submerged in the resin from below, giving perfect optical contact |
| **Substrate faces down toward the objective** | Allows printing directly onto the substrate-resin interface |
| **Large sample stage is accessible from above** | Easy to load/unload samples without moving the objective |

---

## 🏗️ Anatomy of the Microscope Module

```
                    ┌──────────────────────────────┐
                    │        SAMPLE STAGE          │
                    │  (XY motorized, 100×100 mm)  │
                    │  ┌────────────────────────┐  │
                    │  │     SAMPLE HOLDER      │  │
                    │  │  (substrate face-down) │  │
                    │  └────────────┬───────────┘  │
                    └───────────────┼──────────────┘
                                    │  ↑ upward beam
                    ┌───────────────┼──────────────┐
                    │        PIEZO STAGE           │
                    │  (Z-axis, 300 µm range)      │
                    └───────────────┼──────────────┘
                                    │
                    ┌───────────────┼──────────────┐
                    │     OBJECTIVE TURRET         │
                    │  (holds up to 6 objectives)  │
                    │  [ 10× ] [ 25× ] [ 63× ] ... │
                    └───────────────┼──────────────┘
                                    │
                    ┌───────────────▼──────────────┐
                    │   LASER BEAM (from below)    │
                    └──────────────────────────────┘
```

---

## 🎯 The Objective Turret

The GT2 has a motorized **objective turret** that holds multiple objectives simultaneously. You switch between them using the NanoWrite software — the turret rotates to bring the selected objective into the beam path.

> ⚠️ **Never physically push the turret by hand** while the machine is powered on. Always use the software controls or the SPS panel buttons to rotate it. Forcing the turret can damage the objectives or misalign the optics.

The turret can typically hold:
- 10× objective
- 25× objective
- 63× objective
- 20× air objective (if installed)
- Additional empty slots or reserved positions

Each objective has a different working distance, numerical aperture, and immersion mode. Full details are in **[03_Objectives/](../03_Objectives/README.md)**.

---

## 📐 The Sample Stage (XY Motors)

The **large-range XY motorized stage** is responsible for coarse positioning of the sample. Its specs:

| Parameter | Value |
|---|---|
| **Travel range** | 100 × 100 mm |
| **Positional accuracy** | ~1 µm |
| **Drive type** | Stepper motor with encoder feedback |
| **Speed** | Up to several mm/s (for repositioning, not printing) |

The XY stage is used for:
- Moving to the starting position before a print
- Stitching multiple print fields together (field stitching)
- Repositioning to a fresh resist area if a print fails

> 🧠 **Key distinction:** The XY stage moves the *sample* — not the laser. The laser beam position is fixed; the sample moves underneath it.

---

## ⚡ The Piezo Stage (Z-axis Precision)

The **piezo actuator** is the heart of the GT2's precision. It controls the Z position of the focal point with sub-nanometer resolution.

| Parameter | Value |
|---|---|
| **Travel range** | 300 µm (0.3 mm) |
| **Resolution** | ~10 nm |
| **Response time** | Sub-millisecond |
| **Drive mechanism** | Piezoelectric crystal (expands/contracts under voltage) |

The piezo stage is used in **Piezo Scan Mode** (explained in detail in [galvo_vs_piezo_scanning.md](./galvo_vs_piezo_scanning.md)):
- Moving the focal point **up and down** through the resin (Z-axis)
- Fine XY correction at the nanoscale
- Tilt correction for non-flat substrates

> ⚠️ **Do not exceed the piezo's 300 µm range.** If your structure is taller than 300 µm, you must use step-and-repeat stitching or galvo mode. Attempting to drive the piezo beyond its range will trigger a software error or, in rare cases, physically damage the actuator.

---

## 🔍 The Interface Detection System

Before any print can begin, the GT2 must find the **substrate-resin interface** — the exact Z position where the substrate surface meets the liquid resin.

This is done optically:
1. The laser is set to very low power (below the polymerization threshold)
2. The system scans in Z while monitoring reflected light intensity
3. A sharp change in reflectivity marks the interface (due to the refractive index change, Δn, at the substrate surface)
4. The system sets Z = 0 at this interface

> 🧠 **Why Δn matters:** The interface detection relies on a **minimum refractive index difference of Δn ≥ 0.04** between the substrate and the resin. If Δn is too small (e.g., printing on a substrate with nearly the same n as the resist), the system cannot find the interface. See **[05_Substrates/interface_detection_requirements.md](../05_Substrates/interface_detection_requirements.md)**.

---

## 📡 The Transmitted Light Illumination

The GT2 has a conventional white-light illumination source for visual inspection of the sample. This is the light you use (via the AxioVision camera) to:

- Check the sample is positioned correctly
- Verify the resist drop is in the field of view
- Monitor the structure during and after printing

This light source does **not** interact with the 2PP process — it is separate from the NIR laser path.

---

## 🔗 Related Files

- [03_Objectives/README.md](../03_Objectives/README.md) — Objectives in detail
- [galvo_vs_piezo_scanning.md](./galvo_vs_piezo_scanning.md) — Scanning modes
- [05_Substrates/interface_detection_requirements.md](../05_Substrates/interface_detection_requirements.md) — Δn requirements
- [camera_and_axiovision.md](./camera_and_axiovision.md) — Live camera monitoring
- [09_Printing_Modes/piezo_scan_mode.md](../09_Printing_Modes/piezo_scan_mode.md)