# Step 8 — Find the Interface

> Interface detection for the 25x + ITO substrate combination is the most reliable setup on the GT2. The large delta-n between IP-S (n = 1.478) and ITO (n ~ 1.8–2.0) produces a strong, clean reflection signal.

---

## Why This Is Easier Than Workflow A

With the 63x + borosilicate glass, the delta-n is approximately 0.004 — marginal for detection. With 25x + ITO, the delta-n is approximately 0.3–0.5. The system finds this interface quickly and reliably in nearly all cases.

If interface detection still fails with this substrate combination, the most likely causes are mechanical — the substrate was loaded ITO-side up, or the objective is not in the beam path.

---

## Procedure

The procedure is identical to Workflow A Step 8. Refer to [Workflow A / step_08_find_interface.md](../Workflow_A_63x_DiLL_IP_Dip2/step_08_find_interface.md) for the full step-by-step.

Additional notes for Workflow B:
- Interference fringes will appear sooner and more brightly than with the 63x + glass combination, due to the higher delta-n
- The auto-interface finder typically completes in under 30 seconds for ITO substrates
- If the system detects the interface but the Z value seems too high (larger than expected), it may have found the top surface of the glass rather than the ITO bottom surface — verify by checking the displayed Z value against the known glass thickness (~1.1 mm for a standard slide)

---

## Related Files

- [step_09_run_print_job.md](./step_09_run_print_job.md)
- [05_Substrates/ITO_coated_glass.md](../../05_Substrates/ITO_coated_glass.md)
- [06_Software_Workflow/NanoWrite_Software/sample_approach.md](../../06_Software_Workflow/NanoWrite_Software/sample_approach.md)
- [11_Troubleshooting/interface_not_found.md](../../11_Troubleshooting/interface_not_found.md)
