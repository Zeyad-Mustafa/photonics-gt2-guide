# ✅ 63× Objective — When to Use It

---

## Use the 63× When...

### ✅ You need features smaller than 1 µm
The 63× is the only GT2 objective that reliably produces sub-micron features. Anything requiring walls < 1 µm, gaps < 1 µm, or precision better than 500 nm belongs on the 63×.

### ✅ Surface smoothness is critical
The small voxel size (~160 nm) produces surfaces with Ra < 10 nm — necessary for optical waveguides, resonators, and any device where surface scattering matters.

### ✅ You are making photonic devices
Photonic crystals, diffraction gratings, plasmonics templates, optical resonators — all require the sub-wavelength precision only the 63× can deliver.

### ✅ Your structure is small (< 0.1 mm³)
The 63× is slow. For structures that fit in 0.1 mm³, print time is manageable (minutes to a few hours). Beyond that, consider using the 25×.

### ✅ You are using IP-Dip2 resist
IP-Dip2 is specifically formulated for the 63× objective and achieves its best resolution and surface quality only with this objective.

---

## Do NOT Use the 63× When...

### ❌ Your structure is larger than 0.1–0.2 mm³
Print time will be days or weeks. Use the 25× or 10× instead.

### ❌ Feature sizes are > 5 µm throughout
You are wasting the 63×'s precision — use 25× which is much faster at this scale.

### ❌ You need IP-S, IP-Visio, or IP-PDMS
These resists are not compatible with the 63×.

### ❌ You need structures taller than 360 µm
The 63× working distance limits you to 360 µm height maximum.

---

## Quick Decision

```
Feature size < 1 µm?            → ✅ 63× required
Surface roughness critical?     → ✅ 63× recommended
Structure < 0.1 mm³?           → ✅ 63× practical
Using IP-Dip2?                  → ✅ 63× only

Any feature > 5 µm throughout? → Consider 25× instead
Volume > 0.2 mm³?              → Consider 25× or 10×
```

---

> 🔗 Next: [oil_immersion_mode.md](oil_immersion_mode.md)