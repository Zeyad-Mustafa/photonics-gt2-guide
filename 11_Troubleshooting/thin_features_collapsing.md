# Thin Features Collapsing

> Pillars, walls, fins, or overhanging beams that look intact when wet are lying flat on the substrate after development and drying. Or they are standing but visibly bent. This is capillary collapse — the dominant failure mode for high-aspect-ratio micro- and nanostructures.

---

## What Is Capillary Collapse

During the final drying step of development, the solvent (IPA or PGMEA) evaporates from the surface of the structure. As the liquid-air interface recedes across a thin feature, surface tension generates a lateral force on the feature. For a cylinder of radius r and height h, the capillary restoring force pulling it sideways scales as:

```
F_capillary ~ gamma * r / h^2 (approximately)
```

Where gamma is the surface tension of the solvent. This force can exceed the elastic restoring force of the polymer, causing the feature to bend permanently. If it bends far enough, it contacts an adjacent feature or the substrate and adheres (due to van der Waals forces between wet polymer surfaces), and the feature remains collapsed even after drying.

This is not an exposure problem and not an adhesion problem. It is a mechanical problem with the drying step.

---

## Which Features Are at Risk

Features with high aspect ratio (height / width) are vulnerable. Approximate collapse thresholds for IP-Dip2 at 63x in IPA:

| Feature | Approximate aspect ratio limit |
|---|---|
| Isolated pillar | 10:1 (e.g., 1 um dia, 10 um tall) |
| Wall (long thin fin) | 7:1 (e.g., 0.5 um thick, 3.5 um tall) |
| Overhanging cantilever | 5:1 (e.g., 1 um wide, 5 um long overhang) |

These numbers depend on feature width, polymer stiffness, and solvent surface tension. Thinner features and taller features collapse more easily. Narrower gaps between features make adhesion between collapsed features more likely.

---

## Fixes

### Fix 1 — Critical Point Drying (CPD)

CPD is the definitive solution. It eliminates the liquid-vapor interface entirely during drying:

1. After IPA rinse, the sample is loaded into a pressure vessel with liquid CO2.
2. CO2 miscibility with IPA allows it to flush the IPA out of the structure completely.
3. Temperature and pressure are raised above the CO2 critical point (31.1 degrees C, 73.8 bar).
4. The CO2 is then vented as gas — because you are above the critical point, there is no liquid-vapor phase boundary and therefore zero surface tension.

Result: no capillary force, no collapse.

CPD chambers are standard equipment in most electron microscopy labs. If your facility has a Tousimis Autosamdri or similar CPD system, this is the correct tool for any structure with aspect ratios above about 5:1.

The full CPD procedure is in [08_Development_and_Post_Processing/scaffold_and_shell_printing.md](../08_Development_and_Post_Processing/scaffold_and_shell_printing.md).

---

### Fix 2 — Use a lower-surface-tension drying solvent

If CPD is unavailable, replace the final IPA rinse with a lower-surface-tension solvent:

| Solvent | Surface tension (mN/m) | Notes |
|---|---|---|
| Water | 72 | Very high — do not use for final rinse |
| IPA | 23 | Standard — moderate surface tension |
| PGMEA | 26 | Similar to IPA |
| HFE-7100 | 13.6 | Fluorocarbon; very low surface tension; not compatible with all resists |
| Pentane | 15 | Very low surface tension; high flammability — check safety clearance |

PGMEA as the final rinse (instead of IPA) can reduce capillary force without CPD. HFE-7100 (a fluorocarbon ether) is the best non-CPD option for extremely fine features.

---

### Fix 3 — Redesign to reduce aspect ratio

The most permanent fix is to modify the structure:

- **Add lateral connectors** between adjacent pillars. A thin strut (1 um wide) connecting pillars at mid-height acts as a mechanical brace during drying, then can be sacrificed (removed by FIB or dissolving) afterward.
- **Widen the base.** Increasing pillar diameter from 0.5 to 1.0 um roughly quadruples the stiffness.
- **Reduce height.** If the structure's height is a free parameter, reducing it improves the aspect ratio.
- **Use a scaffold.** Print a sacrificial surrounding scaffold that mechanically restrains the features during development, then dissolve or remove it.

---

### Fix 4 — Use a stiffer resist

IP-Dip2 has a Young's modulus of approximately 1.2–1.5 GPa when fully cured. IP-S has similar stiffness. For the highest stiffness per volume, IPX-Clear or GP-Silica (after sintering to glass) are more resistant to capillary collapse.

If your application permits a resist change, discuss material alternatives with your supervisor.

---

### Fix 5 — UV cure before development

UV flood curing (405 nm, 10–20 minutes) after printing but before development maximizes the cross-linking density in the polymer, increasing mechanical stiffness. This does not eliminate capillary collapse for very high aspect ratios, but it helps at the margin.

---

## Identifying Collapse vs. Other Failures

| Observation | Likely cause |
|---|---|
| Features flat on the substrate, hinged at base | Capillary collapse |
| Features straight but adhered to adjacent feature | Capillary collapse + adhesion between wet surfaces |
| Features fractured — broken off, debris present | Washed off / too aggressive development (see [structure_washed_off.md](./structure_washed_off.md)) |
| Features absent entirely | Underexposure or adhesion failure |
| Features bent but still standing | Early-stage capillary collapse; not yet stuck |

---

## Related Files

- [structure_washed_off.md](./structure_washed_off.md)
- [08_Development_and_Post_Processing/scaffold_and_shell_printing.md](../08_Development_and_Post_Processing/scaffold_and_shell_printing.md)
- [07_Step_by_Step_Workflows/Workflow_A_63x_DiLL_IP_Dip2/step_10_development.md](../07_Step_by_Step_Workflows/Workflow_A_63x_DiLL_IP_Dip2/step_10_development.md)
