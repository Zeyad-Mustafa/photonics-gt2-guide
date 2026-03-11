# Print Time Estimator

## Overview

DeScribe calculates print time automatically after slicing. This file explains the logic behind the estimate so you can predict print time before opening DeScribe, troubleshoot unexpectedly long estimates, and make informed decisions about which parameters to adjust when time is a constraint.

---

## The Basic Formula

Print time is determined by the total length of all scan lines divided by the scan speed, plus the time spent on stage and piezo moves between lines.

Total scan line length = (structure volume fraction filled) divided by (hatch distance times slice distance)

This simplifies to:

For a solid-fill structure:

Print time (approximate) = (X dimension times Y dimension times Z dimension) divided by (hatch distance times slice distance times scan speed)

Units: all dimensions in micrometers, scan speed in um/s, result in seconds.

---

## Example Calculation

Structure: 100 um x 100 um x 50 um solid box
Objective: 25x
Parameters: hatch 0.5 um, slice 0.8 um, scan speed 50,000 um/s

Total scan line length = (100 x 100 x 50) divided by (0.5 x 0.8) = 500,000 divided by 0.4 = 1,250,000 um

Print time = 1,250,000 um divided by 50,000 um/s = 25 seconds

DeScribe will report a somewhat longer time (typically 1.5 to 3 times this estimate) because the formula ignores:
- Turnaround time at the end of each scan line
- Stage movement time between layers and stitching positions
- Interface detection time at the start
- Acceleration and deceleration of the piezo at each line

For planning purposes, multiply the formula result by 2 to get a conservative estimate. Use DeScribe's actual output for final confirmation.

---

## Print Time by Structure Type

Small high-detail structures (63x, solid fill):

| Structure size | Typical print time |
|---|---|
| 10 x 10 x 10 um cube | 1 to 5 minutes |
| 50 x 50 x 20 um box | 15 to 45 minutes |
| 100 x 100 x 50 um box | 1 to 3 hours |
| 200 x 200 x 100 um box | 4 to 12 hours |

Large fast structures (10x, shell and scaffold):

| Structure size | Typical print time |
|---|---|
| 500 x 500 x 200 um box | 20 to 60 minutes |
| 1 x 1 x 0.5 mm box | 1 to 4 hours |
| 2 x 2 x 1 mm box | 4 to 16 hours |

Times are approximate and depend heavily on fill strategy and exact parameters.

---

## Parameters That Reduce Print Time

Ranked from most to least impact:

1. Switch from solid fill to shell and scaffold: reduces total scan line volume by 60 to 90 percent. Largest single reduction available.

2. Increase slice distance: halving slice distance doubles the number of layers and roughly doubles print time. Increasing slice distance from 0.5 um to 1.0 um halves print time.

3. Increase hatch distance: same effect as slice distance — doubling hatch distance halves the number of scan lines per layer.

4. Increase scan speed: directly proportional. Doubling scan speed halves print time. Increase laser power proportionally to maintain exposure.

5. Switch to a larger objective: the 10x voxel is approximately 100 times the volume of the 63x voxel. A structure that takes 10 hours on the 63x may take minutes on the 10x if resolution requirements allow it.

---

## Planning Your Machine Reservation

Total session time = warm-up + preparation + approach + print + development + UV cure

| Component | Typical time |
|---|---|
| Laser warm-up | 45 minutes (fixed) |
| Substrate preparation (clean, plasma, resin) | 15 to 30 minutes |
| Sample loading and interface detection | 10 to 15 minutes |
| Print (from DeScribe estimate) | Variable |
| Development and IPA rinse | 20 to 45 minutes |
| Nitrogen dry and UV cure | 15 to 30 minutes |
| Buffer for troubleshooting | 30 minutes minimum |

Add 15 percent to the DeScribe print time estimate as a buffer. Add 30 additional minutes for troubleshooting on any session where you are using new parameters or a new design.

A session with a 1-hour print requires approximately 3 to 3.5 hours of total machine time.
