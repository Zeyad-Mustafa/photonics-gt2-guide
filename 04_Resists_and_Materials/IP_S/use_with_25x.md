# IP-S — Use with the 25x Objective

> This file covers the specific steps and considerations for printing IP-S with the 25x objective. For the complete workflow, see Workflow B in 07_Step_by_Step_Workflows.

---

## The 25x + IP-S Combination

The 25x objective (NA 0.8) in DiLL mode is the most common printing configuration on the GT2. IP-S is its standard paired resist. Together they offer:

- Print field of 400 x 400 um (galvo) or 300 x 300 um (piezo)
- Practical feature sizes of ~1-5 um (galvo) or ~500 nm (piezo)
- Fast printing — galvo speeds up to 100 mm/s
- Excellent surface finish
- Low shrinkage for dimensional accuracy

This combination is used in the majority of published GT2 workflows and is the default starting point for new users.

---

## Substrate: ITO-Coated Glass

The standard substrate for 25x + IP-S is **ITO-coated glass**. ITO (Indium Tin Oxide) is a transparent conductive coating that provides a refractive index step sufficient for auto-interface detection.

Critical orientation: **ITO side must face the objective (face down).**

```
Sample holder (top)
        |
        | <- glass substrate (back side, faces up)
        | <- ITO coating (conductive side, faces down toward objective)
        |
   25x objective (below)
```

The refractive index step at the ITO-resist interface (approximately Dn ~ 0.04-0.05) is sufficient for reliable auto-interface detection.

> If you accidentally load the substrate ITO-side up, the laser must first pass through 1 mm of glass before reaching the ITO-resist interface. The system will fail to find the interface at the correct Z position, and your print will be offset or will fail entirely.

---

## Adjustment Ring: Critical Step

The 25x objective has a **correction collar (adjustment ring)** on its barrel that must be set correctly before printing with IP-S in DiLL mode.

Setting: **Set to "Glyc" position (the three longest bars).**

```
Adjustment ring positions on the 25x objective barrel:
|  |  |||  |  |  (shorter marks = Oil, Water settings)
         ^^^
     "Glyc" (glycerol) = DiLL setting for IP-S
```

This setting compensates for the spherical aberration introduced when the objective is designed for coverslip-corrected operation but is instead being used in dip-in mode. Setting it to any other position will reduce resolution and contrast.

See **[03_Objectives/25x_objective/adjustment_ring_guide.md](../../03_Objectives/25x_objective/adjustment_ring_guide.md)** for photographs and detailed instructions.

---

## Resist Application

1. Load the substrate into the Universal holder, ITO-side down.
2. On the exposed (top) surface of the substrate, apply **3-10 uL** of IP-S.
3. The drop should cover approximately 3-5 mm in diameter.
4. The drop should be domed, not flat — if it spreads flat immediately, the substrate may have contamination or residual solvent. Clean and retry.
5. Close the top hatch promptly.

IP-S has higher viscosity than IP-Dip2 and will not spread as aggressively. If it does not wet the substrate well, the substrate surface may benefit from an **oxygen plasma treatment** (30-60 seconds, improves wettability). See **[08_Development_and_Post_Processing/oxygen_plasma_treatment.md](../../08_Development_and_Post_Processing/oxygen_plasma_treatment.md)**.

---

## Laser Parameters (Starting Values)

| Parameter | Starting Value |
|---|---|
| Scan mode | Galvo (for most structures) |
| Laser power | 20-35% |
| Scan speed | 50,000-100,000 um/s (galvo) |
| Slice distance | 0.5-1.0 um |
| Hatch distance | 0.3-0.7 um |

---

## After Printing: Development

1. Remove the sample holder using the Exchange Holder dialog.
2. Carefully transfer the substrate to a PGMEA bath.
3. Develop for 20-30 minutes with gentle agitation (not vigorous — thin features can be dislodged).
4. Rinse in IPA for 5-10 minutes.
5. Allow to air dry or use a gentle N2 blow-dry.
6. UV cure at 405 nm for up to 20 minutes in the UV curing station.

---

## Related Files

- [overview.md](./overview.md)
- [properties.md](./properties.md)
- [handling_and_storage.md](./handling_and_storage.md)
- [03_Objectives/25x_objective/adjustment_ring_guide.md](../../03_Objectives/25x_objective/adjustment_ring_guide.md)
- [05_Substrates/ITO_coated_glass.md](../../05_Substrates/ITO_coated_glass.md)
- [07_Step_by_Step_Workflows/Workflow_B_25x_DiLL_IP_S/README.md](../../07_Step_by_Step_Workflows/Workflow_B_25x_DiLL_IP_S/README.md)