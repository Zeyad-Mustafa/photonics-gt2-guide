# IP-S — Properties

---

## Optical Properties

| Property | Value |
|---|---|
| Refractive index (n) at 780 nm | 1.478 |
| Transmission (cured, visible light) | >90% |
| Fluorescence background | Moderate |
| Absorption at 780 nm | Very low |

---

## Physical Properties (Liquid State)

| Property | Value |
|---|---|
| Appearance | Clear, colorless liquid |
| Viscosity | ~300-500 mPa·s |
| Density | ~1.15 g/cm3 |
| Miscibility | Miscible with PGMEA, IPA |

The medium viscosity of IP-S means it wets the substrate well and forms a stable drop shape. It does not flow as readily as IP-Dip2, which helps maintain a consistent drop geometry on the substrate surface before the objective approaches.

---

## Print Process Properties

| Property | Value | Notes |
|---|---|---|
| Polymerization threshold (typical) | ~15-30% laser power (25x, galvo, typical speeds) | Calibrate per machine |
| Scan speed range | 10-100,000 um/s | Broad usable range |
| Minimum lateral voxel | ~500 nm | In piezo mode at threshold power |
| Typical practical feature size | ~1-2 um | In galvo mode at normal print speeds |
| Slice distance (typical) | 0.5-1.0 um | Adjust based on structure height and required Z resolution |
| Hatch distance (typical) | 0.3-0.7 um | |

---

## Mechanical Properties (Cured State)

| Property | Value |
|---|---|
| Young's modulus | ~1-2 GPa |
| Hardness | High |
| Shrinkage (linear) | ~2-4% |
| Thermal stability | Up to ~150 C |
| Surface roughness (Ra) | < 20 nm (smooth surfaces are a key strength) |

IP-S produces the smoothest surfaces of all the standard IP-series resists. This makes it the preferred choice for micro-optical components where surface quality affects performance (e.g., microlens arrays, prisms, diffractive optical elements).

---

## Developer Compatibility

| Solvent | Role |
|---|---|
| PGMEA | Primary developer (20-30 min) |
| IPA | Rinse (5-10 min) |

Development note: IP-S is somewhat slower to develop than IP-Dip2. Solid scaffold-type structures or dense geometries may require the full 30 minutes in PGMEA to fully remove unexposed resist from internal cavities.

---

## Related Files

- [overview.md](./overview.md)
- [use_with_25x.md](./use_with_25x.md)
- [handling_and_storage.md](./handling_and_storage.md)