# DeScribe — Slicing Parameters

---

## Overview

Slicing parameters are the settings that control how DeScribe converts your 3D model into laser toolpaths. They determine resolution, print speed, structural density, and surface quality. Getting these right is the difference between a successful print and a failed one.

There are four primary parameters: slice distance, hatch distance, laser power, and scan speed. They interact with each other and with your choice of objective and resin.

---

## Slice Distance

Slice distance is the vertical spacing between consecutive layers of the print, measured in micrometers. It determines how finely the model is divided in the Z direction.

A smaller slice distance means:
- More layers for the same structure height
- Smoother vertical surfaces (smaller stairstepping)
- Higher print quality
- Longer print time (more layers to write)

A larger slice distance means:
- Fewer layers
- Faster print time
- More visible stairstepping on vertical surfaces
- Risk of gaps between layers if the slice distance exceeds the axial voxel size

The slice distance must always be smaller than the axial voxel size of your objective. If the slice distance is larger than the axial voxel, consecutive layers will not overlap, leaving gaps in the structure.

Recommended slice distances:

| Objective | Axial voxel size | Recommended slice distance |
|---|---|---|
| 63x | ~500 nm | 0.3 to 0.5 um |
| 25x | ~1.5 um | 0.5 to 1.0 um |
| 10x | ~12 um | 1.0 to 5.0 um |

For the 10x objective, the large axial voxel gives significant flexibility. A slice distance of 3 um (well below the 12 um voxel) still produces good layer bonding and is much faster than using 1 um slices.

---

## Hatch Distance

Hatch distance is the lateral spacing between adjacent scan lines within each layer, measured in micrometers. It determines how densely the interior of each layer is filled.

A smaller hatch distance means:
- More scan lines per layer
- Denser, more uniform fill
- Better mechanical strength
- Longer print time

A larger hatch distance means:
- Fewer scan lines
- Faster print time
- Risk of gaps between scan lines if hatch distance exceeds lateral voxel diameter

Like slice distance, the hatch distance must be smaller than the lateral voxel size of your objective. If it exceeds the voxel diameter, scan lines do not overlap and the structure is porous or fails completely.

Recommended hatch distances:

| Objective | Lateral voxel size | Recommended hatch distance |
|---|---|---|
| 63x | ~160 nm | 0.2 to 0.4 um |
| 25x | ~400 nm | 0.3 to 0.5 um |
| 10x | ~1.6 um | 0.8 to 2.0 um |

---

## Laser Power

Laser power sets the average output power of the writing laser, expressed as a percentage of the maximum output. Higher power delivers more energy to each voxel, increasing the size of the polymerized zone and the degree of crosslinking.

Laser power and voxel size are directly related: higher power produces larger voxels. This means:
- Too low: voxels are below the polymerization threshold — structure does not form
- Correct: voxels form at the expected size — structure prints correctly
- Too high: voxels are larger than expected — features merge, fine detail is lost, blooming occurs

Because voxel size depends on power, laser power is also one of the main tools for tuning feature sizes. For sub-diffraction-limit features (using the 63x), lowering power so only the very center of the focal volume exceeds threshold can produce features significantly smaller than the nominal voxel size.

Starting ranges by objective and resin:

| Objective and resin | Typical starting power |
|---|---|
| 63x + IP-Dip2 | 15 to 30 percent |
| 25x + IP-S | 20 to 40 percent |
| 25x + IP-Visio | 25 to 45 percent |
| 10x + IP-Q | 35 to 60 percent |

These are starting ranges only. Actual optimal power depends on the specific resin lot, the age of the resin, laser alignment, and your structure geometry. Always run a calibration print (power sweep) when starting a new project or using a new resin bottle.

---

## Scan Speed

Scan speed is the velocity at which the focal point moves through the resin during writing, in micrometers per second. Higher scan speed means less time spent at each position, therefore less cumulative exposure per voxel.

Scan speed and laser power have equivalent effects on exposure: halving the scan speed is approximately equivalent to doubling the laser power in terms of total energy delivered per unit length. In practice, scan speed is used to fine-tune exposure after laser power has been set to a reasonable starting point.

Higher scan speed:
- Shorter print time
- Less exposure per voxel (smaller effective voxel, lower crosslink density)
- Risk of underexposure if too fast

Lower scan speed:
- Longer print time
- More exposure per voxel (larger effective voxel, higher crosslink density)
- Risk of overexposure and blooming if too slow

Typical scan speeds:

| Objective | Typical range |
|---|---|
| 63x | 10,000 to 25,000 um/s |
| 25x | 25,000 to 75,000 um/s |
| 10x | 50,000 to 150,000 um/s |

The 10x objective is run at higher speeds because its larger voxels provide more process margin — it is harder to underexpose or overexpose, and higher speeds are needed to keep print times practical for large structures.

---

## How Parameters Interact

Slice distance and hatch distance determine print time through the total number of scan lines. Scan speed determines how long each line takes. Laser power determines whether each line polymerizes correctly.

A common optimization workflow:

Step 1 — Set slice and hatch distances based on required quality and your objective.
Step 2 — Set scan speed to the maximum that still gives adequate exposure for your power level. Start at the middle of the recommended range.
Step 3 — Set laser power to the middle of the recommended starting range.
Step 4 — Run a calibration test print: print a simple structure (a 20x20x10 um box) and inspect. Adjust power up or down based on results.
Step 5 — Once power is calibrated, if print time needs to be reduced, increase scan speed and increase power proportionally to maintain the same exposure.

---

## Checking Print Time Before Committing

After setting all parameters and clicking Slice, DeScribe calculates and displays the estimated print time. Always check this before generating the GWL files and transferring to the GT2.

Print times that are unacceptably long can be reduced by:
- Increasing slice distance (fewer layers)
- Increasing hatch distance (fewer scan lines per layer)
- Increasing scan speed (faster lines)
- Switching to a larger objective (larger voxels, fewer lines needed)
- Using shell and scaffold mode instead of solid fill (see hatching_strategies.md)

A useful rule of thumb: if the print time exceeds the time you have reserved on the machine, adjust parameters before transferring the job. It is much easier to adjust in DeScribe than to abort a running print partway through.

---

Proceed to: hatching_strategies.md
