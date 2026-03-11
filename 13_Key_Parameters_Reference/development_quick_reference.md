# Development Quick Reference

## Standard Post-Print Sequence

Remove from holder → PGMEA (primary development) → IPA rinse → nitrogen dry → UV cure at 405 nm

---

## Development Times at Room Temperature (20 to 23 degrees C), Fresh Solvent

| Resin | PGMEA time (small, up to 100 um tall) | PGMEA time (medium, 100 to 300 um) | PGMEA time (large, above 300 um) | IPA rinse | UV cure |
|---|---|---|---|---|---|
| IP-Dip2 | 10 to 15 min | 15 to 20 min | 20 to 25 min | 5 min | 5 to 15 min |
| IP-S | 15 to 20 min | 20 to 30 min | 30 to 35 min | 5 min | 5 to 15 min |
| IP-Visio | 15 to 20 min | 20 to 30 min | 30 to 40 min | 5 min | 5 to 15 min |
| IP-PDMS | 25 to 30 min | 30 to 40 min | 40 to 45 min | 5 min + 5 min (two rinses) | 10 to 20 min |
| IP-Q / IPX-Q | 20 to 25 min | 25 to 35 min | Two-bath: 20 + 20 min | 5 min | 5 to 20 min |
| IPX-Clear | 15 to 20 min | 20 to 25 min | 25 to 30 min | 5 min | 5 to 15 min |
| GP-Silica | 20 to 25 min (no agitation) | 20 to 25 min (no agitation) | Not recommended above 300 um | 3 min (no agitation) | Do not UV cure before sintering |

UV cure times are for the 405 nm station. Larger structures require more time. Hard maximum: 40 min total per session.

---

## Temperature Correction for PGMEA

| Lab temperature | Multiply development time by |
|---|---|
| 18 degrees C | 1.2 |
| 20 to 23 degrees C | 1.0 (use table as-is) |
| 28 degrees C | 0.85 |

---

## Signs of Underdevelopment

Cloudy or hazy regions under optical microscope. Internal channels appear blocked. Fine gaps between features appear filled.
Action: return to fresh PGMEA for 5 to 10 additional minutes, then re-rinse in fresh IPA.

## Signs of Overdevelopment

Features appear larger than designed (swelling). Very fine features are rounded or soft. IP-PDMS structures may be distorted.
Action: reduce development time by 20 to 30% for next print. Cannot be reversed on current sample.

---

## Two-Bath Protocol (IP-Q / Large Structures)

Bath 1: fresh PGMEA, 20 minutes, gentle rocking
Transfer to Bath 2: fresh PGMEA, 20 minutes
Transfer to IPA, 5 minutes
Nitrogen dry

---

## Critical Development Warnings

GP-Silica: no agitation at any step. Handle with extreme care — the green body is fragile.

IP-PDMS: surfaces feel tacky after development = underdeveloped. Return to fresh PGMEA for 10 additional minutes.

All resins: use fresh solvent. Replace PGMEA after 5 to 10 sessions. Replace IPA after 3 to 5 sessions.

All resins: never pour PGMEA or IPA down the drain. Collect in organic solvent waste container.
