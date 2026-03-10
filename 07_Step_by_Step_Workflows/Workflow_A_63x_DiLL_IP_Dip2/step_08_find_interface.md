# Step 8 — Find the Interface

> Interface detection sets Z = 0 at the substrate surface. Every Z coordinate in your GWL file is measured from this point. If interface detection fails or finds the wrong surface, your structure will be printed in the wrong location — usually floating above or below the substrate, not attached to it.

---

## Why This Step Matters

Before printing, the GT2 must know exactly where the substrate surface is relative to the objective. This is called interface detection or "sample approach." The system scans in Z while monitoring the reflected laser intensity. When the laser crosses the substrate-resist interface (where the refractive index changes from n_resist to n_substrate), the reflected signal changes sharply. This Z position is set as Z = 0.

All Z coordinates in the GWL file are offsets from Z = 0. If Z = 0 is wrong, every layer is wrong.

---

## The Refractive Index Requirement

Interface detection relies on a detectable change in refractive index at the interface. For this workflow:

- IP-Dip2: n = 1.511
- 170 um borosilicate glass: n = 1.515
- The delta-n at this interface is approximately 0.004

This is at the very low end of reliable detection. Some operators add a thin metallic adhesion layer (e.g., Ti or Cr) or use ITO-coated substrates to improve the reflection signal. If your substrate gives unreliable interface detection, discuss with your facility supervisor.

For quartz (n = 1.458), the delta-n with IP-Dip2 (1.511) is 0.053 — much more detectable. This is one reason quartz is sometimes preferred over borosilicate for 63x work.

---

## Procedure

1. In NanoWrite, navigate to the Sample Approach panel.
2. Use the AxioVision camera (see [02_Machine_Components/camera_and_axiovision.md](../../02_Machine_Components/camera_and_axiovision.md)) to confirm the resist drop is visible in the camera field of view. The drop should appear as a clear, slightly curved region in the center of the image.
3. Use the coarse Z motor controls to bring the objective toward the substrate slowly. Watch the camera image. Stop when interference fringes (Newton's rings) appear — this indicates the objective is within a few micrometers of the surface.
4. In NanoWrite, click "Find Interface" or "Auto Approach." The system will perform an automated scan in Z and locate the intensity step that marks the interface.
5. Wait for the system to report "Interface Found" and display the detected Z position.
6. Confirm the detected interface makes physical sense: the Z value should correspond to the substrate surface, not the bottom of the resist drop or the top of the substrate.
7. If the system reports "Interface Not Found," see the troubleshooting section below and [11_Troubleshooting/interface_not_found.md](../../11_Troubleshooting/interface_not_found.md).
8. Once the interface is confirmed, do not move the sample holder or change the Z position. Any accidental movement here invalidates the interface detection and requires re-approach.

---

## What the Camera Shows During Approach

As the objective approaches the substrate from below:

- Far from surface: uniform gray image, no fringes
- Getting close: faint interference rings begin to appear
- Very close (< 10 um): bright concentric interference fringes (Newton's rings)
- At or past interface: image of substrate surface features becomes visible

The appearance of fringes is your visual confirmation that the objective is close enough for automated interface detection to succeed.

---

## What Can Go Wrong

| Problem | Cause | Fix |
|---|---|---|
| Interface not found | Delta-n too low, wrong substrate side, or resist not present | Check substrate orientation; verify resist was applied; try quartz substrate |
| Wrong interface detected | System found the bottom of resist drop instead of substrate | Manually verify Z value; repeat approach with adjusted start position |
| Fringes never appear during approach | Objective is moving toward wrong area | Check camera image; reposition XY to center of resist drop |
| Fringes appear then disappear | Objective is moving too fast | Slow the approach speed |

---

## Related Files

- [step_09_run_print_job.md](./step_09_run_print_job.md)
- [02_Machine_Components/camera_and_axiovision.md](../../02_Machine_Components/camera_and_axiovision.md)
- [05_Substrates/interface_detection_requirements.md](../../05_Substrates/interface_detection_requirements.md)
- [06_Software_Workflow/NanoWrite_Software/sample_approach.md](../../06_Software_Workflow/NanoWrite_Software/sample_approach.md)
- [11_Troubleshooting/interface_not_found.md](../../11_Troubleshooting/interface_not_found.md)
