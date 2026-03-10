# ✅ 10× Objective — When to Use It

---

## Use the 10× When...

### ✅ Your structure is larger than 1 mm³
The 10× can address volumes up to ~10 mm³ in a reasonable print time. The 25× becomes impractically slow above ~1 mm³, and the 63× above ~0.1 mm³.

### ✅ Your smallest feature is larger than 5 µm
If nothing in your design requires finer than 5 µm, the 10× will print it faster than any other objective.

### ✅ You need maximum print height
Working distance of 700 µm gives you the tallest possible structures on the GT2. The 25× maxes out at ~380 µm height; the 63× at ~360 µm.

### ✅ You are printing mechanical metamaterials or lattices
Large repeating unit cell structures (octet truss, gyroid, Kelvin foam) with cells > 20 µm are perfect candidates for the 10×.

### ✅ Speed is a priority over resolution
A structure that takes 12 hours on the 63× might take 45 minutes on the 10× — if resolution requirements allow.

### ✅ You are prototyping before a high-resolution print
Print a quick 10× version first to check dimensions, fit, and assembly before committing to a long 63× run.

---

## Do NOT Use the 10× When...

### ❌ Features smaller than 5 µm are present
The ~1.6 µm lateral voxel and ~12 µm axial voxel make sub-5 µm features unreliable. Switch to 25× or 63×.

### ❌ Smooth vertical surfaces are required
The 12 µm axial voxel creates visible stairstepping on surfaces that are not perfectly horizontal. Optical components requiring smooth sidewalls need the 25× or 63×.

### ❌ You need IP-S, IP-Dip2, IP-Visio, or IP-PDMS resists
These resists are not compatible with the 10×. Only IP-Q, IPX-Q, and IPX-Clear work with this objective.

### ❌ Your substrate is ITO-coated glass
The 10× workflow is optimized for silicon wafers. ITO glass is the substrate for the 25× DiLL workflow.

---

## Quick Decision Check

```
Is your structure > 1 mm³?           → Yes → Consider 10×
Is your smallest feature > 5 µm?     → Yes → Consider 10×
Do you need > 380 µm print height?   → Yes → 10× only option
Are you using IP-Q or IPX-Q resist?  → Yes → 10× or 25×

All yes? → Use 10×
Any no?  → Consider 25× or 63×
```

---

> 🔗 Next: [compatible_resists.md](compatible_resists.md)