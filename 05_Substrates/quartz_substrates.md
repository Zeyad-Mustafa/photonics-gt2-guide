# Quartz Substrates

---

## What Is Quartz in This Context?

In GT2 contexts, "quartz" refers to fused silica — amorphous silicon dioxide (SiO2) produced by melting and re-solidifying high-purity silica. It is not the same as crystalline quartz (alpha-quartz), which has different optical properties.

Fused silica substrates are used when:
- The substrate must be optically transparent from the UV through the near-infrared
- Low autofluorescence is required for characterization
- High chemical and thermal stability is needed
- The application involves light transmission through the substrate

---

## Optical Properties

| Property | Value |
|---|---|
| Refractive index at 780 nm | ~1.457 |
| Transmission range | 150 nm to 3500 nm |
| Autofluorescence | Very low |
| Surface roughness (polished) | Less than 1 nm Ra |
| Thermal expansion coefficient | 0.55 x 10^-6 per K (very low) |

The UV transparency of fused silica (down to 150 nm) is the key property that distinguishes it from borosilicate glass. Borosilicate glass absorbs UV below approximately 300 nm. For applications requiring UV excitation or UV characterization of the printed structure, quartz is mandatory.

---

## Delta-n Considerations With IP-Series Resins

Quartz has a lower refractive index (1.457) than both IP-Dip2 (1.511) and IP-S (1.478).

| Resin | Substrate (quartz) | Delta-n | Detection reliability |
|---|---|---|---|
| IP-Dip2 | 1.457 vs 1.511 | 0.054 | Acceptable — works reliably |
| IP-S | 1.457 vs 1.478 | 0.021 | Marginal — may require careful drop geometry |
| IP-Q | 1.457 vs 1.480 | 0.023 | Marginal |

For 63x + IP-Dip2 on quartz: delta-n of 0.054 is above the 0.04 minimum threshold, and interface detection works reliably if the resin drop is properly semi-spherical.

For 25x + IP-S on quartz: delta-n of 0.021 is below the reliable threshold. Interface detection may fail or give inconsistent results. Prefer silicon wafer pieces when using IP-S, unless quartz is specifically required for the application.

If you must use quartz with IP-S, try:
- Maximizing drop semi-sphericity (fresh resin, room temperature)
- Running the interface finder multiple times
- Manually assisting by observing the camera feed and adjusting Z position

---

## Standard Substrate Sizes

Fused silica substrates are available in the 25x25 mm size required for GT2 holders from suppliers such as University Wafer, Precision Glass and Optics, and Mark Optics. Specify:
- Fused silica (not crystalline quartz)
- 25 x 25 mm
- 1 mm thickness (standard) or 0.5 mm if thinner substrates are needed
- Double-side polished for maximum flatness and transparency

---

## Cleaning Fused Silica

Fused silica is chemically robust and can withstand aggressive cleaning. The same protocol as silicon applies:

Step 1 — Acetone rinse, 30 to 60 seconds
Step 2 — IPA rinse, 30 seconds
Step 3 — DI water rinse, 30 seconds
Step 4 — Nitrogen blow dry

Optional step — Piranha etch
For critical optical applications requiring the lowest possible surface contamination, piranha solution (H2SO4 : H2O2 = 3:1) is highly effective. This produces an extremely clean, hydroxylated surface with excellent adhesion. This is a hazardous procedure requiring trained personnel and proper waste disposal.

Optional step — O2 plasma
60 to 120 seconds at 100 W. Produces a clean, wettable surface. Very effective for improving resin adhesion and drop geometry.

---

## Adhesion of IP Resins on Quartz

Adhesion of cured IP-series polymers on fused silica is generally good, particularly after O2 plasma treatment. The hydroxylated silica surface (-SiOH groups) can bond to the polymer network through hydrogen bonding and, in the presence of silane coupling agents, through covalent bonds.

For structures with very small contact area (isolated pillars, thin walls with small footprint):
- Always use O2 plasma before printing
- Consider MEMO silane functionalization for critical structures
- Design wider anchor pads at the base of pillars if possible — the extra footprint significantly improves adhesion

---

## Applications That Require Quartz

- Micro-optical elements (lenses, beam shapers) that will transmit UV light
- Photonic devices characterized by UV-visible transmission spectroscopy
- Waveguides for UV wavelengths
- Any application where the substrate itself must be imaged by fluorescence microscopy without autofluorescence from the glass
- High-temperature applications — fused silica retains dimensional stability up to approximately 1000 degrees C without deforming

---

Proceed to: custom_substrates.md
