# Laser Safety Overview

> The GT2 laser is invisible, silent, and permanently damaging to the eye before you can react. This is not a theoretical risk. Class IV NIR femtosecond lasers have caused permanent vision loss in research settings. The enclosure and SPS system prevent this during normal operation. Your job is to never defeat those protections.

---

## The Laser Parameters

| Parameter | Value | Relevance to Safety |
|---|---|---|
| Wavelength | 780 nm | Near-infrared — invisible to human eye |
| Pulse duration | 100 femtoseconds | Peak intensity extremely high even at low average power |
| Repetition rate | 80 MHz | 80 million pulses per second — continuous apparent exposure |
| Average power at sample | Up to ~200 mW | Class IV threshold is 500 mW CW, but pulsed NIR is dangerous well below this |
| Laser class | Class IV | Highest hazard category |

---

## Why NIR Femtosecond Lasers Are Especially Dangerous

**Invisible beam.** 780 nm is beyond the visible spectrum. You cannot see the beam, cannot see a reflection of the beam on a surface, and cannot see it entering your eye. There is no blink reflex or aversion response. By the time tissue damage has occurred, the exposure is over.

**No pain signal.** The retina has no pain receptors. Retinal damage from laser exposure is painless at the moment of injury. A person may not realize they have been injured until hours later when they notice a blind spot or loss of central vision.

**High peak intensity.** A 100 fs pulse contains the same energy as a longer pulse but compressed into a far shorter time. Peak intensity (watts per cm2) is many orders of magnitude higher than a continuous wave laser of the same average power. Femtosecond pulses can cause multiphoton ionization damage in tissue at average power levels that would not cause injury from a CW laser.

**Specular reflections.** NIR light reflects from glass, polished metal, and optical surfaces just as visible light does. A reflection from the edge of a slide or metal tweezers in the beam path can redirect the beam in an unpredictable direction. Even a diffuse scattering surface can produce hazardous levels at close range with a Class IV source.

---

## Normal Operation: Hazard Contained by the Enclosure

During normal printing, the entire optical path from the laser source to the sample is inside the GT2 enclosure. The enclosure is an interlocked light-tight box. With the hatch closed and the SPS in the active (green Process) state, the beam cannot exit the enclosure.

This means:

- No laser safety eyewear is required during normal printing with the hatch closed
- Bystanders in the room are not at risk during normal operation
- The room does not need to be a controlled laser area during enclosed operation (confirm this with your facility's laser safety officer — policies vary)

**The protection is the enclosure. The enclosure is only protective when it is closed.**

---

## When the Enclosure Is Open

The hatch must never be opened while the laser is active at printing power. The SPS hardware interlock should prevent this — opening the hatch triggers Safe State and closes the laser shutter. However:

- The SPS can be bypassed by software (for alignment and diagnostic purposes by trained technicians)
- The SPS shutter may be open even at sub-threshold power levels used for interface detection
- Scattered or reflected light during alignment procedures may exit the beam path unexpectedly

**Rule:** If you have any reason to open the enclosure hatch while the system is energized, confirm with your facility laser safety officer and your facility's SOP before doing so. This is a task for trained service personnel, not routine operators.

If you need to inspect the sample mid-print (for example, to check whether a problem has occurred), **stop the print, wait for NanoWrite to confirm the laser shutter is closed, then open the hatch.**

---

## Eye Protection Requirements

| Situation | Required Eye Protection |
|---|---|
| Normal operation, hatch closed | None required |
| Hatch open, laser off and shutter confirmed closed | Safety glasses (standard lab glasses sufficient) |
| Any open-beam work (service, alignment — facility technicians only) | OD 7+ laser safety eyewear rated for 780 nm |

If you are not a facility technician and you find yourself in a situation where you feel you need laser safety eyewear, stop. Something has gone wrong with the workflow. Do not proceed. Close the hatch, engage the E-stop if needed, and contact your facility supervisor.

---

## Beam Path Awareness

During normal operation you will never be in the beam path. However, be aware of the following:

**Fiber ring / objective tip area.** The objective tip, when loaded with resist, is the closest accessible point to the actual focal region. The sample is directly above the objective during printing. Do not reach into the open hatch area above a loaded sample while the laser is active.

**AxioVision camera port.** The camera viewing the sample is coupled via a beamsplitter in the microscope. During normal operation, the camera receives a small fraction of the returned illumination light. Do not look directly into any optical port on the microscope body without confirming the laser shutter is closed.

**Reflective surfaces near the sample.** Keep metal tools, reflective tweezers, and watch faces away from the sample area when the hatch is open and the laser status is uncertain.

---

## Posting and Access Control

The GT2 room should be posted with a laser warning sign at the door. During normal enclosed operation, door interlock is generally not required, but your facility policy may differ. During any open-beam service work, the room must be closed and posted per Class IV requirements.

---

## Related Files

- [sps_safety_system.md](./sps_safety_system.md)
- [emergency_procedures.md](./emergency_procedures.md)
- [02_Machine_Components/safety_enclosure_and_sps.md](../02_Machine_Components/safety_enclosure_and_sps.md)
- [02_Machine_Components/laser_system.md](../02_Machine_Components/laser_system.md)
