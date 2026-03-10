# Step 5 — Run the Print Job

> Print job execution for the 10x is the same as Workflow A and B, but with galvo mode active and potentially very long print times for large volumes. Always check the estimated time before starting.

---

## DeScribe Parameters for 10x + IP-Q

Before loading the job, confirm it was sliced with the correct 10x parameters:

| Parameter | Starting Value |
|---|---|
| Slice distance | 2–5 um |
| Hatch distance | 1–2 um |
| Laser power | 30–50% |
| Scan speed | 100,000–200,000 um/s (galvo) |
| Scan mode | Galvo |
| Strategy | Shell + Scaffold |

---

## Procedure

Follow the pre-print checklist and procedure in [Workflow A / step_09_run_print_job.md](../Workflow_A_63x_DiLL_IP_Dip2/step_09_run_print_job.md).

10x specific notes:
- Interface detection uses the drop bottom (curved IP-Q surface) as the primary interface — the system detects the bottom of the domed resist drop, then calculates the substrate position based on the drop geometry
- The structure footprint may extend over a large area; confirm the print origin is centered on the resist drop
- For structures spanning multiple stitched fields, review the stitching coordinates in the GWL job file before starting

---

## Related Files

- [step_06_development.md](./step_06_development.md)
- [06_Software_Workflow/NanoWrite_Software/loading_gwl_job.md](../../06_Software_Workflow/NanoWrite_Software/loading_gwl_job.md)
