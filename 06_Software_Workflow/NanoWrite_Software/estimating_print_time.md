# NanoWrite — Estimating Print Time

---

## Where to Find the Print Time

The estimated print time is displayed in two places:

In DeScribe: after compilation (pressing F5), the time estimate appears in the information panel. Check this before generating the GWL files and before reserving machine time.

In NanoWrite: after loading the job file, the time estimate is shown in the job summary dialog before you click Start. This is the same value as DeScribe showed — it is pre-calculated, not computed by NanoWrite.

---

## How Accurate Is the Estimate

The DeScribe and NanoWrite print time estimate is generally accurate to within 5 to 15 percent for straightforward structures. It can deviate more for:

- Structures with highly variable cross-sectional area per layer (varies a lot between layers)
- Jobs with many StageGoTo moves between structures (stage movement time is not always accurately estimated)
- Very long jobs where small timing errors accumulate

As a practical rule: add 15 percent to the estimated time when planning your session.

---

## What Affects Print Time

The following parameters increase print time:

- Smaller slice distance (more layers)
- Smaller hatch distance (more scan lines per layer)
- Lower scan speed (more time per line)
- Larger model volume (more total material to write)
- Solid fill instead of shell and scaffold

The following parameters decrease print time without changing structure quality significantly:

- Switching to shell and scaffold mode (60 to 90 percent reduction for large structures)
- Increasing scan speed and proportionally increasing laser power
- Increasing slice distance (if vertical surface quality is not critical)
- Using a larger objective with larger voxels (fewer lines needed for the same volume)

---

## Planning Your Session

When reserving machine time, calculate:

Total session time = laser warm-up (45 min) + substrate preparation (15 to 30 min) + sample loading and approach (10 to 15 min) + print time (from DeScribe estimate + 15 percent buffer) + development and UV cure (30 to 45 min)

A session printing a 30-minute structure therefore requires approximately 2 to 2.5 hours total.

Build in extra time for troubleshooting. Your first session with a new design almost always takes longer than expected.
