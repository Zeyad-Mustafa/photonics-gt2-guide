# NanoWrite — Startup Procedure

---

## Overview

The GT2 startup sequence must be followed in a specific order. Skipping steps or changing the order can leave the laser in an unstable state, cause incorrect power readings, or trigger safety interlock errors that require a full restart.

Total startup time from power-on to print-ready: approximately 50 to 60 minutes, dominated by the 45-minute laser warm-up.

---

## Step 1 — Check the Lab Environment

Before turning on any equipment:

Confirm the vibration isolation table is active (if using an active isolation system). Passive tables require no action but confirm the GT2 is not being disturbed by nearby equipment or foot traffic.

Confirm the temperature in the room is stable. The GT2 is sensitive to temperature changes — large HVAC fluctuations during a print can cause focus drift. In labs with poor temperature control, schedule prints during stable periods.

Confirm the UV curing station is available (you will need it after printing and development).

---

## Step 2 — Power On the Electronics Cabinet

The electronics cabinet (below or beside the main GT2 enclosure) contains the laser module, piezo drivers, galvo drivers, and SPS controller.

Turn on the electronics cabinet using the main power switch on its front panel. The switch is typically a rocker or key switch. A green power indicator light will illuminate.

Wait 30 seconds for the electronics to initialize before proceeding.

---

## Step 3 — Power On the GT2 Control Computer

Turn on the GT2 control computer if it is not already running. Wait for Windows to fully boot before launching NanoWrite. Do not launch NanoWrite during Windows startup — doing so can cause initialization errors.

---

## Step 4 — Launch NanoWrite

Double-click the NanoWrite icon on the desktop. NanoWrite will open and begin its own initialization sequence. A progress dialog or status bar typically indicates initialization progress.

During initialization, NanoWrite establishes communication with all machine hardware components. If any hardware fails to respond, an error dialog will appear. Common initialization errors and their solutions are covered in the troubleshooting section.

Wait for initialization to complete fully before proceeding.

---

## Step 5 — Start Laser Warm-Up

In NanoWrite, find the Laser panel or Laser Status section. Click the laser enable button or warm-up button to activate the laser.

The laser requires 45 minutes of warm-up time before it reaches thermal and power stability. During warm-up, the laser output power and pulse characteristics drift as the fiber laser cavity thermally stabilizes. Printing before warm-up is complete produces inconsistent voxel sizes and unpredictable exposure.

The warm-up timer is displayed in NanoWrite. Use this time to:
- Prepare your substrate (clean, apply O2 plasma)
- Apply the resin drop to the substrate
- Transfer and verify your GWL files on the GT2 computer
- Review your DeScribe settings and print parameters

Do not skip or abbreviate the warm-up. This is the single most common cause of inconsistent prints among new users.

---

## Step 6 — Verify Laser Power

After the warm-up timer completes, verify the laser output power reading in NanoWrite. It should be stable and within the expected range for your system. If the power is significantly lower than expected or fluctuating, allow additional warm-up time or contact your facility manager.

---

## Step 7 — Run Pre-Print Checklist

Before loading a sample, confirm:

[ ] Laser warm-up is complete (timer shows 45 minutes or more)
[ ] Laser power reading is stable
[ ] Correct objective is installed in the turret
[ ] Correct sample holder is configured in NanoWrite
[ ] GWL files have been transferred to the GT2 computer
[ ] Substrate has been cleaned and resin has been applied
[ ] Resin drop is semi-spherical and was applied within the last 15 minutes

When all items are confirmed, proceed to exchange_holder_dialog.md to load the sample.
