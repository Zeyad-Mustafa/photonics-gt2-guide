# 🧱 25× Objective — Compatible Substrates

---

## Primary Substrate: ITO-Coated Glass

The standard substrate for the 25× DiLL workflow is **ITO (Indium Tin Oxide) coated borosilicate glass**.

| Property | Value |
|---|---|
| Size | 25×25 mm |
| Thickness | ~0.7–1.1 mm |
| ITO coating | ~100–200 nm on one side |
| Refractive index (glass) | n ≈ 1.52 |
| Refractive index (IP-S resin) | n = 1.478 |
| Δn | ~0.04 (minimum for detection) |

### Why ITO?
The ITO layer provides a slightly higher refractive index contrast at the substrate–resin interface, making it easier for NanoWrite's interface finder to detect the boundary. ITO is also conductive, which is useful for downstream electrodeposition or SEM characterization.

### Critical Orientation
⚠️ **The ITO-coated side must face DOWN toward the objective.**

If you place the substrate the wrong way:
- The laser must pass through the full glass thickness before reaching the resin
- Focus quality degrades significantly
- Interface detection may fail
- Working distance effectively reduces

**How to identify the ITO side:**
- Use a multimeter — ITO side is conductive (reads resistance), bare glass side is insulating
- The ITO side may have a very slight blue/gold tint under certain lighting
- Nanoscribe substrates are often labeled on the box

---

## Secondary Substrate: Silicon Wafer Pieces

Silicon works with the 25× for applications where substrate conductivity or downstream silicon processing is required.

- Cut to 25×25 mm
- Polish side facing objective
- High Δn (silicon n ≈ 3.5 vs IP-S n ≈ 1.478) → very reliable interface detection

---

## Substrate Cleaning Procedure

1. Rinse with **acetone** — 30 seconds gentle agitation
2. Rinse with **IPA** — 30 seconds
3. Rinse with **DI water** — 30 seconds
4. Dry with **nitrogen gun** — blow from center outward
5. Optional: **O₂ plasma** 120 s, 100 W — improves adhesion significantly

⚠️ Do NOT use O₂ plasma on ITO-coated substrates if preserving ITO conductivity matters — plasma can partially oxidize ITO and change its resistance.

---

> 🔗 Next: [voxel_dimensions.md](voxel_dimensions.md)