# ITO-Coated Glass — Standard Substrate for 25x DiLL

---

## What Is ITO-Coated Glass?

ITO stands for Indium Tin Oxide. It is a transparent, electrically conductive metal oxide that is deposited as a thin film (typically 100 to 200 nm thick) on one surface of a borosilicate glass slide.

The result is a substrate that is:
- Optically transparent in the visible spectrum
- Electrically conductive on the coated surface
- Mechanically rigid and flat
- Chemically stable in PGMEA and IPA

ITO-coated glass is the standard substrate for the 25x DiLL workflow. It is available pre-cut to 25x25 mm from Nanoscribe and from general laboratory suppliers.

---

## Why ITO Works for the 25x Workflow

The 25x objective using IP-S resin requires a substrate with delta-n of at least 0.04 relative to the resin. Plain borosilicate glass has a refractive index of approximately 1.52 — nearly identical to IP-S (1.478) — giving a delta-n of only about 0.04, which is borderline.

The ITO coating changes this situation. The ITO layer itself has a higher refractive index (approximately 1.8 to 2.0 depending on deposition conditions), and more importantly, the ITO surface creates an optical discontinuity that the interface finder can detect more reliably than plain glass.

Additionally, ITO is reflective enough at the GT2's detection wavelength to produce clear interference fringes during the approach step.

---

## Critical Orientation Rule

The ITO-coated side must face DOWN toward the objective.

This means the resin drop sits on the ITO surface, and the objective dips into the resin from below. If you flip the substrate so the uncoated glass faces the objective, the laser must focus through the full thickness of the glass before reaching the resin. This introduces severe spherical aberration at NA 0.8 and makes interface detection unreliable.

How to identify the ITO side:
- Use a multimeter set to resistance mode. Touch both probes to the same surface. The ITO side reads a finite resistance (typically 10 to 100 ohms per square). The bare glass side reads open circuit (infinite resistance).
- Some Nanoscribe substrates have a notch or label indicating the ITO side. Check the product packaging.
- Under certain lighting angles, the ITO side may appear very slightly golden or bluish. This is subtle and not always visible.

Mark the non-ITO edge with a permanent marker before cleaning so you can identify orientation after handling.

---

## Refractive Index Data

| Layer | Refractive Index at 780 nm |
|---|---|
| Borosilicate glass (bulk) | ~1.515 |
| ITO coating | ~1.8 to 2.0 |
| IP-S resin | 1.478 |
| IP-Q resin | 1.48 |
| Delta-n (ITO vs IP-S) | ~0.32 to 0.52 |

The large delta-n from the ITO layer is what makes interface detection reliable with the 25x objective.

---

## Cleaning Procedure for ITO Glass

ITO is conductive and relatively durable, but it can be damaged by harsh chemicals. Follow this procedure:

Step 1 — Acetone rinse
Pour acetone over the substrate and gently agitate for 30 seconds. This removes organic contamination, oils, and particulates.

Step 2 — IPA rinse
Rinse immediately with isopropanol for 30 seconds. This removes acetone residue.

Step 3 — DI water rinse
Rinse with deionized water for 20 seconds. Do not use tap water — mineral deposits will contaminate the surface.

Step 4 — Nitrogen blow dry
Dry from the center outward using a clean nitrogen gun. Do not wipe — wiping can deposit lint or scratch the ITO.

Step 5 (optional) — Oxygen plasma
If adhesion problems have occurred in previous prints, treat with O2 plasma for 60 to 120 seconds at 100 W. This removes any remaining organics and increases surface wettability dramatically.

Caution with plasma on ITO: prolonged or repeated O2 plasma treatment can increase the sheet resistance of the ITO layer, which may matter if you are using the ITO conductivity for downstream processing such as electrodeposition.

---

## Resin Application on ITO Glass

1. Set the substrate on the sample holder with the ITO side facing down.
2. Turn the substrate over briefly to apply resin — hold it ITO-side up.
3. Using the supplied pipette, deposit 1 to 2 small drops of IP-S onto the ITO surface.
4. The drop should form a semi-spherical bead. If it spreads flat immediately, the surface has too much wettability (possibly from over-treatment with plasma). Let it sit for 30 seconds and re-evaluate.
5. Turn the substrate back over (ITO down) and load into the holder immediately. Do not wait more than 15 to 20 minutes.

---

## Adhesion Considerations

Adhesion of IP-S printed structures to ITO is generally good without any adhesion promoter. However, for structures with a very small footprint (thin pillars, fragile overhangs) where adhesion forces are low, or for structures that will undergo aggressive downstream processing, consider:

- O2 plasma treatment before resin application (most effective)
- Methacryloxypropyltrimethoxysilane (MEMO) silanization if plasma is not sufficient — consult your lab's chemical safety protocols before using silane chemistry

---

## Storage

Store ITO-coated substrates in a clean, dust-free box. Avoid stacking them without interleaving tissue paper — scratches on the ITO surface will create adhesion problems and interfere with interface detection.

---

Proceed to: silicon_wafers.md
