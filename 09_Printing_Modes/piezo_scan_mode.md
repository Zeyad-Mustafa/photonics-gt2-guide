# Piezo Scan Mode

> Piezo scan mode moves the sample rather than the beam. It is the highest-precision scanning configuration on the GT2 and the correct choice for any structure requiring sub-micron positional accuracy, nanoscale feature sizes, or tilt correction.

---

## How Piezo Scan Mode Works

In piezo scan mode, the laser beam and objective are stationary. The **piezo stage** moves the sample in X, Y, and Z so that each successive voxel position passes under the fixed focal point.

```
Laser beam: FIXED
Objective:  FIXED
Focal point: FIXED in space

Sample moves:

   initial position          after X move         after Z move
   ___________               ___________           ___________
   |  |                      |    |                |  |
   |  | <- focal point       |    | <- focal point |  |
   |__|                      |____|                |__|
    SUBSTRATE                 SUBSTRATE             SUBSTRATE
    moves left                                    moves up
```

Because the optical path never changes — the beam always travels the same route through the same optics — there is no field distortion, no beam aberration at the field edge, and no systematic positional error from beam steering. The only positional error is from the piezo stage itself, which is approximately 10 nm.

---

## Key Specifications

| Parameter | Value |
|---|---|
| X range | 300 um |
| Y range | 300 um |
| Z range | 300 um |
| Positional accuracy | ~10 nm |
| Minimum step size | ~1 nm (theoretical) |
| Maximum scan speed | ~10 mm/s (practical limit before vibration) |
| Tilt correction | Yes — supported in piezo mode only |

---

## When to Use Piezo Scan Mode

Piezo mode is the right choice when:

- Your structure fits within 300 x 300 x 300 um
- You need sub-micron positional accuracy (< 1 um feature placement)
- You are using the 63x objective for nanoscale features
- Your substrate has a tilt that requires correction
- You are printing photonic crystals, nanostructures, or any geometry where galvo field distortion would be unacceptable

Piezo mode is not the right choice when:

- Your structure exceeds 300 um in any dimension — the stage will go out of range and the print will fail
- You are printing large structures where galvo speed is needed to keep print time reasonable
- You are using the 10x objective for mm-scale printing

---

## Piezo Stage Architecture

The piezo stage uses **piezoelectric crystals** that expand or contract by a precisely controlled amount in response to an applied voltage. The crystals are arranged to provide independent motion in X, Y, and Z.

Key properties of piezoelectric actuation:
- **Sub-millisecond response time** — the stage can change direction essentially instantaneously at the scale of human perception
- **No backlash** — unlike stepper or servo motors, piezo stages have no mechanical play in the drive mechanism
- **Hysteresis** — piezo crystals exhibit slight hysteresis (the extension at a given voltage depends on the recent history of applied voltages). The GT2's closed-loop position feedback corrects for this using a capacitive sensor.
- **Temperature sensitivity** — piezo response is slightly temperature dependent. This is one reason the GT2 requires a 45-minute warm-up before printing.

---

## Piezo Scan Mode in DeScribe

When you select piezo as the scan mode in DeScribe, the generated GWL file contains X, Y, Z coordinate commands that the NanoWrite software sends to the piezo controller. The GWL syntax for piezo mode uses absolute coordinate commands within the 300 um cube.

If your structure exceeds 300 um in any dimension, DeScribe will either warn you or silently generate coordinates outside the piezo range. Always verify your structure dimensions before generating GWL, and confirm the estimated print does not exceed the range.

Structures larger than 300 um that require piezo precision can be printed using **piezo + stage stitching**: the piezo handles each 300 x 300 um field, and the large XY motor stage repositions the sample between fields. This requires careful overlap and stitching calibration.

---

## Piezo vs. Galvo — Summary

| Feature | Piezo | Galvo |
|---|---|---|
| What moves | Sample | Laser beam (mirrors) |
| Range | 300 x 300 x 300 um | 400 x 400 um (XY) |
| Accuracy | ~10 nm | ~1–2 um |
| Max speed | ~10 mm/s | ~100 mm/s |
| Field distortion | None | Slight at edges |
| Tilt correction | Yes | No |
| Best objective | 63x | 25x, 10x |
| Best for | Nanostructures, precision | Large fast prints |

---

## Related Files

- [galvo_scan_mode.md](./galvo_scan_mode.md)
- [tilt_correction_mode.md](./tilt_correction_mode.md)
- [02_Machine_Components/galvo_vs_piezo_scanning.md](../02_Machine_Components/galvo_vs_piezo_scanning.md)
- [02_Machine_Components/microscope_module.md](../02_Machine_Components/microscope_module.md)
- [13_Key_Parameters_Reference/stage_ranges_table.md](../13_Key_Parameters_Reference/stage_ranges_table.md)
