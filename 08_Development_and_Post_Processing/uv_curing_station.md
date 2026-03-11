# UV Curing Station

## Purpose

UV post-curing is performed after development and drying. Its purpose is to complete the polymerization reaction in the cured structure. During 2PP printing, the laser delivers enough energy to form a solid crosslinked network — enough to maintain structure shape and survive development — but not enough to react every available monomer and crosslinking site within the polymer volume. Unreacted monomers and partially reacted chains remain trapped inside the network after printing.

UV post-curing activates any remaining photoinitiator in the structure and drives these residual reactions to completion. The result is:

- Increased mechanical hardness and stiffness (typically 20 to 50 percent improvement)
- Improved chemical resistance to solvents and humidity
- Reduced risk of slow continued polymerization over time, which would otherwise cause gradual dimensional drift
- Better optical clarity in transparent resins such as IPX-Clear and IP-Visio

---

## The UV Curing Station

The GT2 lab UV curing station uses a 405 nm near-UV LED or lamp source. The 405 nm wavelength was chosen to match the absorption spectrum of the photoinitiators used in Nanoscribe IP-series resins. It is also the wavelength at which these photoinitiators absorb most efficiently under single-photon conditions.

Typical station specifications:

| Parameter | Value |
|---|---|
| Wavelength | 405 nm |
| Irradiance | approximately 1.2 to 2.0 W per cm squared |
| Chamber size | accommodates standard 25x25 mm substrates |
| Timer | adjustable, auto shutoff |
| Observation window | yellow-filtered glass or acrylic |

---

## Operating the UV Curing Station

Step 1 — Confirm the station is off before opening
Check the power indicator. If the lamp is on, do not open the lid. Wait for the current cycle to complete or turn the station off and wait 30 seconds for the lamp to cool.

Step 2 — Place the substrate in the chamber
Open the lid and place the substrate with the printed structure facing up, toward the lamp. Center it in the chamber for uniform exposure. For very small structures, position them directly under the lamp center.

Step 3 — Close the lid completely
The lid must be fully closed before starting. A partially closed lid allows 405 nm light to escape from the chamber. While 405 nm is not as hazardous as UV-C or UV-B, direct exposure to the output of a high-irradiance 405 nm source is uncomfortable and potentially harmful to eyes over extended periods.

Step 4 — Set the timer
Set the timer according to the recommended curing time for your resin and structure size (see table below). The station shuts off automatically when the timer expires.

Step 5 — Start the cure
Press the start button. The lamp activates immediately. You may observe fluorescence from the structure through the yellow observation window — the cured polymer fluoresces slightly at 405 nm excitation. This fluorescence fades as the curing progresses and unreacted photoinitiator is consumed.

Step 6 — Wait for completion
Do not open the lid during curing. When the timer expires and the station shuts off, wait 10 to 15 seconds before opening to allow any residual lamp heat to dissipate.

Step 7 — Remove the substrate
Open the lid and remove the substrate with clean tweezers. The substrate may be slightly warm to the touch — this is normal.

---

## Curing Times by Resin and Structure Size

| Resin | Structure height up to 100 um | Structure height 100 to 300 um | Structure height above 300 um |
|---|---|---|---|
| IP-Dip2 | 5 to 10 minutes | 10 to 15 minutes | 15 to 20 minutes |
| IP-S | 5 to 10 minutes | 10 to 15 minutes | 15 to 20 minutes |
| IP-Q | 5 to 10 minutes | 10 to 20 minutes | 20 minutes |
| IP-Visio | 5 to 10 minutes | 10 to 15 minutes | 15 to 20 minutes |
| IP-PDMS | 10 to 15 minutes | 15 to 20 minutes | 20 minutes |
| IPX-Clear | 5 to 10 minutes | 10 to 15 minutes | 15 to 20 minutes |

Hard maximum: do not run any single curing cycle for more than 40 minutes. Extended operation generates heat inside the chamber that can thermally distort structures or damage the lamp. If longer total curing is needed (for very large structures), run two separate cycles with a 5-minute cooling interval between them.

---

## Why 405 nm and Not Broadband UV

Broadband UV lamps (such as mercury arc lamps used in photolithography aligners) are not recommended for post-curing IP-series resins. Their output includes UV-C and UV-B wavelengths that can cause photodegradation of the cured polymer, yellowing of transparent resins, and excessive heating at the sample surface.

The 405 nm LED source is spectrally narrow and matches the photoinitiator absorption without driving degradation reactions. The result is a harder, clearer structure without yellowing.

---

## Observing Through the Yellow Window

The yellow filter in the observation window absorbs 405 nm light and allows longer visible wavelengths to pass through. This allows you to see the substrate during curing without exposing your eyes to the direct lamp output.

Do not remove the yellow filter panel or tape over it. Do not attempt to open the lid during a curing cycle.

If no yellow observation window is present on your specific curing station model, do not look into the chamber while the lamp is running. Wait for the cycle to complete before opening.

---

## Effect of UV Curing on Mechanical Properties

The following changes are typical after UV post-curing compared to a printed-and-developed but uncured structure:

| Property | Before UV cure | After UV cure | Change |
|---|---|---|---|
| Vickers hardness | Baseline | 20 to 50 percent higher | Significant improvement |
| Young's modulus | Baseline | 10 to 30 percent higher | Moderate improvement |
| Chemical resistance | Moderate | Good | Improved |
| Dimensional stability | Moderate (may drift over days) | Good | Significantly improved |
| Surface tackiness | Sometimes present | Eliminated | |

The improvement in dimensional stability is particularly important for optical elements and precision mechanical devices where tolerance drift of even a few hundred nanometers over days would degrade performance.

---

## UV Curing of GP-Silica Structures

GP-Silica green bodies should not be UV cured before debinding and sintering. The green body binder will be burned out in the furnace. UV curing the binder before furnace processing does not improve the final glass structure and may harden the binder in a way that makes debinding less uniform.

---

Proceed to: oxygen_plasma_treatment.md
