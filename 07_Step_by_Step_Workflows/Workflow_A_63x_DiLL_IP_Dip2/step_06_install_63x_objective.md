# Step 6 — Install the 63x Objective

> The 63x objective is the most sensitive and most expensive component in the GT2 system. Its installation requires a fiber ring (not a silicone ring), and the procedure must be followed exactly to avoid damaging the objective or the machine.

---

## Why This Step Matters

The 63x is an oil-immersion objective with NA 1.4. It is designed to be used with the objective tip submerged in the IP-Dip2 resist (DiLL mode) or with a thin film of immersion oil between the tip and the substrate (oil immersion mode, for through-glass printing). The key mechanical difference from the 25x is that the 63x uses a **fiber ring** to seal the objective mounting threads — not the silicone O-ring used by other objectives. Using the wrong ring, or no ring, will cause resist to wick into the objective housing and permanently contaminate it.

---

## The Fiber Ring

The fiber ring is a thin loop of soft fiber (not rubber, not silicone) that sits at the base of the objective threads when the objective is screwed into the turret. It provides a seal against capillary wicking of the low-viscosity IP-Dip2 upward along the threads.

Every time you mount the 63x, verify the fiber ring is present before installation. If it is missing or damaged, do not install the objective until a replacement is available.

---

## Procedure

1. In NanoWrite, go to the objective control panel and select the empty or placeholder position where you will install the 63x. The system will rotate the turret to that position.
2. Use the Exchange Holder dialog to put the stage in a safe retract position before accessing the turret.
3. Open the top hatch of the GT2.
4. Locate the 63x objective in its storage case. Handle it by the barrel only — never touch the front lens element.
5. Inspect the front lens element under bright light. It should be clean and free of oil, dust, and fingerprints. If it is dirty, clean it with appropriate lens tissue and optical cleaning solution before proceeding. Do not clean with regular paper tissues — they will scratch the coating.
6. Check that the **fiber ring** is seated in the thread groove at the base of the objective.
7. Thread the objective into the turret by hand, turning clockwise. Tighten **finger-tight only**. Do not use tools. The fiber ring provides the seal; overtightening damages both the ring and the thread.
8. Close the top hatch.
9. In NanoWrite, select the 63x in the objective dropdown. The system will register that this objective is now active.
10. In NanoWrite, verify the working distance setting matches the 63x (360 um). An incorrect working distance setting can cause the stage to crash.

---

## After Each Print — Cleaning the Objective

After any print using IP-Dip2, the objective tip will be coated in resist. Clean it immediately after the print (before the resist has a chance to partially cure from ambient light).

Cleaning procedure:
1. In NanoWrite, retract the stage fully using the Exchange Holder dialog before removing the sample.
2. Using a clean lens tissue (not a swab — swabs can scratch), apply a small amount of PGMEA to the tissue.
3. Gently wipe the objective front element with one stroke. Do not scrub.
4. Follow immediately with a fresh tissue dampened with IPA.
5. Inspect under a bright light. Repeat if any residue remains.
6. Never leave dried resist on the objective. Dried IP-Dip2 is difficult to remove without risking damage.

---

## What Can Go Wrong

| Problem | Cause | Fix |
|---|---|---|
| Resist wicks up into objective housing | Fiber ring missing or damaged | Remove objective; replace fiber ring; reinstall |
| Objective not recognized by NanoWrite | Wrong objective selected in dropdown | Set to 63x in NanoWrite objective panel |
| Front lens element is fogged | Fingerprint or oil contamination | Clean with lens tissue + PGMEA then IPA |
| Objective is difficult to thread | Turret thread is cross-threaded | Back out completely; re-engage straight; finger-tight only |
| Working distance error on approach | Working distance value set incorrectly | Verify 360 um in NanoWrite; reset if needed |

---

## Related Files

- [step_07_load_sample_holder.md](./step_07_load_sample_holder.md)
- [03_Objectives/63x_objective/overview.md](../../03_Objectives/63x_objective/overview.md)
- [03_Objectives/63x_objective/fiber_ring_installation.md](../../03_Objectives/63x_objective/fiber_ring_installation.md)
- [03_Objectives/63x_objective/installation_steps.md](../../03_Objectives/63x_objective/installation_steps.md)
- [11_Troubleshooting/objective_crashing.md](../../11_Troubleshooting/objective_crashing.md)
