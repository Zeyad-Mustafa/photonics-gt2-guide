# NanoWrite — Shutdown Procedure

---

## Overview

The GT2 shutdown sequence must be followed correctly to protect the laser, protect the objectives, and leave the machine in a safe state for the next user. Incorrect shutdown — particularly cutting power without parking the stage or disabling the laser first — can cause hardware errors that require facility manager intervention to resolve.

---

## Step 1 — Confirm Print Is Complete and Sample Is Removed

Before shutting down, confirm:
- The print has completed and NanoWrite shows a completion state
- The sample has been removed through the Exchange Holder dialog
- No substrate or resin is left in the sample holder
- The objective is clean (no dried resin on the lens or fiber ring)

---

## Step 2 — Disable the Laser

In NanoWrite, click the Laser Disable button (or go to Laser > Disable). Wait for the laser power reading to drop to zero. The green Process light on the machine front panel will go off when the laser is fully disabled.

Do not skip this step and jump directly to powering off the electronics cabinet. An abrupt power cut to the laser module while it is active can shorten laser lifetime.

---

## Step 3 — Park the Stage

In NanoWrite, use the stage controls to move the piezo and coarse stage to the home or park position. This is typically a single button labeled Park or Home in the stage control panel.

Parking the stage:
- Retracts the stage away from the objective, ensuring no accidental contact when the machine is next powered on
- Moves the stage to a reproducible position so the next user starts from a known state

---

## Step 4 — Close NanoWrite

After the laser is disabled and the stage is parked, close NanoWrite through File > Exit or the window close button. Allow NanoWrite to complete its shutdown sequence — it may take 10 to 30 seconds to save state and close hardware connections.

Do not force-close NanoWrite using Task Manager unless it is completely unresponsive. An improper close can leave hardware connections in an inconsistent state.

---

## Step 5 — Power Off the Electronics Cabinet

Once NanoWrite is fully closed, turn off the electronics cabinet using the main power switch. Wait 10 seconds for all internal components to discharge before proceeding.

---

## Step 6 — Shut Down the GT2 Control Computer

Shut down the GT2 control computer normally through the Windows Start menu. Do not use the power button unless the computer is unresponsive.

---

## Step 7 — Log the Session

Most GT2 facilities require users to log their sessions in a paper or electronic logbook. Record:
- Your name
- Date and time of session start and end
- Objective used
- Resin used
- Notes on any issues encountered
- Contact information if there is an ongoing problem

Logging sessions helps facility managers track machine usage, identify recurring problems, and attribute maintenance needs.

---

## If You Are the Last User of the Day

If no other users are scheduled after you:
- Confirm the UV curing station is off and the lid is closed
- Confirm the resin bottles are capped and returned to refrigerated storage
- Confirm the development solvent containers (PGMEA, IPA) are capped
- Confirm the fume hood sash is at the correct height

Leave the lab in the same condition you found it. The next user's print quality depends on the care taken by everyone who uses the facility.

---

This is the final file in Section 06 — Software Workflow.
Proceed to Section 07 — Step by Step Workflows.
