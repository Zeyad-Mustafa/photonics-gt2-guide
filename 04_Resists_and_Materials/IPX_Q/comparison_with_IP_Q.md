# IPX-Q vs. IP-Q — Comparison

> A direct side-by-side comparison to help you decide which large-volume resist to use.

---

## Side-by-Side Comparison Table

| Property | IP-Q | IPX-Q |
|---|---|---|
| Refractive index | 1.48 | ~1.48 |
| Compatible objectives | 10x only | 10x and 25x |
| Optical clarity (cured) | Slightly yellow | Slightly amber (less yellow than IP-Q) |
| Feature resolution (10x) | ~2-5 um | ~1-3 um |
| Shrinkage | ~5-8% | ~4-7% |
| Viscosity | Low-medium | Low-medium |
| Developer | PGMEA + IPA | PGMEA + IPA |
| Drop casting rules | Same 1-2 drops rule applies | Same 1-2 drops rule applies |
| Published parameters available | Many (older, well-established) | Fewer (newer formulation) |
| Cost | Lower | Higher |

---

## When the Difference Actually Matters

The practical difference between IP-Q and IPX-Q is small for most applications. The cases where IPX-Q's improvements are meaningful:

**Clarity improvement matters when:**
- Printing optical elements (lenses, waveguide inputs) at large scale — the reduced yellowing of IPX-Q improves transmission in the visible spectrum
- Imaging through the printed structure under transmitted light — less background absorption

**Resolution improvement matters when:**
- Your design has features between ~1-2 um — IP-Q cannot reliably print these, but IPX-Q can
- You want to use the 25x objective for a fast large print while keeping finer features than IP-Q allows

**IP-Q is still preferred when:**
- Your lab has years of calibrated IP-Q data and you need reproducibility
- Cost-per-print matters
- Resolution of 2-5 um is entirely acceptable for your geometry

---

## Drop Casting Rules for IPX-Q

IPX-Q follows the same critical drop casting rules as IP-Q:
- Apply only 1-2 drops
- The drop must be semi-spherical (domed), not flat
- Use the Multi-DiLL Silicon Wafer Holder with the 10x objective

See **[IP_Q/drop_casting_technique.md](../IP_Q/drop_casting_technique.md)** — the same technique applies to IPX-Q.

---

## Parameter Calibration Note

Because IPX-Q is a newer formulation, there are fewer published parameter tables than for IP-Q. If you are switching from IP-Q to IPX-Q on an existing machine, run a new calibration array — do not assume IP-Q parameters transfer directly to IPX-Q.

---

## Related Files

- [overview.md](./overview.md)
- [IP_Q/overview.md](../IP_Q/overview.md)
- [IP_Q/drop_casting_technique.md](../IP_Q/drop_casting_technique.md)
- [resist_selection_guide.md](../resist_selection_guide.md)