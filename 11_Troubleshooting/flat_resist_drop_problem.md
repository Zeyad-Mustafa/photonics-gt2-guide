# Flat Resist Drop Problem

> You applied IP-Q to the silicon wafer, loaded the sample, and interface detection fails repeatedly. The drop looks like a flat puddle rather than a dome. This is the most common first-time failure with the 10x objective.

---

## What Is Happening

IP-Q (and to a lesser extent IP-S) relies on surface tension to form a semi-spherical drop on the substrate. When the 10x objective approaches from below, it enters through the curved bottom surface of the drop. The curved resist-air interface at the bottom of the drop is what the interface detection system locates — it uses the refractive index change from air (n = 1.0) to IP-Q (n = 1.48) at this curved surface.

A flat drop has no curved bottom surface. The bottom of the drop lies flat against the substrate, with no air-resist interface at the bottom. Interface detection cannot find it — there is no detectable optical boundary at the bottom of the drop.

```
CORRECT — semi-spherical dome:        WRONG — flat puddle:

      air                                   air
  .-----------.                     .-------------------.
 /   IP-Q      \                    |      IP-Q          |
|    resist     |                   |      resist        |
 \             /                    |                    |
  '-----------'   <- curved bottom  '--------------------'  <- flat bottom
  [ substrate ]                         [ substrate ]
  [ objective ]                         [ objective ]
       |                                      |
  laser beam                            laser beam
  (detects                              (nothing to
   curved surface)                       detect here)
```

---

## Why a Drop Goes Flat

| Cause | Explanation |
|---|---|
| Too much resist applied | Excess volume overwhelms surface tension; the drop spreads out and flattens |
| Wrong substrate surface | IP-Q wets some surfaces too aggressively and spreads instead of beading |
| Substrate contamination | Organic contamination or residue lowers contact angle, causing spreading |
| Resist viscosity too low | IP-Q stored too warm becomes thinner; thin resist spreads more easily |
| Applied too fast | Dropping resist quickly from height causes spreading before surface tension establishes the dome |

---

## The Correct Drop

A correct IP-Q drop on a clean silicon surface looks like:

- Volume: 1–2 drops from the pipette (approximately 5–15 uL depending on pipette)
- Shape: visibly dome-shaped when viewed from the side — taller in the center than at the edges
- Footprint: approximately 5–8 mm diameter on a standard substrate piece
- Color: clear to very slightly amber (IP-Q is nearly colorless)

If you view the drop from the side and it looks like a thin flat disc, it is wrong.

---

## Fixes

**Fix 1 — Remove and reapply with less volume**

Remove the existing drop by wicking it away with a cleanroom swab or pipette. Apply 1 drop only from the resist bottle pipette. Observe the shape before loading.

If the drop is still flat with 1 drop, try this: tilt the substrate 45 degrees and allow the drop to bead on the surface for 5 seconds before setting it flat. This encourages the drop to form a dome rather than spreading.

**Fix 2 — Clean the substrate surface**

A flat drop almost always means the substrate surface has contamination lowering its contact angle with the resist. Repeat the full cleaning sequence:

1. Acetone > IPA > DI water > N2 blow dry
2. Apply O2 plasma at 100 W for 60–90 seconds

After plasma treatment, the contact angle with IP-Q typically increases (the surface becomes more energetically favorable for the dome shape). Wait 2–3 minutes after plasma before applying resist — fresh plasma can cause resist to spread aggressively in a different way.

**Fix 3 — Check resist temperature**

IP-Q should be stored at 4–8 degrees C and allowed to warm to room temperature before use. If the resist has been stored at room temperature for an extended period or has been warmed above 25 degrees C, its viscosity will be lower and it will spread more easily.

If the resist bottle feels warm, return it to cold storage and use a fresh aliquot after it reaches room temperature.

**Fix 4 — Use the Multi-DiLL Silicon Wafer Holder correctly**

For the 10x objective with IP-Q, the only compatible holder is the Multi-DiLL Silicon Wafer Holder. This holder has a recessed well that constrains the resist drop physically, which helps maintain the dome shape even if the drop is slightly flatter than ideal.

If you are using any other holder with IP-Q and the 10x, switch to the Multi-DiLL holder.

---

## Confirming the Drop Is Correct Before Loading

Before loading the sample into the machine, hold the substrate at eye level and look at the drop from the side. You should be able to see a clear dome shape. If it is flat, fix it before loading — it is much faster to fix outside the machine than to troubleshoot interface detection failures inside.

---

## Related Files

- [interface_not_found.md](./interface_not_found.md)
- [04_Resists_and_Materials/IP_Q/drop_casting_technique.md](../04_Resists_and_Materials/IP_Q/drop_casting_technique.md)
- [02_Machine_Components/sample_holder_types.md](../02_Machine_Components/sample_holder_types.md)
- [07_Step_by_Step_Workflows/Workflow_C_10x_Large_Scale/step_03_apply_IP_Q.md](../07_Step_by_Step_Workflows/Workflow_C_10x_Large_Scale/step_03_apply_IP_Q.md)
