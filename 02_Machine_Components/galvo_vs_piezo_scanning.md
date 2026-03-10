# 🔄 Galvo vs. Piezo Scanning

> This is one of the most important decisions you'll make in DeScribe before every print. Choosing the wrong scanning mode costs you either **time** or **resolution**. This file explains both modes in depth so you can make the right call every time.

---

## 🧠 The Core Problem: How Do You Move the Focal Point?

To build a 3D structure, the laser's focal point must trace out every voxel in your design. There are two fundamentally different ways to move that focal point:

1. **Move the laser beam** (galvo mode — fast, lower precision)
2. **Move the sample** (piezo mode — slower, higher precision)

The GT2 supports both, and you can use each independently or — in some setups — combine them.

---

## ⚡ Galvo Scan Mode

### How It Works

**Galvo scanning** uses a pair of small, motorized mirrors (**galvanometer mirrors**) in the beam path to steer the laser beam rapidly in X and Y. The beam deflects without moving any mechanical stage — it's pure optics, which is why it's so fast.

```
Laser beam ──► [Galvo Mirror X] ──► [Galvo Mirror Y] ──► Objective ──► Focal Point
                    ↕ (rotates)            ↕ (rotates)
                 Beam deflects           Beam deflects
                 in X direction          in Y direction
```

### Key Specifications

| Parameter | Galvo Mode |
|---|---|
| **Scan field size** | 400 × 400 µm |
| **Typical scan speed** | Up to 100,000 µm/s (100 mm/s) |
| **Z movement** | Piezo stage (Z still uses piezo) |
| **Positional accuracy** | ~1–2 µm within field |
| **Best for** | Large structures, fast prints, scaffold/shell printing |

### Galvo Mode Strengths

- ✅ **Up to 100× faster** than piezo mode for equivalent print volume
- ✅ No mechanical vibration during XY scan — only Z (piezo) moves mechanically
- ✅ Ideal for printing with **IP-Q**, **IP-S**, **IPX-Clear** where print speed matters
- ✅ Handles large print fields that exceed the piezo's 300 µm XY range

### Galvo Mode Limitations

- ❌ **Lower positional accuracy** (~1–2 µm vs. ~10 nm for piezo)
- ❌ Slight field distortion at the edges of the 400 × 400 µm scan field
- ❌ Not appropriate for structures requiring sub-micron XY precision
- ❌ Cannot use tilt correction (tilt correction requires piezo XY movement)

> 🧠 **When to choose galvo:** Your structure is large (> ~100 µm in XY), print time is a concern, and you don't need sub-micron feature placement accuracy. Almost all **scaffold and shell printing** workflows use galvo mode.

---

## 🎯 Piezo Scan Mode

### How It Works

**Piezo scanning** keeps the laser beam fixed and moves the **entire sample** using the piezo stage (described in [microscope_module.md](./microscope_module.md)). The sample shifts in X, Y, and Z so that each new voxel position comes under the fixed focal point.

```
Laser beam ──► Objective ──► Fixed Focal Point
                                    ↑
                               [Sample moves]
                            ← X ─ Y ─ Z →
                         (piezo stage moves the sample)
```

### Key Specifications

| Parameter | Piezo Mode |
|---|---|
| **Scan range** | 300 × 300 × 300 µm |
| **Typical scan speed** | 10–10,000 µm/s |
| **Positional accuracy** | ~10 nm |
| **Best for** | High-precision structures, sub-micron features, nanostructures |

### Piezo Mode Strengths

- ✅ **~10 nm positional accuracy** — the highest precision available on the GT2
- ✅ No optical distortion (the beam path doesn't change — only sample position changes)
- ✅ Essential for **sub-200 nm feature sizes** with the 63× objective
- ✅ Supports **tilt correction** for non-flat substrates
- ✅ Best for **IP-Dip2** and applications requiring highest fidelity

### Piezo Mode Limitations

- ❌ **Limited to 300 µm** in X, Y, and Z — structures larger than this require stitching
- ❌ Significantly slower than galvo mode for equivalent volumes
- ❌ Mechanical stage movement can introduce vibration at high speeds

> 🧠 **When to choose piezo:** You're printing small, precision structures (< 300 µm in all dimensions), using the 63× objective, working with IP-Dip2, or needing tilt correction. Any time feature quality matters more than print speed.

---

## 📊 Direct Comparison Table

| Feature | Galvo Mode | Piezo Mode |
|---|---|---|
| **How beam/sample moves** | Beam moves (mirrors) | Sample moves (piezo) |
| **Max scan area (XY)** | 400 × 400 µm | 300 × 300 µm |
| **Max Z range** | ~8 mm (full stage) | 300 µm |
| **Speed** | Up to 100 mm/s | Up to ~10 mm/s |
| **Positional accuracy** | ~1–2 µm | ~10 nm |
| **Tilt correction** | ❌ No | ✅ Yes |
| **Field distortion** | Slight at edges | None |
| **Best objective pairing** | 25×, 10× | 63×, 25× |
| **Typical use case** | Fast large prints | High-precision nanostructures |

---

## 🔀 Combining Galvo + Piezo (Hybrid Mode)

In some configurations, the GT2 can use **galvo for XY** scanning and **piezo for Z** movement simultaneously. This is the most common approach for medium-to-large structures printed with the 25× objective:

- Galvo scans each layer rapidly in XY
- Piezo steps the Z position between layers

This hybrid gives you most of the speed of galvo while still using the piezo's smooth Z motion for accurate layer stepping.

---

## 🧮 Practical Decision Guide

```
START HERE
    │
    ▼
Is your structure larger than 300 µm in X, Y, or Z?
    │
   YES ──────────────────────► Use GALVO MODE
    │
   NO
    │
    ▼
Do you need < 1 µm feature placement accuracy?
    │
   YES ──────────────────────► Use PIEZO MODE
    │
   NO
    │
    ▼
Is print speed a priority?
    │
   YES ──────────────────────► Use GALVO MODE
    │
   NO ───────────────────────► Use PIEZO MODE (safer default)
```

---

## ⚠️ Common Mistakes

| Mistake | Consequence | Fix |
|---|---|---|
| Using galvo mode for a 50 µm precision scaffold | ~2 µm positional error — acceptable for most work, but not nanoscale precision | Switch to piezo |
| Using piezo mode for a 500 µm × 500 µm structure | Job will fail — exceeds 300 µm range | Switch to galvo or stitch |
| Not checking scan mode setting in DeScribe | Wrong mode baked into GWL file | Always check the mode in DeScribe before generating GWL |

---

## 🔗 Related Files

- [microscope_module.md](./microscope_module.md) — Piezo stage details
- [09_Printing_Modes/galvo_scan_mode.md](../09_Printing_Modes/galvo_scan_mode.md)
- [09_Printing_Modes/piezo_scan_mode.md](../09_Printing_Modes/piezo_scan_mode.md)
- [13_Key_Parameters_Reference/scanning_speed_table.md](../13_Key_Parameters_Reference/scanning_speed_table.md)
- [06_Software_Workflow/DeScribe_Software/slicing_parameters.md](../06_Software_Workflow/DeScribe_Software/slicing_parameters.md)