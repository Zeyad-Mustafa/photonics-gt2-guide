# Development Times Table

## Overview

Development time is not a single fixed value. It depends on the resin type, the structure geometry (particularly the height and internal complexity), the freshness of the solvent, and the temperature of the solvent. The tables below give recommended starting times based on structure height and resin type at room temperature (20 to 23 degrees C) with fresh solvent.

If your structure has internal channels, enclosed volumes, or very fine gaps, add 20 to 30 percent to the times shown — solvent must diffuse into confined spaces, which takes longer than developing an open surface.

---

## Primary Development: PGMEA

Times are for complete immersion in PGMEA with gentle rocking agitation at room temperature.

### IP-Dip2

| Structure height | Development time |
|---|---|
| Up to 50 um | 10 to 15 minutes |
| 50 to 150 um | 15 to 20 minutes |
| 150 to 360 um (maximum) | 20 to 25 minutes |
| Structures with enclosed internal volumes | Add 5 to 10 minutes |

### IP-S

| Structure height | Development time |
|---|---|
| Up to 50 um | 15 to 20 minutes |
| 50 to 200 um | 20 to 30 minutes |
| 200 to 380 um (maximum) | 30 to 35 minutes |
| Microfluidic channels (closed geometry) | 35 to 45 minutes with gentle agitation |

### IP-Q and IPX-Q

| Structure height | Development time |
|---|---|
| Up to 200 um | 20 to 25 minutes |
| 200 to 500 um | 25 to 35 minutes |
| 500 um to 700 um (maximum) | 35 to 45 minutes |
| Large volume structures over 1 mm cubed | Two-bath development: 20 min + 20 min in fresh PGMEA |

### IP-Visio

| Structure height | Development time |
|---|---|
| Up to 100 um | 15 to 20 minutes |
| 100 to 300 um | 20 to 30 minutes |
| Scaffolds with internal porosity | 30 to 40 minutes with gentle rocking |

### IP-PDMS

| Structure height | Development time |
|---|---|
| Up to 100 um | 25 to 35 minutes |
| 100 to 300 um | 35 to 45 minutes |
| All structures | Follow with second IPA rinse (see ipa_rinse_procedure.md) |

### IPX-Clear

| Structure height | Development time |
|---|---|
| Up to 100 um | 15 to 20 minutes |
| 100 to 300 um | 20 to 25 minutes |
| Optical elements requiring clean surfaces | Use fresh PGMEA for every session |

### GP-Silica (Green Body — Handle With Extreme Care)

| Structure height | Development time |
|---|---|
| All heights | 20 to 25 minutes, no agitation whatsoever |

---

## IPA Rinse Times

After PGMEA development, all resins are rinsed in IPA.

| Resin | IPA rinse time |
|---|---|
| IP-Dip2 | 5 minutes |
| IP-S | 5 minutes |
| IP-Q, IPX-Q | 5 minutes |
| IP-Visio | 5 minutes |
| IP-PDMS | 5 minutes (first rinse) + 5 minutes (second rinse) |
| IPX-Clear | 5 minutes |
| GP-Silica | 3 minutes, no agitation |

---

## Effect of Temperature on Development Time

PGMEA is a faster developer at higher temperatures. If your lab runs warmer than 23 degrees C, development will be faster. If colder, it will be slower.

As a rough adjustment:
- At 18 degrees C: multiply recommended times by 1.2
- At 23 degrees C: use times as listed
- At 28 degrees C: multiply recommended times by 0.85

Do not heat PGMEA intentionally to speed up development — elevated temperatures increase the risk of solvent swelling the cured polymer and can cause dimensional distortion.

---

## Signs of Underdevelopment

The structure has regions that appear cloudy, filled, or less distinct than expected when viewed under an optical microscope. Internal channels appear partially or completely blocked. Fine gaps between features are filled with residue.

Action: return the substrate to fresh PGMEA for an additional 5 to 10 minutes, then re-rinse in fresh IPA.

---

## Signs of Overdevelopment

The structure appears slightly larger than designed (swelling). Very fine features appear rounded or soft. Flexible features (IP-PDMS) may have buckled or distorted.

Action: note the actual development time used and reduce it by 20 to 30 percent for the next print. Overdevelopment cannot be reversed on the current sample.

---

## Two-Bath Development Protocol for Large Structures

For large structures where a single PGMEA bath will become saturated with dissolved monomer before development is complete, use two baths:

Bath 1: fresh PGMEA, 15 to 20 minutes with gentle rocking
Transfer substrate carefully to Bath 2: fresh PGMEA, 15 to 20 minutes
Transfer to IPA rinse, 5 minutes
Dry with nitrogen

The two-bath approach ensures the second bath has low monomer concentration, driving diffusion of remaining uncured resin out of the structure more effectively than a single bath would.

---

Proceed to: ipa_rinse_procedure.md
