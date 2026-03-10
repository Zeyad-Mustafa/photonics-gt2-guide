# IP-PDMS — Overview

> IP-PDMS is the only resist in the standard GT2 lineup that produces soft, flexible, elastic 3D structures. If you need a printed part that bends, stretches, or deforms without breaking, IP-PDMS is the material.

---

## What Is IP-PDMS?

**IP-PDMS** is a photopolymer resin based on **polydimethylsiloxane (PDMS)** chemistry, adapted for two-photon polymerization. PDMS is widely used in microfluidics (as Sylgard 184) and is known for its:

- High elasticity (can be stretched to several times its original length)
- Chemical inertness
- Optical transparency
- Biocompatibility (the PDMS bulk material is biocompatible)
- Low surface energy (hydrophobic — liquids bead up on the surface)

IP-PDMS brings these bulk PDMS properties into the 2PP printing process, enabling **3D elastic microstructures** that would be impossible to mold or cast at this scale.

---

## Key Specifications

| Parameter | Value |
|---|---|
| Refractive index (n) | ~1.41 |
| Recommended objective | 25x (NA 0.8) |
| Printing mode | DiLL |
| Elastic modulus | ~1-10 MPa (very soft — 100-1000x lower than IP-S) |
| Elongation at break | Up to several hundred percent |
| Developer | Specific PDMS-compatible solvent — see below |
| Appearance | Clear, higher-viscosity liquid |
| Viscosity | High (more viscous than IP-S or IP-Q) |

---

## When to Use IP-PDMS

Use IP-PDMS when:

- The final structure must be flexible, elastic, or compressible
- You are making microfluidic components that must deform under pressure (valves, pumps)
- You are making soft robotic microactuators or gripper structures
- You need PDMS-like surface properties (hydrophobic, low friction, cell-compatible)

Do NOT use IP-PDMS when:

- Dimensional accuracy is critical (PDMS is soft and deforms under its own weight at microscale)
- Feature sizes below ~2 um are needed (IP-PDMS resolution is limited)
- You need a rigid, structural part

---

## Development: PDMS-Specific Considerations

IP-PDMS requires a different development approach than other IP-series resists. Because PDMS networks swell in many common solvents:

- **Avoid long development times in PGMEA** — PDMS structures can swell and distort
- Consult the current Nanoscribe application note for IP-PDMS development (protocols are updated as the material matures)
- Isopropanol is typically used as the rinse but may cause some swelling in very fine features
- Allow structures to dry fully (and de-swell) before imaging or use

---

## Related Files

- [applications.md](./applications.md)
- [handling_and_storage.md](./handling_and_storage.md)
- [10_Applications/soft_structures.md](../../10_Applications/soft_structures.md)