# SPS Safety System

> The Safety Precedence Sequence (SPS) is the GT2's hardware interlock system. Understanding what it does — and what it cannot do — is essential for operating the system safely and for diagnosing SPS-related errors without being tempted to bypass it.

---

## What the SPS Is

The SPS is a dedicated hardware safety controller that monitors a set of physical conditions and manages the laser shutter and motion system power based on those conditions. It is separate from the NanoWrite software — it operates at the hardware level and cannot be overridden by software commands during normal operation.

The SPS serves two functions:

1. **Prevent the laser from operating when the enclosure is not safely closed** — protecting operators and bystanders from beam exposure
2. **Provide a clear visual and software indicator of system readiness** — the green "Process" light confirms all safety conditions are met

---

## Conditions Monitored by the SPS

The SPS continuously monitors:

| Condition | Sensor Type | Safe State If... |
|---|---|---|
| Enclosure hatch position | Magnetic or optical interlock switch | Hatch not fully closed |
| Emergency stop (E-stop) status | Hardwired normally-closed contact | E-stop button pressed |
| Key switch position | Key-operated electrical contact | Key not in ON position |
| Laser power supply status | Electrical signal from laser controller | Laser not ready |
| (Facility-specific) door interlock | If installed by facility | Door not closed |

All conditions must be simultaneously satisfied for the SPS to allow the laser shutter to open and the system to enter the printing-ready state (green Process light).

---

## SPS States

```
All conditions met:
  Green "Process" light ON
  Laser shutter: CAN be opened by NanoWrite
  Motion systems: Powered and available
  Status: READY TO PRINT

Any condition not met:
  Green light OFF
  Laser shutter: CLOSED (hardware-forced)
  Motion systems: May be limited
  Status: SAFE STATE
```

The transition from Safe State to ready occurs automatically when all conditions are re-satisfied. There is no "reset" button required for normal Safe State recovery — closing the hatch or releasing the E-stop (and re-completing the startup sequence) restores the system to ready.

---

## What the SPS Protects Against

**Direct beam exposure during normal operation.** The hatch interlock ensures the laser cannot operate at full power with the enclosure open. This is the primary protection for operators.

**Accidental laser activation.** The key switch prevents the system from being activated by unauthorized personnel or inadvertent software commands when the key is removed.

**Emergency shutdown.** The E-stop provides a single, clearly located control to immediately de-energize motion systems and close the laser shutter in an emergency.

---

## What the SPS Cannot Protect Against

Understanding the limits of the SPS is as important as understanding what it does.

**Bypass by trained service personnel.** The SPS can be put into service mode that allows the laser to operate with the hatch open. This is necessary for optical alignment. Service mode is only accessible to trained technicians, but it demonstrates that the hardware interlock is not physically undefeatable.

**Sub-threshold beam exposure during interface detection.** During sample approach, the laser operates at sub-threshold power for interface detection. The shutter is open at low power even before the print begins. The enclosure hatch should remain closed throughout this phase.

**Chemicals and mechanical hazards.** The SPS addresses laser safety only. It provides no protection against chemical exposure, objective crashes, or other mechanical hazards.

**Software faults in NanoWrite.** If NanoWrite has a software error that causes an unexpected stage movement or laser command, the SPS will only intervene if the result causes an SPS-monitored condition to be violated (e.g., if the stage physically opens the hatch). Software errors that keep the beam inside the enclosure are not caught by the SPS.

**User decisions outside the interlock scope.** The SPS cannot prevent an operator from opening the hatch after the laser shutter is confirmed closed, working without gloves, or making other unsafe choices outside the interlock's scope.

---

## The E-Stop: When and How to Use It

The E-stop (emergency stop) is a red mushroom-head pushbutton located on the GT2 enclosure or control panel. Pressing it immediately:
- Cuts power to all motion systems (piezo stage, galvo mirrors, XY motor stage)
- Forces the laser shutter closed via the SPS Safe State

**Use the E-stop when:**
- Any unexpected motion occurs and the system does not respond to software stop
- You hear a mechanical impact (objective crash)
- There is a fire, chemical spill, or other emergency requiring immediate system shutdown
- The hatch opens unexpectedly during operation

**Do not use the E-stop as a routine stop control.** Use the NanoWrite stop or pause functions for routine print interruption. The E-stop cuts motion power abruptly; repeated E-stop use is harder on the motion systems than using the software stop.

**After using the E-stop:**
1. Identify and resolve the condition that required the E-stop.
2. Twist the E-stop button clockwise to release it.
3. Restart the SPS startup sequence (key switch, hatch check, NanoWrite acknowledgment).
4. Do not resume printing without verifying the cause of the emergency and confirming no damage has occurred.

---

## SPS Indicator Light Reference

| Light State | Meaning |
|---|---|
| Green steady ON | All SPS conditions met; system ready to print |
| Green OFF, no other light | Safe State — one or more conditions not met |
| Red steady | Active fault — E-stop engaged or hardware fault detected |
| Amber / yellow | Transitional state or laser warming up |
| Flashing (any color) | Refer to your facility's specific SOP — flashing states vary by GT2 configuration |

---

## Relationship to NanoWrite Software

NanoWrite queries the SPS status before allowing print jobs to start. If the SPS is in Safe State, NanoWrite will display an error and will not start a job. NanoWrite cannot override the SPS hardware — it can only read its status and respond.

During a print, if the SPS transitions to Safe State (for example, if someone opens the hatch), NanoWrite will receive the state change, abort the current job, and log the interruption. The print cannot be resumed from mid-job after a Safe State interruption.

---

## Related Files

- [laser_safety_overview.md](./laser_safety_overview.md)
- [emergency_procedures.md](./emergency_procedures.md)
- [11_Troubleshooting/sps_safe_state_error.md](../11_Troubleshooting/sps_safe_state_error.md)
- [02_Machine_Components/safety_enclosure_and_sps.md](../02_Machine_Components/safety_enclosure_and_sps.md)
- [06_Software_Workflow/NanoWrite_Software/startup_procedure.md](../06_Software_Workflow/NanoWrite_Software/startup_procedure.md)
