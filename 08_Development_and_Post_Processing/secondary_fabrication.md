# Secondary Fabrication

## Overview

In many research applications, the printed polymer structure is not the final device. It is an intermediate step — a template, mold, scaffold, or mask — that enables a subsequent fabrication process. The printed polymer defines the geometry, and another material provides the final functional properties.

This file describes the most commonly used secondary fabrication processes compatible with GT2 printed structures, the requirements each process places on the polymer template, and the integration considerations for each.

---

## Physical Vapor Deposition (PVD)

Physical vapor deposition includes electron beam evaporation and sputter deposition. Both deposit thin films of metal or other materials onto the substrate surface by condensing vapor onto surfaces exposed to the vapor source.

What can be deposited: gold, platinum, titanium, chromium, aluminum, silicon dioxide, titanium nitride, and many other materials.

How the printed structure is used as a template:

Method 1 — Deposition over the structure
The printed polymer structure acts as a 3D scaffold. Metal is deposited over the top and sides of the structure, conformally coating it. The result is a metal-coated polymer structure. If full metal encapsulation is desired, multiple depositions from different angles are needed to coat shadowed regions.

Method 2 — Liftoff
The polymer structure is printed in a pattern that covers the regions where metal is not wanted. Metal is deposited over the entire substrate, covering both the substrate and the polymer. The polymer is then dissolved in PGMEA or acetone, lifting off the metal on top of it and leaving metal only in the regions between the polymer features. This is the inverse tone of the polymer pattern.

Requirements for PVD compatibility:
- The printed polymer must be fully developed and UV cured before entering the PVD chamber
- The deposition chamber is under high vacuum (10 to the minus 6 mbar) — residual solvent in the polymer must be fully evaporated before pump-down, or it will outgas and contaminate the vacuum
- Allow the substrate to bake at 60 degrees C for 30 minutes in an oven (or under a heat lamp in a clean environment) after UV curing to ensure complete solvent removal before PVD
- Temperature during deposition must remain below the glass transition temperature of the polymer (typically above 100 degrees C for IP-series resins) — electron beam deposition can locally heat the substrate; use low deposition rates and monitor temperature

---

## Electrodeposition

Electrodeposition (electroplating) deposits metal from solution onto a conductive surface by driving a current through an electrolytic cell. It produces thicker, denser metal deposits than PVD and is used when bulk metal structures are needed.

How the printed structure is used:

The printed polymer acts as a mold. The substrate is coated with a thin conductive seed layer (typically 5 nm titanium + 50 nm gold by PVD, deposited before printing). The polymer structure is printed on this conductive surface. During electrodeposition, metal deposits only on the exposed conductive areas (the gaps between polymer features) and does not plate onto the insulating polymer. After deposition, the polymer is removed to reveal metal structures whose geometry is the inverse of the printed pattern.

Materials that can be electrodeposited: gold, nickel, copper, silver, platinum, palladium, and many alloys.

Requirements for electrodeposition compatibility:
- The substrate must have a continuous conductive seed layer accessible to the electrolyte
- The printed polymer must be chemically resistant to the plating electrolyte for the duration of deposition — most IP-series polymers are compatible with common gold, nickel, and copper plating solutions; confirm with a compatibility test before critical samples
- The polymer walls must be tall enough to confine the deposited metal to the desired regions — if the metal grows taller than the polymer mold walls, it will spread laterally (overplating)

Integration sequence:
1. Deposit seed layer (Ti/Au) on substrate by PVD
2. Print GT2 structure on seed layer surface (the conductive side)
3. Develop and UV cure the polymer mold
4. Electrodeposit metal to fill the spaces between polymer features
5. Remove polymer mold in PGMEA or by O2 plasma ashing
6. Optionally remove seed layer by chemical etching (gold etch or titanium etch)

---

## Atomic Layer Deposition (ALD)

ALD deposits conformal ultra-thin films (1 to 100 nm) of metal oxides, metals, and nitrides using sequential self-limiting gas-phase reactions. The key property of ALD is perfect conformality — it coats every exposed surface, including deep inside pores and on the inner walls of hollow structures, with a uniform film thickness.

