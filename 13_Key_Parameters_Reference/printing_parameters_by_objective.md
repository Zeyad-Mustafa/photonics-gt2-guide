# Printing Parameters by Objective and Resin

All values are starting ranges for a new user or a new resin lot. Optimize by running a calibration print before committing to a critical sample. Power is expressed as percentage of maximum laser output.

---

## 63x Objective (NA 1.4, DiLL Mode)

### IP-Dip2

| Parameter | Minimum | Typical | Maximum |
|---|---|---|---|
| Laser power | 12% | 20% | 35% |
| Scan speed | 10,000 um/s | 15,000 um/s | 25,000 um/s |
| Slice distance | 0.2 um | 0.3 um | 0.5 um |
| Hatch distance | 0.15 um | 0.3 um | 0.4 um |
| Shell thickness | 0.3 um | 0.6 um | 1.0 um |

Notes:
- Start at 20% power and 15,000 um/s for first print. Adjust power in 2% increments.
- Below 12% power, structures may not fully polymerize.
- Above 35% power, feature blooming degrades fine detail.
- For sub-200 nm features, reduce power toward 12 to 15% and verify with SEM.

### IPX-Clear

| Parameter | Minimum | Typical | Maximum |
|---|---|---|---|
| Laser power | 15% | 22% | 38% |
| Scan speed | 10,000 um/s | 15,000 um/s | 25,000 um/s |
| Slice distance | 0.2 um | 0.3 um | 0.5 um |
| Hatch distance | 0.15 um | 0.3 um | 0.4 um |

Notes:
- IPX-Clear requires slightly higher power than IP-Dip2 for equivalent exposure.
- Optical clarity of IPX-Clear is superior — preferred for waveguides and optical elements.

### GP-Silica (63x, DiLL Mode)

| Parameter | Minimum | Typical | Maximum |
|---|---|---|---|
| Laser power | 25% | 35% | 50% |
| Scan speed | 5,000 um/s | 10,000 um/s | 15,000 um/s |
| Slice distance | 0.3 um | 0.5 um | 0.8 um |
| Hatch distance | 0.2 um | 0.4 um | 0.6 um |

Notes:
- GP-Silica requires higher power and lower speed than IP-Dip2 due to the silica nanoparticle loading reducing photopolymer sensitivity.
- 8-hour time limit from resin deposition to end of development. Do not exceed.
- After sintering, structures shrink approximately 25% in all dimensions. Scale up CAD model accordingly.

---

## 25x Objective (NA 0.8, DiLL Mode)

### IP-S

| Parameter | Minimum | Typical | Maximum |
|---|---|---|---|
| Laser power | 18% | 28% | 45% |
| Scan speed | 25,000 um/s | 50,000 um/s | 75,000 um/s |
| Slice distance | 0.5 um | 0.8 um | 1.5 um |
| Hatch distance | 0.3 um | 0.5 um | 0.8 um |
| Shell thickness | 0.5 um | 1.0 um | 2.0 um |

Notes:
- IP-S is the most commonly used resin. When in doubt about starting parameters, use the typical column.
- For large structures where print time is a concern, increase scan speed to 75,000 um/s and increase power to 40 to 45% proportionally.
- Adjustment ring on the 25x MUST be set to Glyc (3 longest bars) before every session.

### IP-Visio

| Parameter | Minimum | Typical | Maximum |
|---|---|---|---|
| Laser power | 22% | 32% | 48% |
| Scan speed | 20,000 um/s | 40,000 um/s | 60,000 um/s |
| Slice distance | 0.5 um | 0.8 um | 1.5 um |
| Hatch distance | 0.3 um | 0.5 um | 0.8 um |

Notes:
- IP-Visio is biocompatibility-tested. Use for all cell-contact applications.
- Requires slightly higher power than IP-S for equivalent exposure.

### IP-PDMS

| Parameter | Minimum | Typical | Maximum |
|---|---|---|---|
| Laser power | 25% | 38% | 55% |
| Scan speed | 15,000 um/s | 30,000 um/s | 50,000 um/s |
| Slice distance | 0.5 um | 1.0 um | 2.0 um |
| Hatch distance | 0.3 um | 0.6 um | 1.0 um |

Notes:
- IP-PDMS is the softest resin. Requires higher power due to different photopolymer chemistry.
- Development is longer (25 to 35 minutes). Structures are prone to collapse — use CPD for features below 5 um width.
- Surfaces may feel tacky after development if underdeveloped. Return to fresh PGMEA.

### IP-Q and IPX-Q

| Parameter | Minimum | Typical | Maximum |
|---|---|---|---|
| Laser power | 30% | 42% | 60% |
| Scan speed | 25,000 um/s | 60,000 um/s | 150,000 um/s |
| Slice distance | 1.0 um | 3.0 um | 5.0 um |
| Hatch distance | 0.8 um | 1.5 um | 3.0 um |

Notes:
- IP-Q is formulated for large-volume printing with the 10x objective but is also usable with the 25x for medium-scale structures.
- High scan speeds are achievable and recommended for large structures.

### IPX-Clear (25x)

| Parameter | Minimum | Typical | Maximum |
|---|---|---|---|
| Laser power | 18% | 28% | 42% |
| Scan speed | 20,000 um/s | 45,000 um/s | 70,000 um/s |
| Slice distance | 0.5 um | 0.8 um | 1.5 um |
| Hatch distance | 0.3 um | 0.5 um | 0.8 um |

---

## 10x Objective (NA 0.3, DiLL Mode)

### IP-Q

| Parameter | Minimum | Typical | Maximum |
|---|---|---|---|
| Laser power | 35% | 50% | 70% |
| Scan speed | 50,000 um/s | 100,000 um/s | 200,000 um/s |
| Slice distance | 1.0 um | 3.0 um | 8.0 um |
| Hatch distance | 0.8 um | 2.0 um | 5.0 um |

Notes:
- The 10x is optimized for large volume — use the largest slice and hatch distances that meet your quality requirements to minimize print time.
- For structures above 1 mm cubed, use shell and scaffold hatching mode. Solid fill at 10x can take many hours.
- IPX-Q is an extended version of IP-Q for very large volumes. Parameters are similar.

### IPX-Clear (10x)

| Parameter | Minimum | Typical | Maximum |
|---|---|---|---|
| Laser power | 38% | 52% | 68% |
| Scan speed | 40,000 um/s | 80,000 um/s | 150,000 um/s |
| Slice distance | 1.0 um | 3.0 um | 6.0 um |
| Hatch distance | 0.8 um | 2.0 um | 4.0 um |

---

## 20x Objective (Air, 2D Patterning Only)

| Parameter | Typical range | Notes |
|---|---|---|
| Laser power | Determined by resist | Use resist manufacturer's recommended dose |
| Scan speed | Determined by resist | Set to deliver correct energy dose per unit area |
| Slice distance | N/A | 2D only — no Z slicing |
| Hatch distance | 0.5 to 2.0 um | Depends on i-line resist resolution |

Notes:
- 20x is for spin-coated i-line photoresists only. IP-series resins are not compatible.
- No DiLL mode. No 3D printing.

---

## Power and Speed Scaling Rule

When adjusting parameters from the typical values, maintain equivalent exposure by scaling power and speed together:

If you double the scan speed, double the laser power to maintain the same energy per unit length.
If you halve the laser power, halve the scan speed.

This relationship is approximate. At very high or very low powers, the nonlinear absorption of 2PP means the relationship deviates from linear. Use it as a starting point, then verify with a calibration print.
