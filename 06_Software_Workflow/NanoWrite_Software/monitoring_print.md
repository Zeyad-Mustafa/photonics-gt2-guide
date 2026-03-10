# NanoWrite — Monitoring a Print in Progress

---

## The AxioVision Camera Feed

During printing, the AxioVision camera inside the GT2 enclosure provides a live view of the print area. This feed is displayed on the monitor connected to the GT2 computer. It is the primary tool for monitoring print progress.

What you see on the camera feed during a successful print:

- The laser focal point appears as a bright spot or glow moving across the field of view in a systematic hatching pattern
- Each completed layer appears as a slight change in the transparency or color of the resin in that region
- The structure builds up gradually — for tall structures with many layers, you can see the height increasing over time if you watch the camera carefully

---

## Signs of a Successful Print in Progress

- The laser spot moves in regular, evenly spaced parallel lines within each layer (the hatch pattern)
- Movement is consistent and continuous — no long pauses in unusual positions
- The NanoWrite progress indicator (layer counter, percentage complete, or time remaining) is advancing steadily
- No error dialogs or warning popups appear

---

## Signs of a Problem

Problem sign 1 — Laser spot not visible
If the camera feed shows no glow or laser spot even though the print is supposedly running, the laser may not be firing. This can happen if the laser power is set to zero, the SPS interlock has triggered, or the objective has lost contact with the resin. Check the laser power reading in NanoWrite and inspect the Interface Finder panel.

Problem sign 2 — Structure appears to be floating or detached
If you can see the structure has lifted off the substrate and is moving freely in the resin, adhesion has failed. Stop the print. The structure will wash away during development regardless. Investigate the cause (substrate preparation, contact area, resin age) before attempting another print.

Problem sign 3 — Bright flash or sudden intensity change
Occasional bright flashes during printing are usually harmless (resin bubbles popping or small particles). Repeated flashes in the same location may indicate a problem. Note the location and inspect after printing.

Problem sign 4 — No visible progress after several minutes
If the progress counter in NanoWrite is not advancing and the camera shows no activity, NanoWrite may have stalled. Check the NanoWrite window for error messages. If it appears completely frozen, note how far the print had progressed and consult your facility manager before taking any action.

---

## How Often to Check

For short prints (under 30 minutes): check at the start to confirm the print has begun correctly, and at the end.

For medium prints (30 minutes to 3 hours): check at the start, at the midpoint, and at the end.

For long prints (over 3 hours): check at the start, and then every 30 to 60 minutes. Long unmonitored prints risk wasting machine time if a failure occurs early that is not caught.

Do not leave the building during a long print without first confirming it is running correctly and informing a colleague of the print in progress.

---

## When the Print Completes

When the print finishes, NanoWrite displays a completion message and the stage returns to a safe position. The laser stops automatically.

Do not immediately open the enclosure. Wait for the stage to fully return to the home position and for the completion message to appear before clicking Exchange Holder to unload the sample.
