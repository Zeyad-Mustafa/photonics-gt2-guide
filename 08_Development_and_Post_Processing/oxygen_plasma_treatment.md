# Oxygen Plasma Treatment

## Overview

Oxygen plasma treatment is a dry surface treatment that uses ionized oxygen gas to modify surface chemistry. In the GT2 workflow, plasma is used in two distinct contexts:

Before printing: to clean and activate the substrate surface, improving resin wettability and adhesion of the printed structure.

After printing and development: to modify the surface of the printed polymer structure itself, changing its chemical properties for downstream applications.

Both uses are covered in this file.

---

## How Oxygen Plasma Works

A plasma system creates a partially ionized gas by applying radio frequency (RF) energy to oxygen gas at low pressure (typically 0.1 to 1 mbar). The ionized oxygen species (O, O2+, O3, electrons) are highly reactive.

When these species contact a surface they:

Remove organic contamination: carbon-carbon and carbon-hydrogen bonds are broken and volatilized as CO2 and H2O. This is the primary cleaning mechanism. It removes contaminants that solvents cannot touch — adsorbed hydrocarbons, residual photopolymer, fingerprint oils.

Oxidize the surface: the outermost molecular layer of the material is oxidized, converting hydrophobic groups (such as CH3 from silicone contamination) to hydrophilic groups (OH, COOH). This dramatically increases surface energy and wettability.

Etch material: at high power or long times, plasma physically etches away material. This can be used intentionally (plasma ashing to remove polymer) or it is an unwanted side effect of over-treatment.

---

## Plasma Treatment Before Printing

Purpose: clean the substrate and increase its surface energy so the resin drop wets the surface more uniformly and the cured polymer adheres more strongly.

When to use it:
- Always recommended for silicon and quartz substrates
- Recommended for ITO glass when adhesion of large-footprint structures is critical
- Required when adhesion failures have occurred on a previously treated substrate
- Before printing biomedical structures with IP-Visio where surface sterility matters

Parameters for pre-print treatment:

| Substrate | Power | Time |
|---|---|---|
| Silicon | 100 W | 90 to 120 seconds |
| Quartz | 100 W | 90 to 120 seconds |
| ITO-coated glass | 100 W | 60 seconds |
| 170 um borosilicate | 50 W | 30 seconds |
| Gold-coated substrate | 100 W | 60 seconds |

After plasma treatment, apply resin within 30 minutes. The activated surface begins to adsorb atmospheric hydrocarbons (recontamination) within minutes in an uncontrolled lab environment.

Important note on ITO: repeated or prolonged O2 plasma increases the sheet resistance of ITO. If the ITO conductivity is needed for downstream electrodeposition or electrical measurements, limit plasma treatment to 60 seconds and avoid repeated treatment of the same substrate.

---

## Plasma Treatment After Printing

Purpose: modify the surface chemistry of the printed polymer for downstream applications.

Common after-print plasma applications:

Application 1 — Bonding polymer structures to a second substrate
Printed microfluidic chips and lab-on-chip devices must often be sealed to a flat cover substrate. O2 plasma treatment (60 seconds at 100 W) of both the printed structure and the cover substrate generates reactive surface groups that form covalent Si-O-Si bonds when the two surfaces are pressed together within 30 seconds of plasma treatment. This is the standard method for sealing PDMS-based microfluidic devices and works similarly for IP-PDMS structures.

Application 2 — Improving hydrophilicity for aqueous applications
Printed polymer structures are inherently hydrophobic. For biological applications using IP-Visio scaffolds or IP-S devices, hydrophilicity is required for cell adhesion and aqueous reagent flow. O2 plasma for 30 to 60 seconds converts surface CH groups to OH and COOH groups, making the surface hydrophilic. This effect is temporary — surfaces rehydrophobize over 24 to 48 hours in air. Perform plasma treatment immediately before cell seeding or device filling.

Application 3 — Surface functionalization primer
O2 plasma-treated polymer surfaces can be functionalized with silane coupling agents (aminosilane, epoxysilane, etc.) to attach biomolecules, antibodies, or other functional groups. Plasma treatment creates the OH groups on the polymer surface that are needed for silane bonding. Perform silanization within 1 hour of plasma treatment for best results.

Application 4 — Removing uncured resin residue
If development was incomplete and residual monomer has dried on the structure surface, a brief O2 plasma (30 seconds at 50 W) can remove this surface residue. This is a delicate operation — too much plasma will etch into the structure itself. Use conservatively.

---

## What Plasma Treatment Does Not Do

Plasma treatment does not:
- Repair collapsed or broken structures — mechanical failure is permanent
- Remove fully cured polymer — cured IP-series polymer is resistant to short plasma exposures (it is etched, but slowly)
- Substitute for proper substrate cleaning before printing — plasma is a surface treatment, not a bulk cleaning method
- Permanently hydrophilize surfaces — hydrophilicity degrades over 24 to 48 hours

---

## Safety

O2 plasma equipment operates at high voltage and low pressure. The RF generator and vacuum chamber must only be operated according to the instrument-specific SOP for your facility.

- Do not open the chamber during a plasma cycle
- Do not place flammable materials in the chamber
- Do not exceed maximum recommended power for your instrument
- Allow the chamber to vent to atmospheric pressure before opening
- Some plasma systems generate ozone (O3) as a byproduct — use in a ventilated area

---

Proceed to: scaffold_and_shell_printing.md
