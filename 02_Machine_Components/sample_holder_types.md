# 🧲 Sample Holder Types

> The sample holder is the interface between your substrate and the GT2's stage. Choosing the wrong holder — or loading it incorrectly — is one of the most common causes of failed prints. This file covers all three holder types, their uses, and the critical orientation rules.

---

## 🧠 Why Does the Holder Matter?

The sample holder does three things:

1. **Physically supports** the substrate above the objective
2. **Sets the correct working distance** between the objective tip and the substrate
3. **Determines which printing modes are accessible** (DiLL, oil immersion, air)

The GT2 has a **quick-exchange system** — you swap holders without tools, but you must use the correct holder for your objective/substrate combination. Using the wrong holder can cause the objective to crash into the substrate.

---

## 📦 Holder Type 1: Universal Sample Holder

### What It Is

The **Universal Sample Holder** is the most commonly used holder. It accepts a wide range of substrate sizes and is compatible with the 25× and 63× objectives in DiLL and oil immersion modes.

### Compatible With

| Objective | Mode | Resist |
|---|---|---|
| 25× | DiLL | IP-S, IP-Visio, IP-PDMS, IPX-Clear |
| 63× | Oil immersion (through-glass) | IP-Dip2, IP-Dip, IPX-Clear |

### Accepted Substrate Sizes

- Standard microscope slides (25 × 75 mm)
- ITO-coated glass slides (25 × 75 mm or custom)
- Diced silicon pieces (≥ ~5 × 5 mm, up to ~25 × 25 mm)
- Custom substrates that fit the recess

### ⚠️ Critical Orientation Rule: ITO Side Faces Down

When using ITO-coated glass with the 25× objective in DiLL mode:

```
CORRECT:
┌────────────────────────────────────────────┐
│        ITO coating (conductive side)        │  ← Faces DOWN toward objective
│════════════════════════════════════════════│
│        Glass substrate                      │  ← Faces UP (away from objective)
└────────────────────────────────────────────┘
                    ↑
              Objective (below)
              dips into resist
              on ITO surface
```

> ❌ **If you load the substrate ITO-side up, the laser must travel through the full glass thickness before reaching the resin. This shifts the focal plane, prevents proper interface detection, and will ruin your print.**

### Loading Instructions (Summary)

1. Place the substrate in the holder recess with the **functional side (ITO or polished surface) facing down**
2. Secure it with the clip or retaining ring (do not overtighten — glass will crack)
3. Place the resist drop on the substrate surface that is now facing up (which will face the objective when inverted)
4. Carefully invert and insert into the stage

> 🧠 This seems counterintuitive at first. Remember: the GT2 is an **inverted** microscope. "Down" toward the objective is the printing side.

---

## 📦 Holder Type 2: Multi-DiLL Silicon Wafer Holder

### What It Is

The **Multi-DiLL Silicon Wafer Holder** (sometimes called the "10× holder") is designed specifically for use with the **10× objective** and large silicon substrates. It holds a standard 4-inch (100 mm) or diced silicon wafer piece and provides the correct geometry for the 10× objective's longer working distance (700 µm).

### Compatible With

| Objective | Mode | Resist |
|---|---|---|
| 10× | DiLL | IP-Q, IPX-Q, IPX-Clear |

### Key Differences from the Universal Holder

| Feature | Universal Holder | Multi-DiLL Si Holder |
|---|---|---|
| Target objective | 25×, 63× | **10× only** |
| Substrate size | Slides, small chips | 4" wafer or diced pieces |
| Working distance clearance | Shorter WD (25×: 380 µm, 63×: 360 µm) | Longer WD (10×: 700 µm) |
| Resist volume needed | 1–5 µL typical | 1–2 drops IP-Q only |

### ⚠️ Important: Do NOT Use Other Objectives with This Holder

The Multi-DiLL holder is recessed differently from the Universal holder. If you insert a 25× or 63× objective with this holder loaded, the **objective tip will crash into the substrate** before reaching its working distance.

