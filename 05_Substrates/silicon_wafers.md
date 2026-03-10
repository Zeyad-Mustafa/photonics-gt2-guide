# Silicon Wafers

---

## Why Silicon Is an Excellent GT2 Substrate

Silicon has a refractive index of approximately 3.5 at 780 nm. This is dramatically higher than any IP-series resin (1.47 to 1.51), giving a delta-n of approximately 2.0 — far above the minimum 0.04 needed for interface detection. Silicon produces the most reliable, consistent interface detection of any GT2 substrate.

Additional advantages:
- Extremely flat surface (polished wafers have surface roughness below 1 nm Ra)
- Compatible with all IP-series resins
- Compatible with all DiLL objectives (10x, 25x, 63x)
- Excellent adhesion to IP-series polymers
- Widely used in downstream microfabrication — silicon wafer pieces integrate naturally into photolithography, etching, and deposition workflows
- Inexpensive and readily available

---

## Wafer Types and Specifications

Most GT2 applications use standard silicon wafers with the following specifications:

| Property | Typical Value |
|---|---|
| Diameter | 100 mm (4 inch) or 150 mm (6 inch) |
| Thickness | 500 to 675 um |
| Orientation | (100) for most applications |
| Doping | P-type or N-type — does not affect GT2 printing |
| Surface | Single-side polished (SSP) — polished side is the print surface |
| Resistivity | Not critical for printing |

Double-side polished (DSP) wafers are also compatible but are more expensive and the extra polish on the back side provides no benefit for standard GT2 use.

---

## Cutting Wafers to 25x25 mm Pieces

The GT2 sample holder requires 25x25 mm substrate pieces. Full wafers must be cut before use.

Method 1 — Dicing saw (recommended)
A DISCO dicing saw or equivalent produces clean, straight cuts with minimal chipping. This is the preferred method in most cleanroom facilities.

Procedure:
1. Mount the wafer on a dicing tape frame
2. Program the saw for 25x25 mm grid cuts
3. Cut at a blade speed and feed rate appropriate for silicon (consult your facility's SOP)
4. Remove pieces from the dicing tape carefully
5. Clean immediately after dicing — dicing coolant leaves residue

Method 2 — Scribe and cleave
For labs without a dicing saw, silicon can be cleaved along crystal planes using a diamond-tipped scribe.

Procedure:
1. Use a ruler and diamond scribe to score a line on the polished surface
2. Place the score line over a hard straight edge (such as the edge of a glass slide)
3. Apply gentle downward pressure — the wafer will cleave along the crystal plane
4. Silicon cleaves cleanly along (110) planes on a (100) wafer

Limitation: Scribed cuts follow crystal planes. For (100) silicon, this means cuts at 0 and 90 degrees to the flat. Angled cuts will not cleave cleanly.

Method 3 — Laser dicing
Some facilities have laser dicing systems. These produce clean cuts but may leave a heat-affected zone. Clean thoroughly before use.

---

## Polished Side vs Rough Side

Always use the polished side as the print surface (facing down toward the objective in DiLL mode).

How to identify the polished side:
- The polished side is mirror-like and reflects a clear image
- The rough (back) side appears matte or hazy
- Single-side polished wafers have an obvious difference between the two sides

If you accidentally print on the rough side:
- Interface detection may fail (rough surface scatters detection light)
- Adhesion is unreliable (rough surface has inconsistent contact with resin)
- Print quality will be significantly degraded

---

## Cleaning Silicon Wafer Pieces

Silicon is chemically robust and tolerates aggressive cleaning. Standard procedure:

Step 1 — Acetone
Rinse or submerge in acetone for 1 minute with gentle agitation. Removes organic contamination, photoresist residue, and dicing tape adhesive.

Step 2 — IPA
Rinse with IPA for 30 seconds. Displaces acetone.

Step 3 — DI water
Rinse with deionized water for 30 seconds.

Step 4 — Nitrogen dry
Blow dry from center outward with clean nitrogen.

Step 5 (strongly recommended) — Oxygen plasma
Treat with O2 plasma for 120 seconds at 100 W. Silicon oxide grows on the surface during plasma treatment, which is highly wettable and provides excellent adhesion to IP-series resins. This step is particularly important for the 10x + IP-Q workflow where large structures need maximum adhesion.

For more aggressive cleaning (removing metal contamination or stubborn residue):
- Piranha solution (H2SO4 : H2O2, 3:1) — extremely effective, extremely hazardous. Only perform if trained and with appropriate safety equipment and disposal procedures.
- RCA clean — standard semiconductor cleaning sequence. Consult your facility's protocol.

---

## Adhesion to IP-Series Resins on Silicon

Silicon generally provides excellent adhesion to cured IP-series polymers, particularly after O2 plasma treatment. However, large-footprint structures (wider than a few hundred microns) can experience adhesion failure if:

- The silicon surface was not plasma-treated
- There is significant resin shrinkage pulling the structure away from the substrate
- Development involves aggressive agitation (sonication — avoid this)

If adhesion failure is occurring repeatedly on silicon, apply MEMO silane adhesion promoter or use a gentle spin-coat of SU-8 as an adhesion layer before printing.

---

## Silicon in Downstream Processing

Silicon wafer pieces are ideal substrates when your GT2 structure is a step in a larger fabrication process:

- Etching: printed polymer structures can serve as etch masks for silicon etching (SF6 plasma, KOH wet etch, TMAH)
- Metal deposition: physical vapor deposition (PVD) of metals directly onto printed structures on silicon
- Electrodeposition: requires conductive substrate — deposit a seed layer of gold or titanium/gold before printing, then electroplate after development
- Liftoff: print in negative tone — expose the field, develop, deposit metal, liftoff the polymer to leave metal structures

---

Proceed to: borosilicate_glass_170um.md
