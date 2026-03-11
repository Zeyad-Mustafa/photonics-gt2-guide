# Galvo Scan Mode

> Galvo scan mode steers the laser beam with mirrors rather than moving the sample. It is the fastest scanning configuration on the GT2 and the standard choice for the 25x and 10x objectives, where print speed matters and sub-micron positional accuracy is not required.

---

## How Galvo Scan Mode Works

In galvo scan mode, the sample and objective are stationary. Two small motorized mirrors (**galvanometer mirrors**, one for X, one for Y) in the beam path deflect the laser at high speed, steering the focal point across the scan field without any mechanical stage movement.

```
Laser beam enters galvo scanner:

                     [Galvo mirror Y]
                           |
[Laser] --> [Galvo mirror X] --> [Scan lens] --> [Objective] --> [Focal point in resist]
                |
           rotates to deflect
           beam in X

Both mirrors rotate simultaneously to steer
the beam to any X,Y position within the scan field.
```

Z movement (between layers) is handled by the piezo stage stepping the sample up or down between galvo scan layers. So galvo mode is not purely non-mechanical — the Z axis still uses the piezo. Only XY scanning within each layer uses the galvo mirrors.

---

## Key Specifications

| Parameter | Value |
|---|---|
| XY scan field | 400 x 400 um |
| Z range | ~8 mm (full motor stage travel, stepping between layers) |
| Maximum scan speed | ~100 mm/s |
| Positional accuracy (XY) | ~1–2 um within field |
| Field distortion | Slight at field edges due to scan geometry |
| Tilt correction | Not supported |

---

## Why Galvo Mode Is Faster Than Piezo

In piezo mode, the physical mass of the sample must accelerate and decelerate with each direction change. The sample has inertia. Scan speeds above ~10 mm/s introduce vibration that degrades voxel quality.

In galvo mode, the mirrors have almost no inertia — they are small, lightweight, and driven by powerful electromagnets. They can slew between positions and reverse direction in microseconds. This allows scan speeds of 100 mm/s and higher without vibration.

For a 200 x 200 x 100 um structure with 1 um slice distance and 0.5 um hatch:
- Piezo mode: approximately 4–8 hours
- Galvo mode: approximately 20–40 minutes

The speed advantage is most significant for large-area structures with many scan lines per layer.

---

## When to Use Galvo Scan Mode

Use galvo mode when:

- Your structure fits within 400 x 400 um (XY) per print field
- Z height can be any value (galvo Z uses the full motor stage range)
- Print speed is a priority
- You are using the 25x or 10x objective
- Positional accuracy of 1–2 um is sufficient for your feature sizes
- Your substrate is flat (no tilt correction needed)

Do not use galvo mode when:

- You need sub-micron positional accuracy
- Your substrate has a measurable tilt (use piezo with tilt correction instead)
- You are printing with the 63x for nanoscale features where galvo field distortion is unacceptable

---

## Field Distortion at the Scan Field Edges

The galvo scan field is nominally 400 x 400 um, but the beam is deflected by rotating mirrors, not by parallel translation. A rotating mirror introduces a slight geometric distortion — points near the center of the field are positioned more accurately than points near the edges.

This distortion is small (typically < 1 um for a 400 um field) and is partially corrected by the scan lens design. For most 25x applications with feature sizes of 2 um and above, field distortion is not detectable in the final structure.

For structures with critical dimensions at the very edges of the 400 um field, either print smaller structures (staying within the central 300 um where distortion is minimal) or switch to piezo mode.

---

## Stitching Multiple Galvo Fields

For structures larger than 400 um in X or Y, multiple galvo scan fields are stitched together using the large XY motor stage. The workflow:

1. The galvo prints the first 400 x 400 um field.
2. NanoWrite commands the XY motor stage to reposition the sample by 400 um in X or Y (using `StageGoToX` / `StageGoToY` GWL commands).
3. The galvo prints the next field.
4. Repeat until all fields are complete.

The seam between adjacent fields must be calibrated carefully. Imperfect stitching produces a visible step or gap at field boundaries. Calibrate the stitch offset using a test structure (see [06_Software_Workflow/DeScribe_Software/stagegoTo_commands.md](../06_Software_Workflow/DeScribe_Software/stagegoTo_commands.md)).

---

## Galvo Scan Mode in DeScribe

When galvo is selected as the scan mode in DeScribe, the GWL output uses galvo-specific scan commands. The scan lines within each layer are executed by the galvo mirrors; Z steps between layers are piezo commands.

In DeScribe, scan speed in galvo mode is set separately from piezo mode — higher values are appropriate and typical. Starting value for the 25x + IP-S: 50,000–100,000 um/s.

---

## Related Files

- [piezo_scan_mode.md](./piezo_scan_mode.md)
- [02_Machine_Components/galvo_vs_piezo_scanning.md](../02_Machine_Components/galvo_vs_piezo_scanning.md)
- [06_Software_Workflow/DeScribe_Software/slicing_parameters.md](../06_Software_Workflow/DeScribe_Software/slicing_parameters.md)
- [06_Software_Workflow/DeScribe_Software/stagegoTo_commands.md](../06_Software_Workflow/DeScribe_Software/stagegoTo_commands.md)
- [13_Key_Parameters_Reference/scanning_speed_table.md](../13_Key_Parameters_Reference/scanning_speed_table.md)
