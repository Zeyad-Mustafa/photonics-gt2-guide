# ⚡ The Laser System

> The GT2's laser is the engine behind everything. This page explains what kind of laser it is, why its properties are exactly what Two-Photon Polymerization (2PP) requires, and what you should know about it as an operator.

---

## 🧠 Why Does the Laser Matter?

Without the laser, there is no printing. But not just *any* laser works for 2PP — the physics of two-photon absorption (explained in **[01_Physics_and_Principles](../01_Physics_and_Principles/README.md)**) demands a very specific type of light source.

The GT2 uses a **near-infrared (NIR) femtosecond pulsed fiber laser**. Each word in that description is load-bearing:

| Term | What It Means | Why It Matters |
|---|---|---|
| **Near-infrared (NIR)** | Wavelength of ~780 nm (invisible to human eyes) | Single photons at this wavelength don't have enough energy to cure the resin alone — only *two* arriving simultaneously do |
| **Femtosecond** | Pulse duration of ~100 femtoseconds (100 × 10⁻¹⁵ seconds) | Ultra-short pulses create extreme instantaneous intensity at the focal point without depositing too much average heat |
| **Pulsed** | The laser fires in rapid bursts, not continuously | Peak power per pulse is ~100,000× higher than a continuous beam of the same average power |
| **Fiber laser** | Light is guided through optical fiber, not free-space optics | More compact, thermally stable, and alignment-free compared to older Ti:Sapphire systems |

---

## 📋 Key Specifications

| Parameter | Value |
|---|---|
| **Wavelength** | 780 nm (NIR) |
| **Pulse duration** | ~100 femtoseconds (fs) |
| **Repetition rate** | ~80 MHz |
| **Average output power** | Up to ~150 mW (system-dependent) |
| **Laser class** | Class IV (most hazardous — see [12_Safety](../12_Safety/README.md)) |
| **Laser type** | Mode-locked fiber laser |

---

## 🔍 Deep Dive: What Is a Femtosecond?

A femtosecond is **one quadrillionth of a second** (10⁻¹⁵ s).

To put that in perspective:

- 1 femtosecond is to 1 second what 1 second is to **31.7 million years**
- Light travels only about **0.3 micrometers** (300 nm) in 1 femtosecond
- A human nerve impulse takes roughly **10 milliseconds** — that's 10 trillion femtoseconds

This absurdly short pulse duration is what makes 2PP possible. By compressing all the laser energy into a 100 fs window, the instantaneous peak power at the focal point becomes high enough for two photons to be absorbed simultaneously — even though the average power is modest and the overall heat deposited is low.

---

## 🔁 Repetition Rate: 80 MHz

The laser fires at **80 million pulses per second** (80 MHz). This is not something you control directly — it's a fixed property of the laser hardware.

Each pulse lasts ~100 fs, and the gap between pulses is about **12.5 nanoseconds** (12,500,000 femtoseconds). So the laser is "off" for the vast majority of time — but the pulses come so frequently that the focal point receives a smooth, continuous exposure as the beam scans across the sample.

> 🧠 **Why this matters:** The 80 MHz repetition rate, combined with typical scan speeds of 1–100 mm/s, means each point in the resin is hit by dozens to hundreds of pulses as the beam passes over it. The cumulative dose from these pulses is what triggers polymerization.

---

## 🔦 Beam Path: From Fiber to Focus

After exiting the laser module, the beam travels along a controlled optical path inside the GT2:

```
Fiber Laser Output
      │
      ▼
Beam Conditioning Optics (collimation, power control)
      │
      ▼
Acousto-Optic Modulator (AOM) — fast on/off shutter
      │
      ▼
Galvo Scanner Mirrors (for galvo scan mode)
      │
      ▼
Scan Lens + Tube Lens
      │
      ▼
Objective Lens (10×, 25×, or 63×)
      │
      ▼
Focal Point in Resin ← This is where polymerization occurs
```

You, as an operator, don't adjust any of these optical components. They are factory-aligned. What you *do* control is:

- **Laser power** (set as a percentage in NanoWrite or DeScribe)
- **Scan speed** (mm/s, set in DeScribe)
- **Which objective** is in the beam path (physical swap)
- **Whether the laser is enabled** (controlled by NanoWrite and the SPS)

---

## ⚙️ Laser Power: What "100%" Means

When you set laser power to "50%" in the software, that is **not** 50% of the laser's maximum physical output. It refers to a **scaled value within the operating window** defined by the system. The actual mW value at the sample depends on:

- Which objective is installed (different transmissions)
- The attenuation/filter settings in the beam path
- The AOM efficiency

> ⚠️ **Important:** Never assume absolute mW values from percentage settings alone. Different resist/objective combinations require specific calibrated power settings — always refer to the parameter tables in **[13_Key_Parameters_Reference](../13_Key_Parameters_Reference/README.md)**.

---

## 🌡️ Laser Warm-Up: Why You Must Wait 45 Minutes

The femtosecond laser requires a **45-minute warm-up period** before printing. This is not optional.

**Why?**

Mode-locked lasers are highly sensitive to temperature. During warm-up:
- The laser cavity reaches thermal equilibrium
- The pulse timing (mode-locking) stabilizes
- Output power becomes consistent and reproducible

Printing before the warm-up is complete will give you **inconsistent voxel sizes, power drift, and unpredictable results**. The NanoWrite software tracks this warm-up and will warn you if you try to print too soon.

> 🔢 **Procedure:** Power on the GT2 → enable the laser in NanoWrite → wait 45 minutes → begin printing. See **[06_Software_Workflow/NanoWrite_Software/startup_procedure.md](../06_Software_Workflow/NanoWrite_Software/startup_procedure.md)**.

---

## 🛡️ Laser Safety

The GT2 uses a **Class IV laser** — the highest hazard class. Invisible NIR light at 780 nm can cause **permanent retinal damage** without triggering the blink reflex (because you can't see it).

The machine's safety enclosure and SPS system prevent beam exposure during normal operation. However, you should always:

- Know where the emergency stop is
- Never attempt to open the enclosure during an active print
- Wear appropriate laser safety eyewear if performing any open-beam service (trained personnel only)

Full laser safety information: **[12_Safety/laser_safety_overview.md](../12_Safety/laser_safety_overview.md)**

---

## 🔗 Related Files

- [01_Physics_and_Principles/femtosecond_laser_explained.md](../01_Physics_and_Principles/femtosecond_laser_explained.md)
- [01_Physics_and_Principles/one_photon_vs_two_photon_absorption.md](../01_Physics_and_Principles/one_photon_vs_two_photon_absorption.md)
- [12_Safety/laser_safety_overview.md](../12_Safety/laser_safety_overview.md)
- [13_Key_Parameters_Reference/laser_parameters.md](../13_Key_Parameters_Reference/laser_parameters.md)
- [06_Software_Workflow/NanoWrite_Software/startup_procedure.md](../06_Software_Workflow/NanoWrite_Software/startup_procedure.md)