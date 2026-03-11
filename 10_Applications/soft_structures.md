# Soft Structures

## Why the GT2 Is Used for Soft Structures

Most GT2 applications produce stiff polymer structures. IP-S, IP-Dip2, and IP-Q all cure to materials with Young's moduli in the gigapascal range — comparable to hard plastics. This stiffness is appropriate for optical, mechanical, and photonic applications but excludes applications that require compliance, large elastic deformation, or stiffness matching to soft biological tissues.

IP-PDMS (a polydimethylsiloxane-based resin) changes this. It cures to a soft elastic material with Young's modulus in the megapascal range — three to four orders of magnitude softer than other IP resins — while remaining compatible with the 25x DiLL workflow. This enables fabrication of soft 3D structures that can deform substantially under load and return to their original shape.

---

## What Can Be Fabricated

Microfluidic membranes and valves: thin elastic membranes that deflect under applied pressure, used as pressure sensors, pneumatic valves, or peristaltic pump elements. Membrane thickness from approximately 5 um to several hundred um.

Soft actuators: structures that deform in response to a stimulus — pressure inflation, swelling in solvent, or thermal expansion. Bellows, chambers, and bilayer bending actuators are common geometries.

Cell culture substrates with controlled stiffness: flat or patterned IP-PDMS substrates with stiffness in the range of soft tissues, used for mechanobiology experiments where substrate stiffness directs cell differentiation.

Micropost arrays for traction force microscopy: arrays of slender IP-PDMS pillars whose deflection under cell-applied forces is measured to calculate the magnitude and direction of cellular traction forces. Pillar stiffness is tuned by adjusting pillar diameter and height.

Soft microgrippers: compliant mechanisms that grip delicate objects (cells, small organisms, fragile components) without damage, driven by fluid pressure, swelling, or magnetic actuation.

Wearable and skin-interfacing devices: soft polymer structures that conform to curved biological surfaces for biosensing or drug delivery.

Acoustic metamaterials: periodic soft structures that control sound propagation, using the large contrast in elastic modulus between IP-PDMS and a surrounding stiff matrix or substrate.

---

## Recommended Objective and Resist

The only resin for soft structures in the standard GT2 workflow: IP-PDMS with the 25x objective.

IP-PDMS is not compatible with the 63x or 10x objectives. The 25x is the required objective.

Important properties of IP-PDMS:

| Property | Value |
|---|---|
| Young's modulus after UV cure | 1 to 5 MPa |
| Elongation at break | 50 to 200 percent |
| Density | approximately 1.05 g/cm cubed |
| Optical clarity | Transparent in visible |
| Surface energy | Low (hydrophobic) |
| Development solvent | PGMEA |
| Development time | 25 to 35 minutes (longer than other resins) |

---

## Design Considerations

Minimum feature sizes: IP-PDMS structures have the same minimum feature constraints as other 25x prints (minimum wall approximately 2 um, minimum stable pillar approximately 1 um diameter). However, because IP-PDMS is much more compliant than IP-S, thin features are more susceptible to mechanical collapse during development and drying. In practice, use minimum wall thickness of 5 um or above for IP-PDMS to ensure structural stability.

Collapse during drying: IP-PDMS features are particularly prone to collapse from surface tension during the IPA-to-air drying transition. For arrays of thin pillars or membranes, critical point drying is strongly recommended. If CPD is not available, minimize pillar height-to-diameter aspect ratio and use low-pressure nitrogen for drying.

Stickiness and self-adhesion: uncured IP-PDMS is tacky. After printing but before development, avoid contact between the uncured sample and any surface — it will stick. After development and UV curing, the cured surface is still somewhat low-energy and may stick to itself if opposing faces contact each other. Design features to avoid self-contact in the as-printed configuration.

Swelling: PDMS-based materials absorb nonpolar organic solvents and swell significantly (20 to 100 percent volume increase) when immersed in toluene, hexane, or DCM. This is a known limitation for applications involving organic solvent streams. For aqueous applications, swelling is minimal.

Bonding IP-PDMS to a cover substrate: O2 plasma bonding works for IP-PDMS (same as conventional PDMS to PDMS bonding). Plasma-treat both surfaces at 100 W for 60 seconds and bring into contact within 30 seconds. The bond forms at room temperature and reaches full strength within 1 hour.

Micropost array design for traction force microscopy: post stiffness k = 3EI/L cubed where E is Young's modulus, I is the second moment of area (pi times d to the 4th divided by 64 for circular posts), and L is the post height. Adjust d and L to target a specific stiffness range matching the expected cell traction forces (typically 1 to 100 nN per post).

---

## Comparing IP-PDMS to Cast PDMS

| Property | IP-PDMS (GT2 printed) | Cast PDMS (Sylgard 184) |
|---|---|---|
| 3D geometry | True 3D | Planar (2D extruded) only |
| Minimum feature | approximately 2 um | approximately 5 to 10 um |
| Young's modulus | 1 to 5 MPa | 1 to 3 MPa |
| Fabrication time | Hours (single step) | Days (photolithography + casting) |
| Biocompatibility | Limited data | Extensively validated |
| Throughput | Low | High (many devices per mold) |

For applications requiring complex 3D soft geometry: use IP-PDMS.
For applications requiring extensive biocompatibility validation or high throughput: use cast PDMS from a GT2-printed master.

---

## Representative Results

IP-PDMS micropost arrays with post diameter 3 um, height 12 um, and spacing 6 um, used for traction force microscopy of human endothelial cells, have demonstrated measurement of forces with resolution of approximately 1 nN.

Soft pneumatic actuators with bellows geometry printed in IP-PDMS have demonstrated displacement of 100 um at pressure of 10 kPa, with reversible actuation over 1000 cycles.

3D IP-PDMS scaffolds with stiffness of 2 kPa have been used for cardiomyocyte culture, demonstrating beating cell monolayers on the soft 3D surface.

---

## Limitations

- Limited resist selection: IP-PDMS is the only soft resin in the Nanoscribe lineup. Its properties cannot be tuned in the same way that cast PDMS stiffness can be tuned by changing the crosslinker ratio.
- Longer development: IP-PDMS requires longer development times and is more prone to incomplete development than other resins. Follow the extended development protocol in development_times_table.md.
- Biocompatibility data gap: IP-PDMS has less published biocompatibility characterization than IP-Visio. Test cytotoxicity before cell contact experiments.

---

Proceed to: metallic_structures.md
