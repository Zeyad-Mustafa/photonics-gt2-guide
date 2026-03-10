# GP-Silica — Workflow Special Steps

> GP-Silica printing has requirements that do not apply to any other resist. Failing to follow these rules will ruin your print or your machine. Read before starting.

---

## The 8-Hour Time Limit

**Once GP-Silica is applied to the substrate, you have a maximum of 8 hours to complete the print.**

After 8 hours, the paste begins to dry and harden unpredictably. The viscosity changes, the drop shape shifts, and the optical properties at the resist-substrate interface degrade. Prints started after 8 hours from resist application will fail or produce defective green bodies.

This is a hard constraint — it is not conservative advice. Plan your workflow accordingly:

- Do not apply GP-Silica until the machine is warmed up, the GWL file is loaded, and you are ready to immediately begin printing
- For long print jobs (> 6 hours), apply the resist only after confirming the print will complete within the 8-hour window
- If the print job will take longer than 8 hours, split it into multiple shorter jobs with fresh resist application for each

> To estimate print time before committing: load the GWL file in NanoWrite and use the print time estimator. See **[06_Software_Workflow/NanoWrite_Software/estimating_print_time.md](../../06_Software_Workflow/NanoWrite_Software/estimating_print_time.md)**.

---

## Substrate Requirements for GP-Silica

GP-Silica requires a substrate that:
- Can withstand furnace temperatures up to 1500 C without melting or reacting with silica
- Allows the sintered structure to be separated after sintering (or sacrificially destroyed)

Compatible substrates:
- Quartz (fused silica) wafers or plates — the green body can be sintered while attached; the structure may bond to the quartz substrate
- Alumina (Al2O3) plates — high temperature stable, the sintered structure typically does not bond strongly and can be separated
- Platinum or platinum-alloy foils — used in some protocols for easy release

Incompatible substrates:
- Standard borosilicate glass (softens at ~820 C — the sintering temperature of 1500 C will melt it)
- Silicon wafers (may react with silica at high temperature)
- ITO-coated glass (ITO layer will be destroyed; glass substrate melts)
- Polymer substrates of any kind

---

## Resist Application

GP-Silica is much more viscous than standard IP resists — it is a **paste**, not a flowing liquid. Apply it with a clean spatula or thick-tipped dropper:

1. Take a small amount of GP-Silica paste (approximately 10-20 uL)
2. Place it onto the center of the substrate
3. Gently spread to a thin, even layer approximately 1-2 mm thick and 3-5 mm in diameter
4. The layer should fully cover the printing area with some margin
5. Start the print immediately (8-hour clock starts now)

Do not apply GP-Silica more than 15 minutes before printing begins.

---

## Print Parameters

GP-Silica requires **lower scan speeds and adjusted laser power** compared to IP-S printed with the same 25x objective, because the composite paste has different absorption and sensitivity characteristics.

Consult Nanoscribe's current GP-Silica application note for the recommended parameter set. Starting points are approximately:
- Laser power: 30-50% (higher than IP-S)
- Scan speed: 10,000-30,000 um/s (slower than IP-S)
- Slice distance: 0.5-1 um
- Hatch distance: 0.5-0.8 um

Always run a calibration array with a fresh batch before printing your final geometry.

---

## After Printing: Green Body Handling

The as-printed GP-Silica structure (before furnace treatment) is called the **green body**. It is:

- Extremely fragile — the structure is held together only by the partially polymerized binder
- Cannot be developed in PGMEA like standard IP resists — GP-Silica uses its own development protocol
- Must be handled with extreme care under magnification if removal from substrate is required before sintering

Development of GP-Silica:
- Use the specific GP-Silica developer (consult the Nanoscribe application note — standard PGMEA may be insufficient to remove all binder)
- Rinse carefully with IPA
- Allow to dry completely before furnace loading — any residual solvent in the green body can cause cracking during debinding

---

## Related Files

- [overview.md](./overview.md)
- [debinding_and_sintering.md](./debinding_and_sintering.md)
- [11_Troubleshooting/gp_silica_print_timeout.md](../../11_Troubleshooting/gp_silica_print_timeout.md)
- [07_Step_by_Step_Workflows/Workflow_D_Glass_Structures_GP_Silica/special_requirements.md](../../07_Step_by_Step_Workflows/Workflow_D_Glass_Structures_GP_Silica/special_requirements.md)