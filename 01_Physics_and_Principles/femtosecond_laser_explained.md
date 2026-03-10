# ⚡ The Femtosecond Laser — Explained

> The GT2's laser is not a simple pointer or a cutting laser. It is one of the most precisely engineered light sources in existence. This page explains what makes it unique and why every one of its properties matters.

---

## The GT2 Laser at a Glance

| Property | Value |
|---|---|
| Type | Mode-locked fiber laser |
| Wavelength | 780 nm (near-infrared) |
| Pulse duration | 100 femtoseconds |
| Repetition rate | 80 MHz (80 million pulses/second) |
| Average output power | Up to ~150 mW |
| Peak power per pulse | ~6,000–10,000 W |
| Beam quality | Near-diffraction-limited (M² ≈ 1) |

---

## What Is a Femtosecond?

A femtosecond (fs) is **10⁻¹⁵ seconds** — one quadrillionth of a second.

To put it in perspective:

```
1 femtosecond is to 1 second
    as
1 second is to 31.7 million years
```

Light itself travels only **0.3 micrometers** (300 nm) in 1 femtosecond — less than the width of a single voxel.

The GT2's laser pulses are **100 femtoseconds** long. During that time, the laser delivers an enormous burst of photons to the focal point, then switches off completely until the next pulse.

---

## Mode-Locked Fiber Laser — What Does That Mean?

**Fiber laser:** The laser light is generated and guided inside a thin optical fiber (similar to fiber optic cables used in internet connections). This makes the system compact, stable, and low-maintenance compared to older Ti:Sapphire crystal lasers.

**Mode-locked:** A technique that forces all the laser's frequency modes to oscillate in phase with each other. When all modes are synchronized, they constructively interfere to produce extremely short, extremely intense pulses separated by periods of near-zero intensity.

```
Mode-locked laser output:

Power │   █   █   █   █   █   █   █
      │   │   │   │   │   │   │
      └───┴───┴───┴───┴───┴───┴───── Time
         ←12.5 ns→
      (1/80 MHz = 12.5 nanoseconds between pulses)
```

Between pulses: essentially no light
During pulse: enormous intensity for 100 femtoseconds

---

## Why 780 nm Wavelength?

The 780 nm wavelength is chosen for several reasons:

**1. Transparency to IP-series resins**
The resin is designed to be **transparent at 780 nm** — meaning the laser passes through undisturbed until two photons simultaneously hit a photoinitiator. This allows printing deep into the resin volume.

**2. Achieves two-photon threshold**
Two 780 nm photons together have the same energy as one 390 nm UV photon — exactly the energy needed to activate the photoinitiator in Nanoscribe's IP-series resins.

**3. Tight focusing**
780 nm is short enough to focus to a very small spot using high-NA objectives, enabling sub-micron voxel sizes.

**4. Eye safety relative to UV**
NIR is still a Class IV laser hazard and requires full safety precautions. However, it does not cause the same photochemical damage to the cornea and lens that UV lasers do.

---

## Why 80 MHz Repetition Rate?

The laser fires **80 million pulses per second**. This is not arbitrary:

- At typical scan speeds (10,000–100,000 µm/s), the focal point moves only **0.1–1.25 nm** between consecutive pulses
- This means consecutive pulses overlap nearly perfectly → the voxel is exposed uniformly
- The high repetition rate makes the exposure appear smooth and continuous even though it is actually pulsed

At lower repetition rates, individual pulses would be spaced further apart and you would get discrete exposure spots instead of a smooth voxel.

---

## Peak Power vs Average Power

This distinction is critical for understanding why 2PP works without damaging samples:

```
Average power (what a power meter reads): ~50 mW
                                                    ↓
This is the SAFE level that doesn't heat the sample

But during each 100 fs pulse:

Peak power = Average power / (pulse duration × repetition rate)
           = 0.050 W / (100×10⁻¹⁵ s × 80×10⁶ Hz)
           = 0.050 / (8×10⁻⁶)
           ≈ 6,250 Watts during each pulse
```

**6,250 W for 100 femtoseconds** — then nothing for 12.5 nanoseconds. The sample never accumulates enough heat to be damaged, but the instantaneous intensity is high enough to trigger two-photon events.

---

## The Warm-Up Requirement

⚠️ **The GT2 laser requires a 45-minute warm-up period before use.**

Why? Mode-locked fiber lasers are sensitive to temperature. The laser cavity length must stabilize thermally for the pulse duration and repetition rate to be consistent. If you start printing before warm-up:
- Pulse duration may be longer than 100 fs → lower peak power → inconsistent polymerization
- Output power may drift during printing → varying voxel size → print failure

**Never skip the warm-up.** It is built into the startup procedure in NanoWrite automatically.

---

## Laser Power Control in the GT2

In DeScribe and NanoWrite, laser power is set as a **percentage (0–100%)**.

This percentage scales the average output power of the laser. Typical working ranges:

| Objective | Typical Power Range |
|---|---|
| 63× + IP-Dip2 | 15–35% |
| 25× + IP-S | 20–50% |
| 10× + IP-Q | 30–70% |

These are starting points only — every lab's system will be slightly different due to optical losses, alignment, and resin lot variations. Always do a power calibration print when starting a new project.

---

## What Happens If Power Is Wrong?

```
Too LOW power:
→ Fewer two-photon events
→ Below polymerization threshold
→ Voxels don't form → missing features → print failure

Too HIGH power:
→ Two-photon zone extends beyond focal volume
→ Voxel grows larger than intended
→ Features merge together → loss of resolution → blooming
→ Thermal damage possible at extreme levels
```

---

## Summary

| Property | Value | Why It Matters |
|---|---|---|
| 780 nm wavelength | NIR, invisible | Transparent to resin until 2-photon threshold |
| 100 fs pulse duration | 100 femtoseconds | Creates extreme peak intensity |
| 80 MHz repetition | 80M pulses/second | Smooth, uniform voxel exposure |
| ~50 mW average power | Low average | No sample heating |
| ~6,250 W peak power | Extremely high instantaneous | Triggers two-photon absorption |
| 45-min warm-up | Thermal stabilization | Consistent pulse duration and power |

---

> 🔗 **Next:** [Voxel Formation →](voxel_formation.md)