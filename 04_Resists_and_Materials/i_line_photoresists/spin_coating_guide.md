# i-line Photoresists — Spin Coating Guide

> i-line resists are applied by spin coating, not drop casting. This is a standard semiconductor fab process. This file covers the basics for researchers who may be new to spin coating.

---

## What Is Spin Coating?

Spin coating deposits a thin, uniform film of photoresist on a flat substrate by:
1. Dispensing a small volume of liquid resist onto the center of the substrate
2. Spinning the substrate at high speed (500-6000 RPM)
3. Centrifugal force spreads the resist outward and flings off the excess
4. Solvent evaporates, leaving a solid thin film of controlled thickness

The resulting film is typically **0.5-10 um thick** depending on resist viscosity and spin speed.

---

## Equipment Required

- Spin coater with programmable speed and ramp control
- Hot plate for soft bake
- Fume hood (resist solvents are flammable)
- Pipette (1-5 mL, plastic or glass)
- Resist-compatible waste container

This equipment is typically found in a cleanroom or microfabrication facility. The GT2 itself does not have a spin coater — this step is done separately, then the coated substrate is brought to the GT2.

---

## General Spin Coating Procedure

These steps apply to most positive i-line resists (AZ, Shipley, etc.). Always consult the specific resist datasheet for exact parameters.

**Step 1: Substrate preparation**
- Clean the substrate thoroughly (acetone, IPA, DI water, N2 dry)
- Optional: oxygen plasma treatment (30-60 s) for better adhesion
- Optional: HMDS (hexamethyldisilazane) vapor prime for adhesion promotion on silicon

**Step 2: Dispense**
- Place the substrate on the spin coater chuck and apply vacuum
- Dispense 1-3 mL of resist onto the center of the substrate
- Static dispense (drop before spinning) gives more uniform coverage than dynamic dispense for most resists

**Step 3: Spin**

| Phase | Speed | Ramp | Duration |
|---|---|---|---|
| Spread step | 500 RPM | 100 RPM/s | 5-10 s |
| Final spin | 1000-4000 RPM (resist-dependent) | 300 RPM/s | 30-60 s |

Higher final spin speed = thinner film.

Typical thickness at common spin speeds for AZ 1505:

| Spin Speed (RPM) | Film Thickness (nm) |
|---|---|
| 1000 | ~2000 nm (2 um) |
| 2000 | ~1400 nm |
| 3000 | ~1100 nm |
| 4000 | ~900 nm |
| 6000 | ~700 nm |

**Step 4: Soft bake (pre-bake)**
- Bake on a hot plate at 90-100 C for 60-90 seconds
- This evaporates residual solvent and hardens the film slightly
- Do not over-bake — excess baking reduces sensitivity

**Step 5: Inspect**
- Visually inspect for defects (streaks, bubbles, edge bead)
- Measure thickness with a profilometer or ellipsometer if precision is needed

---

## Bringing the Coated Substrate to the GT2

After soft bake:
1. Allow the substrate to cool to room temperature
2. Load into the appropriate sample holder (5-inch mask holder or Universal holder)
3. The resist-coated side faces down toward the 20x objective (same inverted-microscope logic as all other workflows)

> Do not expose the coated substrate to bright light between spin coating and loading. Work quickly or use yellow safe-light in the vicinity.

---

## After Exposure on the GT2: Post-Exposure Bake and Development

Some resists (particularly SU-8 and chemically amplified resists) require a **post-exposure bake (PEB)** immediately after laser exposure and before development. Check your specific resist datasheet.

Development:
- Immerse in the appropriate developer for the resist
- Agitate gently
- Rinse in DI water (for aqueous developers) or IPA
- Blow dry with N2

Positive resists: exposed areas dissolve in developer, unexposed areas remain.
Negative resists (e.g., SU-8): exposed areas remain, unexposed areas dissolve.

---

## Related Files

- [overview.md](./overview.md)
- [03_Objectives/20x_objective/overview.md](../../03_Objectives/20x_objective/overview.md)
- [09_Printing_Modes/air_mode.md](../../09_Printing_Modes/air_mode.md)
- [05_Substrates/README.md](../../05_Substrates/README.md)