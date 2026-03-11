# Interface Not Found

> NanoWrite reports "Interface not found" or the approach procedure completes but sets Z = 0 at an incorrect position. This means the automatic surface detection failed to locate the substrate-resist interface.

---

## What Interface Detection Does

Before every print, the GT2 scans the objective upward in Z while monitoring the reflected laser intensity. At the substrate-resist interface, the refractive index changes from n_resist to n_substrate. This change causes a detectable reflection. NanoWrite finds this reflection peak and sets it as Z = 0.

If no detectable reflection is found, NanoWrite either throws an "Interface not found" error or, worse, continues and sets Z = 0 at the wrong position (the stage limit, a stray reflection, or the wrong interface). Printing with incorrect Z = 0 places every voxel in the wrong location.

---

## Causes and Fixes

### Cause 1 — Delta-n is too small

The most fundamental requirement for interface detection is a sufficient refractive index contrast (delta-n) between the resist and the substrate. If delta-n is too small, the reflected signal is below the detection threshold.

| Interface | delta-n | Detection reliability |
|---|---|---|
| IP-Dip2 / quartz | 0.053 | Excellent |
| IP-S / ITO glass | ~0.3–0.5 (ITO layer) | Excellent |
| IP-Dip2 / borosilicate | 0.004 | Marginal — may fail |
| IP-Q / silicon | ~0.04 | Good |
| GP-Silica / quartz | ~0.05 | Good |

**Fix:** If using borosilicate glass with IP-Dip2, switch to quartz or ITO-coated glass substrates. Alternatively, add a thin metallic adhesion layer (Ti 5 nm / Cr 5 nm) between the substrate and resist — the metal-resist interface has a very high delta-n and is reliably detected.

---

### Cause 2 — Flat resist drop (10x + IP-Q only)

If using the 10x objective with IP-Q and the drop is flat rather than dome-shaped, the bottom of the drop has no air-resist interface to detect. This is covered in detail in [flat_resist_drop_problem.md](./flat_resist_drop_problem.md).

**Fix:** Remove the flat drop, reclean the substrate, and reapply with correct drop volume and shape before reloading.

---

### Cause 3 — Objective did not contact the resist

For DiLL mode, the objective tip must be submerged in resist before the Z approach begins. If the resist volume is insufficient, the objective approaches but never enters the resist — it passes through air and finds nothing.

**Fix:** Check that the resist drop fully covers the objective front element. For the 25x (380 um working distance), the drop must be at least 0.5 mm tall above the substrate. For the 63x (360 um working distance), a 5–10 uL drop is usually sufficient.

---

### Cause 4 — Air bubble directly below the interface

An air bubble trapped in the resist directly in the path of the approaching objective will produce a spurious reflection. NanoWrite may detect the bubble surface as Z = 0 and set it there — placing Z = 0 several hundred micrometers above the true substrate surface. Printing then occurs inside the bubble or above the resist.

**Fix:** Before loading, inspect the resist drop under the microscope and remove visible bubbles by gently touching them with the tip of a clean tweezers or by re-pipetting the resist. Do not print if bubbles are present.

---

### Cause 5 — Incorrect surface selected (wrong side of substrate)

For ITO substrates and some double-polished wafers, there are two surfaces: the correct printing side and the back side. If the substrate is loaded upside down, interface detection may find the back surface. Z = 0 is then set at the wrong surface — typically 0.5–1 mm away from the actual printing surface.

**Fix:** Confirm substrate orientation before loading. For ITO substrates: the ITO-coated side is conductive — verify with a multimeter before loading (ITO side to objective, glass side up). See [07_Step_by_Step_Workflows/Workflow_B_25x_DiLL_IP_S/step_04_prepare_ITO_substrate.md](../07_Step_by_Step_Workflows/Workflow_B_25x_DiLL_IP_S/step_04_prepare_ITO_substrate.md).

---

### Cause 6 — Objective tip is dirty

A film of dried resist or contamination on the objective front element will scatter the approach beam. The reflected signal is weakened or distorted and the threshold detection may fail.

**Fix:** Clean the objective tip with PGMEA followed by IPA on a lens tissue before the next attempt. Inspect the front element under oblique lighting — it should be perfectly clear.

---

### Cause 7 — Laser power is too low for approach scan

Interface detection uses the laser at low power (well below the polymerization threshold), but there is a minimum power level needed for the detector to see the reflection. If laser power was manually set very low, the detection signal may be below threshold.

**Fix:** Confirm the laser power setting in NanoWrite during the approach procedure is in the recommended range (typically 5–15% for approach — check your facility SOP).

---

## Confirming Z = 0 Is Correct After Detection

After a successful approach, do not assume the detected position is correct. Confirm it:

1. In AxioVision, slowly move the Z position from below Z = 0 upward through Z = 0. Watch the interference fringes in the camera image.
2. Below Z = 0 (inside the resist): fringes visible, changing with Z.
3. At Z = 0 (at the substrate surface): fringes disappear or change character sharply.
4. Above Z = 0 (inside the substrate): fringes gone, image dark or dim.

The fringes should disappear at a single Z position, not gradually over 10–20 um. If they fade gradually, detection may have found a broad or dirty interface — consider recleaning and re-running the approach.

---

## Related Files

- [flat_resist_drop_problem.md](./flat_resist_drop_problem.md)
- [07_Step_by_Step_Workflows/Workflow_A_63x_DiLL_IP_Dip2/step_08_find_interface.md](../07_Step_by_Step_Workflows/Workflow_A_63x_DiLL_IP_Dip2/step_08_find_interface.md)
- [05_Substrates/interface_detection_requirements.md](../05_Substrates/interface_detection_requirements.md)
- [02_Machine_Components/microscope_module.md](../02_Machine_Components/microscope_module.md)
