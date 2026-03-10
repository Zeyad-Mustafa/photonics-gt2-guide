# CAD Design — Section Overview

## What This Subfolder Covers

The CAD design stage is where everything begins. You create your 3D model on any computer using any CAD software that can export an STL file. The GT2 does not care what software you used — it only sees the STL output.

However, designing for two-photon polymerization is not the same as designing for a desktop 3D printer or for CNC machining. There are specific rules, constraints, and considerations that apply only to 2PP printing. Ignoring them leads to structures that look correct in CAD but fail during printing, collapse during development, or delaminate from the substrate.

This subfolder explains all of those rules and gives you a practical checklist to verify your design before exporting.

---

## Files in This Subfolder

| File | Contents |
|---|---|
| designing_for_2PP.md | All design rules specific to 2PP — minimum features, overhangs, anchors, shrinkage |
| recommended_cad_tools.md | Overview of CAD tools that work well with the GT2 workflow |
| stl_export_guide.md | How to export a correct STL from each major CAD tool |
| gwl_scripting_intro.md | Writing GWL code directly, bypassing STL entirely |
| design_rules_checklist.md | One-page checklist to run before every export |

---

## The One Thing Most Beginners Get Wrong

New GT2 users almost always design their first structure the same way they would design something for a desktop 3D printer — they create the shape they want and export it without any additional thought.

This works sometimes, but fails for several predictable reasons:

- Features are too thin and collapse during development
- There are no anchor structures to keep the print attached to the substrate
- Overhangs are too long and sag before they can polymerize fully
- The structure is oriented so that critical dimensions are in the axial direction, where resolution is 3 to 4 times worse than lateral

Reading designing_for_2PP.md before your first export will save you several failed prints.

---

After this subfolder, proceed to the DeScribe Software subfolder.
