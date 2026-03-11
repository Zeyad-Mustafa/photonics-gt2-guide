# Section 08 — Development and Post Processing

## Overview

Development and post processing are the steps that happen after the laser has finished writing your structure. At the end of a print, your substrate sits in a pool of liquid resin. The polymerized structure exists inside that liquid, but it is surrounded and covered by uncured monomer that must be removed before you can see, measure, or use the structure.

Development is the chemical step that removes the uncured resin. Post processing includes UV curing to fully harden the structure, and any secondary fabrication steps that use the printed polymer as a starting point for further manufacturing.

These steps are not optional refinements. A structure that is not developed correctly will either retain uncured resin that obscures features, or will collapse and wash away entirely. A structure that is not UV cured will remain softer and weaker than its final specification and may change dimensions slowly over days or weeks.

---

## Why This Section Matters

Most new GT2 users invest significant effort in CAD design, DeScribe parameter optimization, and machine operation — and then rush through development because it seems simple. Development failures are responsible for a large fraction of lost prints. The most common causes are:

- Wrong solvent for the resin being developed
- Development time too short — uncured resin remains in fine features
- Development time too long — solvent swells and distorts the cured polymer
- Aggressive agitation that physically knocks over thin features
- Improper drying that causes collapse from surface tension
- Skipping UV post-curing, resulting in soft or dimensionally unstable structures

Reading and following this section carefully recovers many prints that would otherwise be considered failures.

---

## Files in This Section

| File | Contents |
|---|---|
| what_is_development.md | What development is, what happens chemically, why it is necessary |
| development_solvents.md | Which solvent to use for each resin, solvent properties, safety |
| development_times_table.md | Development times by resin type and structure geometry |
| ipa_rinse_procedure.md | Why IPA rinse is necessary and how to do it correctly |
| uv_curing_station.md | How the UV curing station works, settings, timing, safety |
| oxygen_plasma_treatment.md | When and how to use plasma after development |
| scaffold_and_shell_printing.md | How infill strategy affects development and what to expect |
| secondary_fabrication.md | Using printed structures as templates for metal deposition, molding, and etching |

---

## The Standard Post-Print Sequence

Every GT2 print follows this sequence after the laser finishes:

Remove substrate from holder
Immerse in primary development solvent (PGMEA for most resins)
Transfer to IPA rinse
Nitrogen blow dry or critical point dry
UV post-cure at 405 nm
Inspect and characterize

Secondary fabrication steps (metal deposition, electroplating, molding) follow after this sequence if needed.

---

After this section, proceed to Section 09 — Printing Modes or Section 10 — Applications depending on your needs.
