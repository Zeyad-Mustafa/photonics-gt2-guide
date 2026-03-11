# SPS Safe State Error

> NanoWrite shows a "SPS Safe State" error, the green Process indicator light on the front of the machine is not lit, or the machine refuses to start a print job. The laser is blocked.

---

## What the SPS Is

The Safety Precedence Sequence (SPS) is the hardware safety interlock system that controls laser access. Before the GT2 allows any laser operation — including the low-power approach scan and printing — all SPS conditions must be satisfied simultaneously. If any condition is not met, the system enters "Safe State," which means the laser shutter is closed and the system refuses to proceed.

This is a deliberate design: a fault in any single safety component brings the entire laser system to a safe, non-operational state.

---

## SPS Conditions (All Must Be True to Exit Safe State)

| Condition | Physical component |
|---|---|
| Safety enclosure hatch is closed and latched | Hatch with magnetic sensor |
| SPS key switch is in the "ON" position | Key switch on the SPS unit |
| Emergency stop button is not depressed | Red E-stop button on the SPS unit |
| NanoWrite has initialized and is in the correct state | Software interlock |
| Laser interlock connector is seated | Physical connector at the rear of the machine |

All five must be satisfied simultaneously. The SPS Safe State error means at least one is not.

---

## Diagnosis and Fix by Cause

### Cause 1 — Hatch not fully closed

The top hatch of the GT2 has a magnetic contact sensor. If the hatch is not fully closed and latched, the sensor reads "open" and the SPS enters Safe State.

**Fix:** Open the hatch completely, then close it firmly. Push down on the front edge to ensure the magnetic contact is fully engaged. Listen for the click of the latch. Check the AxioVision status bar or SPS indicator — it should show "Hatch: Closed."

This is the most common cause of the SPS Safe State error during normal operation.

---

### Cause 2 — E-stop is depressed

If the red Emergency Stop button on the SPS unit was pressed (deliberately or accidentally), it locks in the depressed position and the system enters Safe State.

**Fix:** Twist the E-stop button clockwise until it releases and pops out. The button is a twist-to-release type — pushing it again does not release it. After releasing, the SPS should exit Safe State if all other conditions are met.

---

### Cause 3 — SPS key switch not in ON position

The key switch on the SPS unit must be in the "ON" (vertical) position. If it has been turned to "OFF" (horizontal) or removed, the system is in Safe State.

**Fix:** Insert the key (if removed) and turn to the vertical ON position.

---

### Cause 4 — NanoWrite software not ready

If NanoWrite was just started, it takes approximately 30–60 seconds to initialize communication with the hardware. During this time, the software interlock is not satisfied and the SPS is in Safe State.

**Fix:** Wait for NanoWrite to fully initialize. The status bar should show hardware connection confirmed. Do not attempt to start a print during initialization.

If NanoWrite crashed and was restarted, the hardware may need to be power-cycled. Follow the full startup procedure in [06_Software_Workflow/NanoWrite_Software/startup_procedure.md](../06_Software_Workflow/NanoWrite_Software/startup_procedure.md).

---

### Cause 5 — Laser interlock connector is unseated

The GT2 has a physical interlock connector at the rear or side of the machine that must be plugged in for the laser to operate. This connector is occasionally disturbed when the machine is moved or serviced.

**Fix:** Inspect the rear of the machine (power off first if accessing the back panel). Verify all connectors are fully seated. If you see a connector that appears loose or disconnected, do not force it — note its position and contact your facility supervisor or Nanoscribe service.

---

## The Green Process Light

The green "Process" indicator light on the front panel of the SPS unit shows the SPS status:

| Light state | Meaning |
|---|---|
| Solid green | All SPS conditions met; laser operations permitted |
| Off | SPS in Safe State; at least one condition not met |
| Flashing green | Transitional state during initialization |

Do not attempt to start a print if the Process light is off.

---

## After Resolving Safe State

After fixing the underlying condition:

1. Verify the green Process light is solid green.
2. Confirm NanoWrite status bar shows all hardware components ready.
3. If you had to restart NanoWrite or power-cycle the machine, repeat the full startup procedure including laser warm-up.
4. Do not skip the 45-minute warm-up even if the SPS issue was brief — the laser stability clock resets on power cycle.

---

## When to Contact Facility Staff

Contact your facility supervisor or Nanoscribe service if:

- You cannot identify which SPS condition is not met after checking all five
- The green Process light flashes repeatedly without resolving
- The E-stop released but the SPS does not exit Safe State
- You suspect a hardware interlock failure (connector, sensor malfunction)

Do not attempt to bypass or defeat any SPS interlock. The SPS exists to prevent Class IV laser exposure. Bypassing it is a serious safety violation.

---

## Related Files

- [02_Machine_Components/safety_enclosure_and_sps.md](../02_Machine_Components/safety_enclosure_and_sps.md)
- [12_Safety/sps_safety_system.md](../12_Safety/sps_safety_system.md)
- [06_Software_Workflow/NanoWrite_Software/startup_procedure.md](../06_Software_Workflow/NanoWrite_Software/startup_procedure.md)
