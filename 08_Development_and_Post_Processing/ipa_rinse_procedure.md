# IPA Rinse Procedure

## Why IPA Rinse Is a Separate Step

After PGMEA development, the substrate and the structure surface are coated with a thin layer of PGMEA. If this PGMEA is allowed to evaporate directly without a rinse step, it leaves behind dissolved monomer residue that deposits on the structure surface as the solvent evaporates. This residue degrades optical clarity, changes surface chemistry, and can act as a contaminant in downstream processes.

IPA solves this problem because it is fully miscible with PGMEA, rapidly displaces it from the structure surface, and evaporates cleanly without leaving residue. IPA also has lower surface tension than PGMEA, which reduces the capillary forces that can collapse thin features during the transition from wet to dry.

---

## Standard IPA Rinse Procedure

Step 1 — Prepare the IPA bath
Pour fresh IPA into a clean beaker or container large enough to fully submerge the substrate. The container must be clean — any residual contamination in the container transfers to the substrate during rinsing.

Step 2 — Transfer the substrate from PGMEA to IPA
Pick up the substrate with clean tweezers, holding at the edges. Do not shake off excess PGMEA before transferring — let the substrate drip briefly over the PGMEA container, then move it directly into the IPA without pause. Allowing PGMEA to begin evaporating before the IPA rinse can deposit residue.

Step 3 — Submerge and hold
Fully submerge the substrate in IPA. Gently rock the container by hand for 30 seconds to ensure IPA contacts all surfaces. Then allow to soak undisturbed for the remaining rinse time (see development_times_table.md for rinse times by resin).

Step 4 — Remove and inspect
Remove the substrate from IPA using tweezers at the edges. Hold it at an angle and allow most of the IPA to run off. Do not shake.

Step 5 — Nitrogen dry
Using a clean nitrogen gun, dry the substrate from the center outward using gentle, low-pressure nitrogen flow. Hold the nozzle at a low angle. Do not blast the nitrogen directly onto thin features at high pressure — the gas flow can mechanically knock over sub-micron structures.

---

## Special Considerations for Fragile Structures

For structures with features thinner than 2 um, the IPA-to-air transition during drying is the highest-risk point in the entire post-processing sequence. As IPA evaporates from a narrow gap between two features, the liquid meniscus pulls the features toward each other with a force that scales inversely with gap width. For sub-micron gaps, this capillary force can exceed the elastic restoring force of the polymer walls, causing permanent collapse.

Options for fragile structures:

Option 1 — Critical point drying (CPD)
After the IPA rinse, transfer the substrate to a critical point dryer before the IPA evaporates. The CPD replaces IPA with liquid CO2, then takes the CO2 above its critical point (31 degrees C, 74 bar) to transition directly from liquid to gas without a liquid-gas interface. No surface tension forces act on the structure. This is the most reliable method for very fine features.

Availability: CPD equipment is typically available in nanofabrication facilities but is not included with the GT2. Check with your facility manager.

Option 2 — Supercritical CO2 drying (alternate terminology for CPD)
Same as Option 1. The terms critical point drying and supercritical CO2 drying refer to the same process.

Option 3 — Gentle nitrogen stream at low pressure
For structures that are fragile but not at the extreme limit, low-pressure nitrogen (reduce regulator to minimum usable flow) from a distance of 15 to 20 cm is gentler than a standard nitrogen gun. Dry slowly, starting from the edges of the substrate and working inward.

Option 4 — Allow to air dry
In a clean environment (laminar flow hood or cleanroom), allowing the substrate to air dry slowly at room temperature generates less mechanical force than nitrogen blowing. This is only feasible in clean environments where airborne particulate contamination during the drying period is acceptable.

---

## IP-PDMS Specific Rinse Notes

IP-PDMS structures require a two-step IPA rinse. The first rinse removes PGMEA and the majority of uncured PDMS oligomers. However, PDMS oligomers have higher molecular weight than standard IP resin monomers and diffuse more slowly out of the cured network. A second fresh IPA rinse removes the remaining oligomers that were displaced from the structure interior during the first rinse.

After drying, if an IP-PDMS structure feels tacky, this indicates uncured oligomers on the surface. Return to a fresh PGMEA bath for 10 minutes, then repeat the two-step IPA rinse.

---

## GP-Silica Rinse Notes

The GP-Silica green body (the fragile particle compact after development) must be rinsed extremely gently. Do not agitate. Do not use a nitrogen gun. Submerge in IPA for 3 minutes undisturbed, then remove and allow to air dry in a clean environment. Even modest mechanical forces can fracture the green body at this stage.

---

Proceed to: uv_curing_station.md
