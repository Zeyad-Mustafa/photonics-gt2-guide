# Objective Crashing

> You hear a crunching or grinding noise from inside the machine during sample approach, or you see the objective tip visibly press into the substrate. This is an objective crash.

---

## What an Objective Crash Is

An objective crash occurs when the objective front element makes hard physical contact with the substrate or sample holder, beyond what is safe for the optics. In mild cases, the crash is softened by the resist layer. In severe cases, the objective lens can crack, the front element can shatter, and the sample and holder can be damaged.

An objective crash is a serious event. Stop immediately and assess before proceeding.

---

## Immediate Response

1. **Stop all motor movement.** If the stage is still moving, click Stop in NanoWrite immediately.
2. **Do not attempt to retract the objective quickly.** A rapid retract can make damage worse if the objective is stuck in solidified resist.
3. **Trigger E-stop if necessary.** If NanoWrite is unresponsive, press the red E-stop button on the SPS unit.
4. **Inspect without touching.** Look through the access hatch at the objective tip and substrate. Do not touch anything yet.
5. **Contact your facility supervisor.** A crashed objective requires evaluation by trained staff before the machine is used again.

---

## What Causes Objective Crashes

### Cause 1 — Z = 0 set at wrong position, structure prints into substrate

If interface detection found the wrong surface (e.g., a bubble, the wrong side of the substrate, or a spurious reflection), Z = 0 is set at the wrong height. The GWL file contains Z coordinates referenced from this false Z = 0, and the print job commands the objective to move to a Z position that is physically inside the substrate.

The crash happens when the stage executes a Z command that drives the objective into the substrate.

**Prevention:** Always verify Z = 0 after interface detection by checking the interference fringes in AxioVision. Confirm the substrate surface is where you expect it to be before starting the print job.

---

### Cause 2 — Wrong sample holder loaded

Each objective has a compatible holder. If the wrong holder is loaded — for example, the Universal Holder used with the 10x instead of the Multi-DiLL Silicon Wafer Holder — the substrate sits at the wrong height. The stage approach routine may drive the objective into the substrate before the approach algorithm detects it.

**Prevention:** Always verify the correct holder is selected in NanoWrite before starting approach. Use the Exchange Holder dialog every time a holder is changed.

---

### Cause 3 — Manual Z control used without caution

During manual stage control (moving Z by joystick or keyboard input), it is possible to drive the stage upward faster than the operator can react. As the substrate approaches the objective from below, the operator may not stop in time.

**Prevention:** When using manual Z control near the substrate, use the smallest step size available (typically 0.1 um). Never use fast joystick input when the objective is close to the substrate surface.

---

### Cause 4 — GWL file contains out-of-range Z coordinates

A malformed GWL file with extreme negative Z values (far below the substrate surface) can command the stage to move the substrate upward until it contacts the objective.

**Prevention:** Preview the GWL bounding box in NanoWrite before starting. Confirm Z extents are within the expected range (Z = 0 to the structure height, with no large negative Z values).

---

## After a Crash — Assessment

Do not resume printing until the following have been checked:

**1. Inspect the objective front element**

Look at the objective tip under good lighting. Look for:
- Cracks in the front lens element
- Chipping at the edge of the front element
- Dried resist embedded in the lens
- Misalignment of the front element (it should be centered)

A cracked or chipped objective must be replaced before use. Contact your facility supervisor.

**2. Clean the objective if only resist contamination is present**

If the crash was mild (objective contacted soft resist but no hard impact with the substrate), the objective may only be contaminated with resist. Clean gently with PGMEA on a lens tissue, followed by IPA. Do not use abrasive cleaners.

**3. Inspect the sample holder**

Check that the holder is not bent, cracked, or displaced. A damaged holder will not seat correctly for future prints.

**4. Check the piezo stage**

A hard crash can damage the piezo stage if the force is transmitted through the stage. If Z movement after a crash produces unusual noise, resistance, or non-linear behavior, the stage may need service.

---

## Reporting

Every objective crash must be reported to the facility supervisor, even if no visible damage is found. Some damage (micro-cracks in the lens, partial delamination of optical coatings) is not visible under casual inspection but degrades print quality. The supervisor may choose to perform a formal optical inspection before returning the machine to service.

---

## Prevention Summary

| Preventive action | When to do it |
|---|---|
| Verify correct holder is loaded | Before every sample load |
| Verify Z = 0 with interference fringes | After every interface detection |
| Preview GWL bounding box in NanoWrite | Before every print job |
| Use minimum Z step during manual approach | Whenever manually controlling Z |
| Never bypass E-stop or SPS interlocks | Always |

---

## Related Files

- [interface_not_found.md](./interface_not_found.md)
- [sps_safe_state_error.md](./sps_safe_state_error.md)
- [02_Machine_Components/sample_holder_types.md](../02_Machine_Components/sample_holder_types.md)
- [12_Safety/emergency_procedures.md](../12_Safety/emergency_procedures.md)
- [06_Software_Workflow/NanoWrite_Software/sample_approach.md](../06_Software_Workflow/NanoWrite_Software/sample_approach.md)
