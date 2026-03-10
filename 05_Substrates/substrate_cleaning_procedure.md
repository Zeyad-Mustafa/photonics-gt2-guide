# Substrate Cleaning Procedure

---

## Why Cleaning Matters

A dirty substrate causes problems at every stage of the GT2 workflow:

During interface detection: dust particles and organic contamination scatter the detection laser, creating false interfaces or noisy signals that confuse the interface finder.

During printing: particles under or on the substrate create local height variations. If a particle is large enough, it can cause the objective to crash during approach. Smaller particles under the print area create voids or adhesion failures at that location.

During development: contamination between the substrate and the printed structure weakens adhesion and can cause the structure to delaminate during solvent exposure.

In all cases: the effort invested in substrate cleaning is far less than the effort lost to a failed print.

---

## Standard Cleaning Protocol (Applies to All Substrates)

This four-step protocol removes organic contamination, particulates, and most inorganic residues. It is the minimum cleaning that should be performed before any GT2 print.

Step 1 — Acetone rinse

Pour or spray acetone over the substrate surface for 30 to 60 seconds. For stubborn contamination, submerge in a beaker of acetone and agitate gently. Acetone dissolves oils, photoresist residue, adhesive residue, and most organic compounds.

Do not let acetone dry on the surface before moving to the next step. Dried acetone leaves a residue worse than the original contamination.

Step 2 — IPA rinse

While the substrate is still wet with acetone, rinse immediately with isopropanol for 30 seconds. IPA displaces the acetone and dissolves any residue the acetone left behind. IPA also removes water-soluble contamination that acetone cannot reach.

Step 3 — DI water rinse

Rinse with deionized water for 20 to 30 seconds. This removes IPA and any ionic contamination. Do not use tap water — tap water contains mineral salts that deposit on the surface when it dries, leaving a haze that interferes with interface detection and adhesion.

Step 4 — Nitrogen blow dry

Dry the substrate using clean dry nitrogen from a gun or cylinder. Hold the nitrogen nozzle at a low angle and blow from the center of the substrate toward the edges. This pushes any remaining droplets off the surface rather than spreading them.

Do not wipe the substrate dry with a tissue or wipe — even cleanroom wipes leave lint, and wiping can scratch polished surfaces.

---

## Oxygen Plasma Treatment (Recommended for Most Substrates)

After the standard four-step protocol, O2 plasma treatment provides additional benefits that significantly improve print outcomes:

What plasma does:
- Removes any remaining organic monolayer contamination that solvents cannot reach
- Oxidizes the surface, creating hydroxyl groups (-OH) that are highly wettable and bond well to IP-series resins
- Sterilizes the surface (relevant for biomedical applications using IP-Visio)
- Improves resin drop geometry by increasing surface energy (the resin wets more uniformly)

Recommended parameters:

| Substrate | Power | Time |
|---|---|---|
| Silicon | 100 W | 120 seconds |
| ITO-coated glass | 100 W | 60 to 90 seconds |
| Quartz | 100 W | 120 seconds |
| 170 um borosilicate | 50 W maximum | 30 seconds |
| Polymer film | 50 W | 60 seconds (test first) |
| Gold-coated substrates | 100 W | 60 seconds |

After plasma treatment, proceed to resin application within 30 minutes. The activated surface begins to adsorb atmospheric contamination within minutes in normal lab air. In a cleanroom environment with HEPA filtration, the activated surface remains clean for longer.

---

## Substrate-Specific Considerations

ITO-coated glass:
Standard cleaning protocol applies. Avoid piranha solution — it can damage the ITO film. Limit plasma treatment to 90 seconds to avoid significantly altering ITO sheet resistance if conductivity is needed downstream.

Silicon wafers:
The most tolerant of aggressive cleaning. Full piranha etch is acceptable and produces the cleanest possible silicon surface. RCA clean is equally effective. For routine use, the standard four-step protocol plus plasma is sufficient.

Quartz (fused silica):
Standard protocol plus plasma. For critical optical applications, piranha etch or an RCA clean is preferred. Quartz holds a very clean surface well after plasma treatment.

170 um borosilicate (coverslips):
Handle by edges only throughout cleaning. Use gentle nitrogen pressure for drying to avoid cracking. No piranha — risk of etching the glass surface.

Gold-coated substrates:
Standard protocol. Plasma at 100 W for 60 seconds is effective and does not damage gold. If adhesion promoter (thiol chemistry) is to be applied, do so after plasma treatment.

Polymer films:
Test chemical compatibility before submerging. Some polymers dissolve in acetone. If acetone is incompatible, use isopropanol only, followed by DI water. O2 plasma is the most effective cleaning and activation method for polymer surfaces.

---

## Cleanliness Verification

Before loading the substrate into the GT2, verify cleanliness:

Visual inspection:
Hold the substrate at an angle under bright white light or a fluorescent lamp. Look for smears, particulates, or haze. A clean surface appears uniformly reflective without any distortion.

Optical microscope check (recommended before critical prints):
Inspect the print area at 10x to 50x magnification under an optical microscope. Any particles visible at this magnification are large enough to cause problems. A clean substrate should show only the bare substrate surface with no visible particulates.

Water contact angle (qualitative):
If plasma treatment was performed, a water droplet should spread almost completely flat on the substrate surface (contact angle less than 10 degrees). If the droplet beads up (contact angle greater than 30 degrees), the surface was not adequately cleaned or the plasma treatment did not activate the surface. Re-clean and re-treat.

---

## Common Contamination Sources and How to Avoid Them

Fingerprints:
Always handle substrates with clean powder-free gloves. Fingerprints contain oils and salts that contaminate the surface and are very difficult to fully remove even with cleaning.

Dust and particles:
Perform substrate preparation in the cleanest available environment (cleanroom if possible, or a laminar flow hood). Cover substrates immediately after cleaning and keep covered until resin is applied.

Lint from wipes and tissues:
Never wipe substrate surfaces. Use nitrogen blow dry and rinse techniques only.

Dissolved minerals from tap water:
Use only deionized water with resistivity above 1 megaohm-cm for final rinses.

Reuse of contaminated solvents:
Use fresh solvent poured from a clean bottle for each substrate. Do not re-use acetone or IPA that has been sitting in an open beaker — it absorbs water and accumulates contamination over time.

Previous resin residue:
If a substrate is being reused after a previous print, the cured polymer may remain adhered. Submerge in PGMEA for 20 to 30 minutes to dissolve any remaining uncured resin, then use standard cleaning. If cured polymer remains, it typically must be removed mechanically or by plasma ashing — do not attempt to dissolve it in PGMEA (cured polymer is resistant).

---

## Cleanroom vs Standard Lab Environment

For most GT2 work, a standard lab with laminar flow hood preparation is adequate. Cleanroom conditions (class 100 or better) produce noticeably fewer adhesion failures and interface detection problems, particularly for prints with very small footprint structures or when using the 63x objective where contamination at 160 nm scale is most significant.

If you are working in a standard lab without a laminar flow hood:
- Perform all substrate preparation away from air conditioning vents and high-traffic areas
- Work quickly after cleaning to minimize re-contamination time
- Keep substrates in a covered container at all times except during cleaning and resin application

---

This is the final file in Section 05 — Substrates.
Proceed to: Section 06 — Software Workflow.
