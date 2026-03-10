# NanoWrite — Sample Approach and Interface Detection

---

## Overview

Sample approach is the process of moving the substrate toward the objective until the resin drop contacts the objective lens, and then detecting the substrate surface to define Z = 0. This must be completed before every print.

---

## The Approach Sequence

Step 1 — In NanoWrite, select the correct sample holder configuration from the dropdown (ITO glass, silicon wafer, etc.). This sets the expected substrate thickness and approach parameters.

Step 2 — Click Approach Sample (or the equivalent button in your NanoWrite version). The coarse Z stage will begin lowering the sample holder toward the objective.

Step 3 — Watch the camera feed (AxioVision window) as the sample approaches. You will see the objective coming closer to the substrate from below. When the objective contacts the resin drop, you will see the liquid surface ripple slightly.

Step 4 — The Interface Finder runs automatically during approach. Watch the Interface Finder panel for interference fringes. When the fringes appear and stabilize, the substrate surface has been detected and Z = 0 has been defined.

Step 5 — The system stops automatically when Z = 0 is found. Confirm that the interface detection was successful by checking the status display. A confirmed interface detection shows the Z = 0 position and a stable fringe pattern.

---

## What Successful Detection Looks Like

In the Interface Finder panel, successful detection looks like:

- A rising signal as the objective enters the resin
- Oscillating fringes that increase in frequency as the objective approaches the substrate
- A sudden increase in signal amplitude at the substrate surface
- A lock message or confirmation indicator in the status bar

---

## If Interface Detection Fails

If the system reports that no interface was found, or if the fringes never appear:

Check 1: Confirm that resin was applied to the substrate and is between the objective and the substrate surface.

Check 2: Confirm the resin drop is semi-spherical. A flat drop is the most common cause of unreliable detection.

Check 3: Confirm the substrate material has adequate delta-n relative to the resin. If delta-n is below 0.04, detection is unreliable.

Check 4: Try running the approach again. If it fails consistently, switch to manual approach using the NanoWrite joystick controls and define Z = 0 manually by focusing on the substrate surface in the camera view.

Full failure mode analysis is in Section 05 — interface_detection_requirements.md.

---

## Manual Z = 0 Definition

If automatic detection fails and manual approach is needed:

1. Use the manual Z controls (joystick or arrow keys in NanoWrite) to move the stage slowly downward.
2. Watch the camera feed. When a surface feature on the substrate (a scratch, a particle, or an alignment mark) comes into sharp focus, you are at or very near the substrate surface.
3. Click Set Z = 0 (or the equivalent button) in NanoWrite. This defines the current Z position as the print reference.
4. Proceed to load the job file.

Manual Z = 0 accuracy is approximately 1 to 5 um. Sufficient for most structures, but not for prints where the first layer must be within a few hundred nanometers of the substrate.