How the printed structure is used:

ALD is used to coat 3D printed polymer templates with functional materials:
- Al2O3 (alumina) for electrical insulation, surface hardening, or etch masks
- TiO2 for photocatalysis or high-index optical coatings
- ZnO for piezoelectric or semiconducting applications
- Pt or Pd for catalytic surfaces

ALD can also conformally coat scaffold and shell structures from the inside out.

Requirements for ALD compatibility:
- ALD processes typically run at 100 to 300 degrees C. IP-series polymers are stable below approximately 120 degrees C under vacuum conditions. For ALD processes requiring temperatures above 120 degrees C, the polymer will deform or char. Use only low-temperature ALD processes (below 100 degrees C) or be aware that the polymer template will not survive the deposition and will act as a sacrificial scaffold.
- The substrate must fit in the ALD reactor — check dimensions against your facility's reactor
- Allow complete solvent removal from the polymer before ALD (bake at 60 degrees C for 30 minutes)

---

## Soft Lithography and Molding

The printed polymer structure can be used as a master mold to cast multiple replicas in PDMS (polydimethylsiloxane) or other soft materials.

How it works:

Uncured liquid PDMS (Sylgard 184 or equivalent, mixed at 10:1 base to crosslinker ratio) is poured over the printed polymer master. The PDMS is degassed under vacuum to remove bubbles, then cured at 60 to 80 degrees C for 2 to 4 hours. After curing, the PDMS is peeled off the master, producing a negative replica of the polymer structure.

This process can be repeated many times from the same master, making soft lithography an efficient way to produce many copies of a GT2-printed geometry without using the GT2 for each copy.

Requirements:
- The polymer structure must be UV cured before molding — uncured monomer from the polymer can inhibit PDMS curing at the contact interface, producing a sticky, partially cured PDMS surface
- Apply a release agent to the polymer master before pouring PDMS (trichloro(1H,1H,2H,2H-perfluorooctyl)silane vapor treatment is standard) to prevent adhesion and allow clean release
- Structures with very high aspect ratio features or extreme undercuts may not release cleanly from PDMS — design for releasability (draft angles, limited undercuts)

---

## Wet Etching Using Printed Structure as Etch Mask

The printed polymer can function as an etch-resistant mask for wet chemical etching of the substrate beneath it.

Compatible etch systems:
- Silicon: KOH wet etch (anisotropic, follows crystal planes) or TMAH etch. IP-series polymers are resistant to KOH at typical etch concentrations (20 to 30 percent by weight) and temperatures (60 to 80 degrees C) for moderate etch times (up to approximately 30 minutes)
- Silicon dioxide: buffered HF (BHF) or dilute HF. IP-series polymers have limited HF resistance — test compatibility before committing a critical sample
- Metals: specific metal etchants vary — confirm polymer compatibility before use

Requirements:
- The polymer must completely cover the regions to be protected from etching — any pinholes or gaps in the polymer will result in unwanted etching below
- After etching, remove the polymer mask in PGMEA or by O2 plasma ashing
- Lateral undercut of the etch (material removed laterally under the mask edges) must be accounted for in the design — the final etched feature will be larger than the polymer mask opening by the amount of lateral undercut

---

## Plasma Etching Using Printed Structure as Etch Mask

Similar to wet etching, the polymer structure can mask substrate areas from plasma etching (reactive ion etching, deep reactive ion etching, etc.).

Etch selectivity: the etch selectivity between the polymer mask and the substrate material determines how thick the polymer mask must be. Common silicon etch processes (SF6 plasma) etch silicon much faster than polymer (selectivity of 10:1 to 50:1). This means a 1 um thick polymer mask can protect silicon through 10 to 50 um of etch depth.

For processes requiring very high polymer etch resistance, a thin hard mask layer (SiO2 or Al2O3 deposited by ALD or PVD) can be added on top of the polymer mask before plasma etching.

---

This is the final file in Section 08 — Development and Post Processing.
Proceed to Section 09 — Printing Modes.
