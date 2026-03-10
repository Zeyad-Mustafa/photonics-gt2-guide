# Step 7 — Load the Sample Holder

> Loading the holder correctly means the substrate printing surface faces the objective, the holder is fully seated in the stage, and the Exchange Holder dialog was used. Skipping the dialog is the primary cause of objective crashes.

---

## Why This Step Matters

The Universal Sample Holder positions the substrate at the correct height above the objective. If the holder is inserted without going through the Exchange Holder dialog, the objective may be at an unsafe Z position when the holder slides in — and the substrate will physically collide with the objective tip.

---

## Procedure

1. In NanoWrite, open the **Exchange Holder** dialog (typically under Machine > Exchange Holder or via the toolbar button).
2. Click "Move to Exchange Position." The stage will retract the objective to a safe distance.
3. Wait for the stage to finish moving. Do not open the hatch until the stage motion has stopped.
4. Open the top hatch.
5. If a holder is already loaded, slide it out by pulling it toward you along the stage rails.
6. Take your Universal Sample Holder with the substrate and resist drop already applied. Hold the holder level — do not tilt it, or the resist drop may shift or drip.
7. Verify once more that the substrate printing surface (with the resist drop) is facing **downward** (toward where the objective will be).
8. Slide the holder into the stage from the front, along the guide rails. Push firmly until the holder clicks or seats against the stop.
9. Close the top hatch.
10. In the Exchange Holder dialog, click "Done" or "Close." The system will note that a new holder has been loaded.
11. Confirm in NanoWrite that the objective selected and the holder type match (Universal Holder selected, 63x objective active).

---

## What Can Go Wrong

| Problem | Cause | Fix |
|---|---|---|
| Objective crash during holder insertion | Exchange Holder dialog not used | Always use the dialog — no exceptions |
| Holder not fully seated | Rails not engaged | Remove and re-insert, push until fully seated |
| Resist drop shifted during insertion | Holder tilted during carry | Remove holder; re-apply resist if drop moved significantly |
| NanoWrite reports wrong holder type | Not confirmed in the Exchange Holder dialog | Re-open dialog and confirm holder type |

---

## Related Files

- [step_08_find_interface.md](./step_08_find_interface.md)
- [02_Machine_Components/sample_holder_types.md](../../02_Machine_Components/sample_holder_types.md)
- [06_Software_Workflow/NanoWrite_Software/exchange_holder_dialog.md](../../06_Software_Workflow/NanoWrite_Software/exchange_holder_dialog.md)
- [11_Troubleshooting/objective_crashing.md](../../11_Troubleshooting/objective_crashing.md)
