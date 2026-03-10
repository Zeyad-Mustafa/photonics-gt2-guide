# 📷 Camera and AxioVision — Live Monitoring

> You can't watch 2PP polymerization happening at the nanoscale with the naked eye, but the GT2's integrated camera and AxioVision software give you a live optical view of the sample during every stage of the process. This file explains what you're seeing and how to use it.

---

## 🧠 What Is the Camera For?

The integrated camera serves several important functions:

| Function | When You Use It |
|---|---|
| **Locating the resist drop** | Before printing — confirming the drop is centered under the objective |
| **Verifying substrate position** | Before printing — checking the substrate edge, alignment marks, or features |
| **Monitoring print progress** | During printing — watching the growing structure in real time |
| **Checking interface detection** | During approach — seeing the fringes that confirm the focal plane is near the interface |
| **Post-print inspection** | After printing — initial quality check before development |

Without the camera, you'd be printing completely blind. The camera is your main feedback loop during the entire workflow.

---

## 🏗️ Hardware: The Camera Module

The GT2 uses a **digital CCD/CMOS camera** mounted to the microscope body's camera port. It captures images via the same optical path as the objective — meaning what the camera sees is exactly what the objective "sees."

| Parameter | Typical Value |
|---|---|
| **Camera type** | Digital CCD or CMOS |
| **Field of view** | Depends on objective (10×: ~1 mm, 25×: ~400 µm, 63×: ~150 µm) |
| **Frame rate** | Live feed, typically 10–30 fps |
| **Illumination source** | Transmitted white light (separate from the NIR laser) |
| **Color** | Typically grayscale or color depending on model |

> 🧠 **The camera uses white light illumination, not the 780 nm laser.** You are seeing your sample under normal visible light — not observing the 2PP process itself. The polymerization is happening at the focal point of the NIR beam, which is invisible to the camera sensor.

---

## 💻 AxioVision Software

**AxioVision** (by Zeiss, the microscope OEM) is the software that receives the camera feed and displays it on the GT2's monitor. It runs alongside NanoWrite and is typically open at all times during operation.

### What AxioVision Shows You

```
┌─────────────────────────────────────────────────────┐
│                  AxioVision Live View                │
│                                                     │
│    ┌─────────────────────────────────────────┐      │
│    │                                         │      │
│    │        Live camera image                │      │
│    │        (substrate surface)              │      │
│    │                                         │      │
│    │   ← field of view depends on objective  │      │
│    │                                         │      │
│    └─────────────────────────────────────────┘      │
│                                                     │
│  Zoom: [1×] [2×] [4×]    Exposure: [ Auto ]         │
│  Capture: [📷 Snapshot]   Record: [⏺ Start]          │
└─────────────────────────────────────────────────────┘
```

### Key AxioVision Controls You'll Use

| Control | What It Does |
|---|---|
| **Exposure / Gain** | Adjusts image brightness — increase if sample is dark, decrease if washed out |
| **Focus (Z)** | Manually adjusting Z in NanoWrite moves the image in/out of focus |
| **Snapshot** | Saves a still image — useful for documenting your sample position |
| **Zoom** | Digital zoom of the camera image (does not change physical field of view) |
| **Crosshair / Center marker** | Shows where the beam center is aligned in the field |

---

## 🔍 What You'll See at Each Stage

### 1. Before Printing — Locating the Drop

Immediately after loading the sample and approaching the objective, you'll see the substrate surface. With the resist drop applied, you should see:

- The edge of the resist drop (a curved boundary)
- The substrate surface features (scratches, particles, substrate edge)
- Interference fringes if you are very close to the glass surface

> ✅ **Good sign:** The drop is visible in the center of the field with a clean, curved edge.  
> ❌ **Bad sign:** No drop visible → either you didn't apply resist, or the drop slid off the substrate.

### 2. During Approach — Interface Fringes

As the piezo stage moves the objective closer to the substrate-resist interface, you'll see **Newton's rings** or **interference fringes** — alternating bright and dark concentric rings or stripes.

```
Camera view during approach:

   (far from interface)        (near interface)
   ___________________      ___________________
   |                 |      |  )) )) )) )) ))  |
   |   Uniform gray  |  →   |  (( (( (( (( ((  |
   |                 |      |  )) )) )) )) ))  |
   |_________________|      |_________________|
                                 ↑
                          Interference fringes
                          = interface is nearby
```

These fringes appear because light reflects from both the objective's front element and the substrate surface, creating optical interference. The appearance of fringes tells you:

- ✅ The objective is within a few micrometers of the surface
- ✅ Interface detection will succeed
- ✅ The refractive index difference (Δn) is sufficient

> ⚠️ **If fringes never appear:** The objective may not be approaching the correct surface, the Δn may be too low, or the substrate is not in the correct orientation. See [11_Troubleshooting/interface_not_found.md](../11_Troubleshooting/interface_not_found.md).

### 3. During Printing — Watching the Structure Grow

Once printing begins, you can watch your structure form in real time. What you'll see depends on the objective:

| Objective | What's Visible During Print |
|---|---|
| 10× | Large features visible; voxels too small to see individually |
| 25× | Layer-by-layer growth visible as increased intensity/contrast |
| 63× | Fine details visible; individual layers sometimes distinguishable |

The structure appears **brighter or more opaque** than the surrounding liquid resin because the polymerized material has a slightly different refractive index and scatters light differently.

> 🧠 **You cannot see the NIR laser beam itself** — it's invisible. What you're seeing is the effect of polymerization (the solidified structure) under white light illumination.

### 4. After Printing — Pre-Development Check

Before moving the sample for development, use AxioVision to do a quick sanity check:

- Is the structure where you expected it?
- Does the overall shape look correct at low magnification?
- Are there any obvious voids, collapses, or misalignments?

Take a snapshot for your lab notebook. This is your baseline record before the development step changes the sample.

---

## ⚠️ Common Camera Issues

| Problem | Likely Cause | Fix |
|---|---|---|
| Image too dark | Exposure too low, or illumination off | Increase exposure in AxioVision; check white light is on |
| Image too bright / washed out | Exposure too high | Decrease exposure |
| No image (black screen) | Camera not connected or AxioVision not running | Check USB/FireWire connection; restart AxioVision |
| Image blurry, won't focus | Z position far from substrate surface | Use coarse Z control to approach the surface |
| Fringes not appearing during approach | Δn too low or wrong substrate orientation | Check substrate orientation; see troubleshooting |

---

## 📸 Best Practices for Documentation

Good camera habits save you hours of troubleshooting:

1. **Take a snapshot before every print** — document the resist drop and substrate position
2. **Take a snapshot after interface detection** — confirm the Z=0 position was found correctly
3. **Take a snapshot after printing** (before development) — record the raw printed structure
4. **Take a snapshot after development** — record the final structure
5. **Save snapshots with meaningful filenames**: `sample01_pre-print_25x_IP-S_2026-03-10.tif`

---

## 🔗 Related Files

- [microscope_module.md](./microscope_module.md) — The optical path the camera shares with the laser
- [05_Substrates/interface_detection_requirements.md](../05_Substrates/interface_detection_requirements.md)
- [11_Troubleshooting/interface_not_found.md](../11_Troubleshooting/interface_not_found.md)
- [06_Software_Workflow/NanoWrite_Software/monitoring_print.md](../06_Software_Workflow/NanoWrite_Software/monitoring_print.md)
- [06_Software_Workflow/NanoWrite_Software/sample_approach.md](../06_Software_Workflow/NanoWrite_Software/sample_approach.md)