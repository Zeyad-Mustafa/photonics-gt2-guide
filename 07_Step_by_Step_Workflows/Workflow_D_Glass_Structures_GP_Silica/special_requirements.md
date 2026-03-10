# Special Requirements — Workflow D (GP-Silica)

> This file details the constraints that make GP-Silica printing different from every other GT2 workflow. These are not optional considerations — they are hard requirements.

---

## Requirement 1: The 8-Hour Time Limit

Once GP-Silica resist is exposed to the 780 nm laser environment and loaded into the machine, you have **8 hours** to complete the print and remove the sample.

This limit exists because the photoinitiator in the GP-Silica binder degrades over time when exposed to ambient light and temperature. After 8 hours, the remaining sensitivity is insufficient to produce fully cross-linked structures.

Managing the time limit:

| Action | Time Impact |
|---|---|
| Apply resist and load holder | Clock starts |
| Laser warm-up (if not already done) | Use the warm-up time as part of your 8-hour window — warm up the laser BEFORE applying resist |
| Large print jobs | Calculate estimated print time in DeScribe before applying resist. If the print will take > 6 hours, do not start. |
| Multiple print fields (stitched) | Each field adds to total time — plan carefully |

Plan your session so that resist application, sample loading, interface detection, and print completion all fit within 6 hours (leaving 2 hours of margin).

See [11_Troubleshooting/gp_silica_print_timeout.md](../../11_Troubleshooting/gp_silica_print_timeout.md) for what happens if you approach or exceed the limit.

---

## Requirement 2: Furnace Capable of 1500 degrees C

The sintering step requires a tube furnace with:
- Maximum temperature of at least 1500 degrees C
- Controlled atmosphere (typically air or inert gas, depending on your application)
- Programmable ramp rates (the sintering profile requires specific ramp and hold times)
- Ceramic or platinum crucible and support tube compatible with 1500 degrees C

This is specialized equipment not available in all labs. Confirm access before attempting this workflow. Common locations: materials science departments, glass fabrication facilities, MEMS fabrication labs.

---

## Requirement 3: Design for Sintering — Shrinkage and Cracking

GP-Silica shrinks **25–30% linearly** in all dimensions during sintering. This means:
- A 100 um printed structure becomes approximately 70–75 um after sintering
- A 1 mm printed structure becomes approximately 700–750 um after sintering
- Scale your design by **1.33–1.43x** in DeScribe to compensate (a 1.35 scale factor is a good starting point)

In addition, certain geometries are prone to cracking:

| Design Feature | Risk | Mitigation |
|---|---|---|
| Solid thick blocks (> 100 um wall) | High cracking risk — differential shrinkage | Use hollow shell designs |
| Abrupt thickness changes | Stress concentration at transition | Taper transitions gradually |
| Large flat areas (> 500 um unsupported) | Warping and cracking | Add ribs or support structures |
| Overhangs | May collapse during sintering if polymer support burns away before silica is rigid | Use self-supporting geometries |
| Uniform-thickness shells and lattices | Low risk | Preferred design approach |

---

## Requirement 4: Substrate Compatibility

GP-Silica prints must be on substrates that can survive the sintering temperature. Standard glass substrates (borosilicate, ITO-coated glass) cannot — they melt or deform at 1500 degrees C.

Compatible substrates for GP-Silica:
- Fused silica (quartz) wafers or slides — survive 1500 degrees C
- Platinum foil — inert at high temperature
- Alumina (Al2O3) — ceramic substrate, thermally stable

The printed composite structure may be removed from the substrate after debinding (when the binder has burned away but before full sintering) if a freestanding glass part is required.

---

## Related Files

- [print_steps.md](./print_steps.md)
- [post_processing.md](./post_processing.md)
- [04_Resists_and_Materials/GP_Silica/overview.md](../../04_Resists_and_Materials/GP_Silica/overview.md)
