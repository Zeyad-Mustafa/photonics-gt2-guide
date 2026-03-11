# Emergency Procedures

> This file covers the immediate response to the most likely emergencies during GT2 operation. Read it before your first session. In an actual emergency, you will not have time to look this up.

---

## Emergency Contact Information

Fill in your facility-specific contacts before your first session:

| Contact | Name / Number |
|---|---|
| Facility emergency number | __________________ |
| Laser Safety Officer (LSO) | __________________ |
| Chemical Hygiene Officer (CHO) | __________________ |
| Nearest hospital / urgent care | __________________ |
| Poison Control (US: 1-800-222-1222) | 1-800-222-1222 |
| Campus/building security | __________________ |

Post these numbers at the GT2 workstation.

---

## Emergency 1: Suspected Laser Eye Exposure

**Symptoms:** Sudden visual disturbance, blind spot, blurred vision, or — with 780 nm NIR — no immediate symptom but you were in a situation where beam exposure was possible.

**Immediate actions:**

1. Do not rub your eyes.
2. Press E-stop on the GT2 immediately.
3. Tell another person in the room what happened.
4. Call your facility emergency number or go directly to urgent medical care. **Do not wait to see if symptoms develop — retinal damage from NIR lasers may not be symptomatic for hours.**
5. Bring the following information to medical personnel: wavelength (780 nm), pulse duration (100 fs), repetition rate (80 MHz), estimated average power at point of exposure if known.
6. Notify your Laser Safety Officer as soon as you are able.

**Do not:**
- Wait and observe — by the time retinal damage is symptomatic, the exposure is over and treatment options are time-sensitive
- Assume you are fine because there is no pain — the retina has no pain receptors
- Return to work on the GT2 until medically cleared

---

## Emergency 2: Chemical Splash — Eye Contact

Any chemical used in GT2 workflows (resist, PGMEA, IPA, acetone, SU-8 developer) in the eye requires immediate irrigation.

**Immediate actions:**

1. Go immediately to the nearest eyewash station. Do not stop to remove contact lenses first.
2. Activate the eyewash. Flush with water continuously for **15 minutes minimum**, holding eyelids open. Use a clock or timer — 15 minutes feels much longer than it is.
3. Remove contact lenses during flushing if you can do so without stopping the flush.
4. After flushing, seek medical attention. Bring the SDS (Safety Data Sheet) for the chemical involved.
5. Report to your Chemical Hygiene Officer.

**Location of nearest eyewash station:** __________________ (fill in before first session)

---

## Emergency 3: Chemical Splash — Skin Contact

**For IP-series resists and PGMEA:**

1. Remove contaminated gloves immediately.
2. Wash affected skin with soap and water for 15 minutes.
3. If the exposure covers a large area or irritation does not resolve within 30 minutes, seek medical attention.
4. For PGMEA skin contact over a large area, seek medical attention regardless of visible symptoms — PGMEA is a reproductive toxin and systemic absorption is a concern.

**For acetone or IPA:**

1. Wash with soap and water.
2. If irritation persists, seek medical attention.

---

## Emergency 4: Chemical Spill

**Small spill (< 10 mL, contained on bench):**

1. Alert others in the area.
2. Put on nitrile gloves and safety glasses.
3. Absorb with paper towels. For IPA or acetone, confirm there are no ignition sources before proceeding.
4. Place contaminated material in a sealed hazardous waste bag.
5. Wipe area with IPA, then discard IPA-soaked wipes in the waste bag.
6. Report PGMEA spills to your Chemical Hygiene Officer.

**Large spill (> 10 mL, floor, or any spill with vapor accumulation):**

1. Do not attempt to clean it yourself.
2. Alert everyone in the area to leave.
3. Close the door to the room.
4. Call your facility emergency number.
5. Do not re-enter until cleared.

**Fire from spilled IPA or acetone:**

1. Activate the nearest fire alarm pull station.
2. Call emergency services (911 in the US).
3. Evacuate. Do not attempt to fight the fire unless it is very small (smaller than a wastebasket), you have a clear exit behind you, and you are trained in fire extinguisher use.
4. Close doors as you leave to slow fire spread.

---

## Emergency 5: Objective Crash

A mechanical impact during the approach or printing procedure — heard as a click or felt as an unexpected resistance in the software position readout.

**Immediate actions:**

1. Press E-stop if motion is still occurring.
2. Do not attempt to manually retract the objective through the SPS or by physically moving the stage.
3. Use NanoWrite to command a controlled Z-retraction once the E-stop is released and the system is in a known state.
4. Remove the sample holder using the Exchange Holder dialog.
5. Inspect the objective front element for damage (scratches, cracks, resist contamination).
6. Do not resume use of the objective until it has been inspected and cleared.
7. Report the incident to your facility supervisor. Objective damage is a significant equipment cost and most facilities require an incident report.

---

## Emergency 6: Power Failure or System Freeze During Print

**If NanoWrite becomes unresponsive during a print:**

1. If the print was in progress, the laser shutter state is uncertain. Do not open the hatch until you have confirmed the SPS is in Safe State (green light is off or red).
2. Press E-stop to force a Safe State.
3. Wait 30 seconds.
4. Release E-stop (twist to release).
5. Restart NanoWrite.
6. The print cannot be resumed mid-job after a software crash. Assess whether the partial print is useful or whether you need to start over.

**If there is a full facility power outage:**

1. The SPS will de-energize and the laser shutter will close (fail-safe state on power loss for most configurations — confirm with your facility).
2. Do not attempt to open the hatch until power is restored and the SPS status is confirmed.
3. Any in-progress print is lost. The resist state on the substrate after a mid-print power failure is unpredictable — discard the sample.

---

## Emergency 7: Smoke or Burning Smell from the GT2

Possible causes: overheated motor driver, laser component failure, electrical fault in ancillary equipment.

**Immediate actions:**

1. Press E-stop.
2. Power off the GT2 main switch if it is safely accessible.
3. Do not open the enclosure — if there is an electrical fire inside, opening the enclosure introduces oxygen and provides an exit for smoke.
4. Activate the fire alarm if smoke is visible or smell is strong.
5. Evacuate and call facility emergency number.
6. Do not use the GT2 again until the cause has been identified and cleared by qualified service personnel.

---

## Post-Emergency Reporting

All emergencies — including near-misses where injury did not occur — should be reported to your facility's safety office. Reporting near-misses is how facilities identify hazards before they cause injury. You will not be penalized for reporting a near-miss.

Laser eye exposure and significant chemical exposures must be reported regardless of whether symptoms are present.

---

## Related Files

- [laser_safety_overview.md](./laser_safety_overview.md)
- [chemical_safety.md](./chemical_safety.md)
- [sps_safety_system.md](./sps_safety_system.md)
- [11_Troubleshooting/objective_crashing.md](../11_Troubleshooting/objective_crashing.md)
- [11_Troubleshooting/sps_safe_state_error.md](../11_Troubleshooting/sps_safe_state_error.md)
