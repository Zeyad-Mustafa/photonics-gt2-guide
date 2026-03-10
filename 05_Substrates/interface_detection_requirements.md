# Interface Detection Requirements

---

## What Is Interface Detection?

Before every print, the GT2 must locate the exact position of the substrate surface — the boundary between the substrate and the liquid resin sitting on top of it. This position becomes Z = 0, the reference from which all print coordinates are measured.

If the interface is not found, or found at the wrong position, the entire print is offset in Z. This means:
- If the reference is set too high: the first layers of the structure are printed in mid-resin with no adhesion to the substrate. The structure floats and washes away during development.
- If the reference is set too low: the first layers are printed below the substrate surface, into the substrate itself, which damages the objective and the substrate.

Accurate interface detection is not optional — it is the foundation of every successful print.

---

## How the Interface Finder Works

The interface finder uses a low-power detection laser (separate from the writing laser) that travels through the objective and reflects off surfaces below it. As the stage raises the substrate toward the objective, the reflected light intensity changes at each optical interface.

The transition the system is looking for is the resin-substrate boundary:

```
Objective (above)
     |
  Resin (liquid)    <-- low reflectance, laser passes through
     |
Substrate surface   <-- high reflectance, laser reflects strongly
     |
 Substrate (solid)
```

The jump in reflected light intensity as the stage crosses the substrate surface is what the software detects. The Z position where this jump occurs is recorded as Z = 0.

The intensity jump appears as interference fringes in the Interface Finder window in NanoWrite — small oscillating bands of light and dark that appear and then stabilize as the substrate surface is found. When you see these fringes clearly and they stabilize, interface detection has succeeded.

---

## The Delta-n Requirement

The intensity jump at the substrate surface is proportional to the difference in refractive index (delta-n) between the resin and the substrate. The minimum delta-n required for reliable automatic detection is 0.04.

Below delta-n of 0.04:
- The reflected intensity change is too small for the software to distinguish from noise
- The interface finder may report no interface found
- Or worse, it may lock onto a spurious reflection (a dust particle, a scratch, a bubble in the resin) and define an incorrect Z = 0

Delta-n above 0.1 gives robust, fast, highly reliable detection.
Delta-n between 0.04 and 0.1 gives acceptable detection but requires careful resin drop geometry.
Delta-n below 0.04 gives unreliable detection and should be avoided.

---

## The Resin Drop Geometry Effect

Even with adequate delta-n, the shape of the resin drop on the substrate surface affects interface detection reliability.

A semi-spherical drop is required. Here is why:

When the objective approaches a semi-spherical drop, it enters the drop gradually from the curved top. The resin-air interface at the top of the drop gives a preliminary reflection that the software uses to estimate where the substrate surface is, and to begin the fine search.

When the drop is flat (spread out into a thin puddle), there is no curved top — the objective enters the drop abruptly from the flat edge. The software has less warning and may miss the substrate interface or lock onto the wrong position.

To ensure a semi-spherical drop:
- Allow resin to reach room temperature before applying (cold resin is more viscous and flattens more slowly, but warm resin forms better drops)
- Apply only 1 to 2 drops — do not over-apply
- Do not let the drop sit for more than 15 to 20 minutes before printing — it spreads and flattens over time
- If the substrate was treated with O2 plasma, the surface is highly wettable. The drop will spread wider and flatter than on untreated surfaces. In this case, apply the resin immediately after plasma treatment and proceed quickly, or reduce plasma treatment time.

---

## What the Interface Finder Display Shows

In NanoWrite, the Interface Finder panel shows a live graph of reflected light intensity vs Z position as the stage moves up.

What you are looking for:
- A rising baseline as the objective approaches the resin surface
- A series of oscillating fringes as the objective enters the resin
- A sharp increase in reflected intensity as the substrate surface is reached
- Stabilization of the fringes — this is the found interface position

If the graph shows:
- No features at all: the objective has not yet reached the resin. Check that resin was applied and the stage is moving in the correct direction.
- Fringes but no sharp peak: the objective is traveling through resin but has not yet reached the substrate. Either the resin drop is very thick or the substrate delta-n is too low.
- Multiple sharp peaks: there may be a particle or bubble in the resin, or the substrate has a coating that creates multiple interfaces. The software typically locks onto the strongest peak — confirm visually.
- A sharp peak followed by no further features: correct — the substrate has been found. The software locks Z = 0 here.

---

## Failure Modes and Solutions

Failure mode 1 — Interface not found, no fringes visible
Cause: Objective did not reach the resin, or resin was not applied.
Solution: Confirm resin was applied. Check that the stage is approaching from the correct direction. Verify the correct objective is installed.

Failure mode 2 — Interface not found, fringes visible but no sharp peak
Cause: Delta-n is too low. The substrate and resin have nearly identical refractive indices.
Solution: Change substrate material (use silicon for maximum delta-n). If substrate cannot be changed, add a thin reflective coating (5 to 10 nm chrome or gold).

Failure mode 3 — Interface found at inconsistent Z position across sessions
Cause: Resin drop geometry varies between sessions (flat drop vs semi-spherical drop). Or the substrate is not flat.
Solution: Standardize resin application procedure. Confirm substrate flatness.

Failure mode 4 — Interface found at wrong position (print offset in Z)
Cause: Software locked onto a false interface (dust particle, bubble, substrate coating interface).
Solution: Inspect the resin drop for bubbles before printing. Clean substrate more carefully. If using a coated substrate, verify coating thickness does not create a confusing secondary interface.

Failure mode 5 — Interface finder crashes the objective into the substrate
Cause: The approach speed was too fast, or the safe approach height was set incorrectly.
Solution: Use the manual approach at low speed until close to the substrate, then switch to automatic. Never leave the machine during approach. Set appropriate soft stop limits.

---

## Manual Interface Finding

For cases where automatic interface finding consistently fails (for example, oil immersion mode with the 63x, or very low delta-n substrates), the interface can be found manually:

1. In NanoWrite, switch to manual Z control.
2. Lower the objective slowly toward the substrate using the coarse stage joystick.
3. Watch the AxioVision camera feed — when the substrate surface comes into focus, you are at or near Z = 0.
4. Fine-tune by looking for the sharpest image of any surface feature (scratch, dust particle, or deliberate alignment mark).
5. Set this position as Z = 0 in NanoWrite.

Manual finding accuracy is approximately 1 to 5 um — acceptable for most structures but insufficient for prints where the first layer must be within a few hundred nm of the substrate surface.

---

Proceed to: substrate_cleaning_procedure.md