> ⚠️ **Rule:** Multi-DiLL holder = 10× objective **only**. No exceptions.

### Resist Application for the 10× + Multi-DiLL

The 10× objective uses **IP-Q** resist. Unlike the 25× DiLL where more resist is okay, with IP-Q you must apply **only 1–2 small drops** to the substrate surface.

- Too much resist creates a flat, wide pool → poor interface detection (the system needs a semi-spherical drop shape for the refractive index step to be sharp)
- The drop should be slightly domed (semi-spherical), not spread flat

See **[04_Resists_and_Materials/IP_Q/drop_casting_technique.md](../04_Resists_and_Materials/IP_Q/drop_casting_technique.md)** for the correct technique.

---

## 📦 Holder Type 3: 5-Inch Mask Holder

### What It Is

The **5-inch Mask Holder** is a large-format holder designed for **photomasks** and large flat substrates up to 5 inches (127 mm) in diameter or equivalent square size. It is used for advanced patterning workflows, not standard 3D printing.

### Compatible With

| Objective | Mode | Use Case |
|---|---|---|
| 20× (air) | Air mode | 2D patterning on spin-coated i-line resists |
| 25× | Selected workflows | Large-area stitched prints |

### When You'll Use This Holder

The 5" mask holder is primarily relevant if:
- You are doing **2D lithography** on spin-coated wafers using the 20× air objective
- You are working with **4-inch wafer-scale substrates** that don't fit the Universal holder
- Your facility uses standard photomask blanks as substrates

Most beginner and intermediate workflows **will not require the 5" mask holder**. Start with the Universal or Multi-DiLL holders.

### Loading Notes

- The substrate sits face-down in the same inverted-microscope logic as the other holders
- Ensure the substrate is flat and fully seated — any tilt will cause focus errors across the print field
- This holder is heavier than the others; use two hands when inserting/removing

---

## 📊 Quick-Reference: Which Holder Do I Need?

| My Objective | My Resist | My Holder |
|---|---|---|
| 63× | IP-Dip2, IP-Dip, IPX-Clear | Universal Sample Holder |
| 25× | IP-S, IP-Visio, IP-PDMS, IPX-Clear | Universal Sample Holder |
| 10× | IP-Q, IPX-Q, IPX-Clear | **Multi-DiLL Silicon Wafer Holder** |
| 20× (air) | i-line photoresist (spin-coated) | 5-Inch Mask Holder or Universal |
| 25× (large wafer) | Various | 5-Inch Mask Holder |

---

## 🔄 Swapping Holders: The Exchange Dialog

Whenever you change from one holder to another, you **must** use the **Exchange Holder dialog** in NanoWrite. This step:

1. Raises the objective to its safe retract position
2. Unlocks the stage so you can slide the holder in or out
3. Prevents the objective from crashing during the swap

> ⚠️ **Never remove or insert a holder without going through the Exchange Holder dialog first.** Skipping this step is the #1 cause of objective crashes and is extremely expensive to repair.

See **[06_Software_Workflow/NanoWrite_Software/exchange_holder_dialog.md](../06_Software_Workflow/NanoWrite_Software/exchange_holder_dialog.md)** for the step-by-step procedure.

---

## 🔗 Related Files

- [microscope_module.md](./microscope_module.md) — Stage and objective turret
- [03_Objectives/README.md](../03_Objectives/README.md) — Objectives and their working distances
- [04_Resists_and_Materials/IP_Q/drop_casting_technique.md](../04_Resists_and_Materials/IP_Q/drop_casting_technique.md)
- [05_Substrates/ITO_coated_glass.md](../05_Substrates/ITO_coated_glass.md)
- [06_Software_Workflow/NanoWrite_Software/exchange_holder_dialog.md](../06_Software_Workflow/NanoWrite_Software/exchange_holder_dialog.md)
- [11_Troubleshooting/objective_crashing.md](../11_Troubleshooting/objective_crashing.md)