# Troubleshooting — Workflow C (10x + IP-Q)

---

## Quick Diagnosis Table

| Symptom | Most Likely Cause | First Action |
|---|---|---|
| Interface not found | Flat resist drop | Remove substrate; re-clean; apply 1–2 drops dome-shaped |
| Interface found but at wrong Z | System found drop bottom not substrate | Verify: reduce approach sensitivity threshold |
| Structure has very rough surface | Hatch and slice distances too large for this feature size | Reduce slice to 2 um, hatch to 1 um |
| Structure did not adhere to silicon | Surface contamination | Re-clean with O2 plasma |
| Print time is unreasonably long | Solid fill on large volume | Switch to Shell + Scaffold; increase hatch/slice distances |
| Structure is correct but much larger than designed | IP-Q has different shrinkage than expected | Measure and calibrate; IP-Q shrinkage is ~5–10% |

---

## Problem: Flat Resist Drop

This is the most common Workflow C failure. See [04_Resists_and_Materials/IP_Q/drop_casting_technique.md](../../04_Resists_and_Materials/IP_Q/drop_casting_technique.md) and [11_Troubleshooting/flat_resist_drop_problem.md](../../11_Troubleshooting/flat_resist_drop_problem.md) for the full diagnosis tree.

Short version:
- If the drop is flat before you even load the holder: the substrate surface is contaminated. Re-clean.
- If the drop was domed but flattened after the holder was inverted: it was too small and spread under gravity. Apply a slightly larger drop.

---

## Problem: Wrong Holder Loaded

If the Universal Sample Holder is accidentally loaded instead of the Multi-DiLL holder, the 10x working distance calculation is wrong. Do not attempt to print in this configuration. Use the Exchange Holder dialog to swap to the correct holder.

---

## Related Files

- [11_Troubleshooting/flat_resist_drop_problem.md](../../11_Troubleshooting/flat_resist_drop_problem.md)
- [11_Troubleshooting/interface_not_found.md](../../11_Troubleshooting/interface_not_found.md)
- [11_Troubleshooting/print_taking_too_long.md](../../11_Troubleshooting/print_taking_too_long.md)
