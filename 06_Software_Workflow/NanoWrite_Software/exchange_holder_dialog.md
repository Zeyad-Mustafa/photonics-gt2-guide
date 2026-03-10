# NanoWrite — Exchange Holder Dialog

---

## What the Exchange Holder Dialog Does

The Exchange Holder dialog in NanoWrite manages safe opening and closing of the GT2's top hatch. It exists because the top hatch must only be opened when the piezo stage has moved to a safe position — if the stage is at working height during approach, opening the lid could allow the sample holder to collide with the objective.

The Exchange Holder dialog handles this automatically. Never open the top hatch without going through this dialog first.

---

## Loading a Sample: Step by Step

Step 1 — In NanoWrite, click the Exchange Holder button. This is typically in the main toolbar or in the Sample menu.

Step 2 — NanoWrite moves the piezo stage to its safe loading position (fully retracted). Wait for movement to complete. A status indicator will confirm when it is safe to open.

Step 3 — Click Open in the dialog. The Open button will flash or change color to confirm it is safe. Only then open the top hatch lid.

Step 4 — Place your prepared substrate in the sample holder. Confirm orientation (resin-coated face toward objective, ITO side down for 25x, etc.). Secure the substrate with the holder clips.

Step 5 — Close the top hatch lid.

Step 6 — Click Close in the Exchange Holder dialog. NanoWrite re-activates the laser safety interlock. The green Process light will illuminate, indicating the SPS is active and the laser system is armed.

---

## Unloading a Sample

The unloading procedure is the same as loading: Exchange Holder > wait for stage to retract > Open > remove sample > close lid > Close dialog.

Never reach into the enclosure without going through the Exchange Holder dialog, even if the print has finished and the machine appears idle. The laser can fire during any stage of NanoWrite operation unless the safety sequence has been followed.

---

## If the Exchange Holder Button Is Not Responding

If the button is greyed out or not responding, NanoWrite may be in an active print state or an error state. Do not force the lid open. Check the NanoWrite status panel for error messages and resolve them before proceeding.
