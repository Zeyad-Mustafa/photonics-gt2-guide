# 🔭 Machine Overview — Parts of the Photonic Professional GT2

> This page walks you through every visible and functional part of the GT2. Before your first session, read this so nothing surprises you when you stand in front of the machine.

---

## Physical Appearance

The GT2 looks like a large black microscope enclosure sitting on a vibration-isolation table. It is approximately **60 cm wide × 50 cm deep × 80 cm tall** and weighs around 100 kg. It must sit on a **vibration-isolated optical table** or an active isolation platform — even footsteps can ruin a print if the table isn't isolated.

---

## Labeled Diagram (Text Version)

```
                        ┌─────────────────────────────┐
                        │        TOP HATCH LID         │  ← Opens for sample loading
                        │   (only open when safe!)     │
                        └──────────────┬──────────────┘
                                       │
          ┌────────────────────────────▼────────────────────────────┐
          │                    ENCLOSURE BODY                        │
          │                                                          │
          │   ┌──────────────┐        ┌──────────────────────────┐  │
          │   │  MICROSCOPE  │        │   TOUCHSCREEN CONTROLLER │  │
          │   │   MODULE     │        │   (objective selection,   │  │
          │   │              │        │    stage position)        │  │
          │   │  ┌────────┐  │        └──────────────────────────┘  │
          │   │  │SAMPLE  │  │                                       │
          │   │  │HOLDER  │  │        ┌──────────────────────────┐  │
          │   │  └────────┘  │        │   OBJECTIVE TURRET       │  │
          │   │              │        │   (holds 1 objective)    │  │
          │   │  ┌────────┐  │        └──────────────────────────┘  │
          │   │  │PIEZO   │  │                                       │
          │   │  │STAGE   │  │        ┌──────────────────────────┐  │
          │   │  └────────┘  │        │   GALVO SCANNING UNIT    │  │
          │   └──────────────┘        └──────────────────────────┘  │
          │                                                          │
          └──────────────────────────────────────────────────────────┘
                                       │
          ┌────────────────────────────▼────────────────────────────┐
          │                   ELECTRONICS CABINET                    │
          │   Laser module │ SPS controller │ Piezo drivers          │
          └──────────────────────────────────────────────────────────┘

   [GT2 PC]          [Monitor]          [UV Curing Station]
   NanoWrite         AxioVision         (separate unit, 405 nm)
   software          camera feed
```

---

## Part-by-Part Breakdown

### 🔴 Top Hatch Lid
- **What it does:** Provides access to the sample area for loading/unloading samples and changing objectives
- **Safety rule:** NEVER open while the green "Process" light is on
- **How to open safely:**
  1. Click "Exchange Holder" in NanoWrite
  2. Click "Open" — button flashes green
  3. Only then lift the lid

---

### 🟢 SPS Green "Process" Light
- **Location:** On the front panel of the enclosure
- **What it means:** When ON → laser safety interlock is active, laser CAN fire
- **What it means:** When OFF → safe to open the lid
- **Never bypass this light** — the laser is Class IV (can cause permanent eye damage and skin burns)

---

### 🔵 Microscope Module
- **What it does:** Houses the objective lens, the piezo stage, and the sample holder. This is the heart of the machine.
- **Piezo Stage:** Moves the sample in X, Y, Z with ~10 nm precision over a 300×300×300 µm range
- **Galvo Unit:** Steers the laser beam with mirrors for fast 400×400 µm field scanning

---

### 🟡 Objective Turret
- **What it does:** Holds the currently installed objective lens
- **Capacity:** One objective at a time
- **Objectives available:** 10×, 20×, 25×, 63×
- **Never leave two objectives installed** — resin contamination between sessions

---

### 🟠 Sample Holder
- **What it does:** Clamps your substrate in place above the objective
- **Types available:**
  - Universal Holder (most substrates)
  - Multi-DiLL Si Wafer Holder (for 10× + silicon)
  - 5" Mask Holder (for photomask substrates)
- **Critical:** The substrate goes face-down (resist side toward objective)

---

### 🟣 Touchscreen Controller
- **What it does:** Physical interface for moving the stage manually, selecting objectives, and monitoring position
- **When to use:** During sample approach, manual focus checks, objective switching
- **Do not use** to move the stage during a print job — NanoWrite controls this automatically

---

### ⚪ GT2 Dedicated PC
- **Runs:** NanoWrite software only
- **Do NOT install other software** on this machine
- **Do NOT use** it for heavy computation (DeScribe runs on the GPU computer)
- Connected to the machine via dedicated USB and serial interfaces

---

### 🔵 UV Curing Station (Separate Unit)
- **Location:** Usually next to the GT2 on the bench
- **Wavelength:** 405 nm (near-UV / violet)
- **Purpose:** Post-curing of printed structures after development
- **Safety:** Has a yellow filter window for observation — do not look at the lamp directly
- **Auto shutoff:** Sets a timer — never run more than 40 minutes

---

### 💻 AxioVision Camera Monitor
- **What it does:** Displays the live camera feed from inside the microscope during printing
- **What to watch:** The glowing laser trace moving through the resin — confirms printing is happening
- **Useful for:** Spotting print failures, checking sample position, verifying interface detection

---

## Workflow of Light Through the Machine

```
Fiber laser (780 nm, 100 fs, 80 MHz)
        ↓
Beam expander & conditioning optics
        ↓
Galvo scanning mirrors (fast XY steering)
        ↓
Objective lens (focuses beam to voxel)
        ↓
Focal point inside resin (TWO-PHOTON ABSORPTION)
        ↓
Voxel polymerizes → solid structure forms
```

---

## Before You Touch Anything — Quick Safety Checklist

- [ ] Green "Process" light is OFF before opening the lid
- [ ] You have completed laser safety training
- [ ] You are wearing laser safety goggles rated for 780 nm if the enclosure is open
- [ ] Fume hood is running if you are handling resins or solvents
- [ ] You have read the lab SOP for the GT2

---

> 🔗 **Next:** Go to **[Section 01 — Physics and Principles](../01_Physics_and_Principles/README.md)** to understand the science behind what you just read.