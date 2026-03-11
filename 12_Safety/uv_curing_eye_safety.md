# UV Curing Eye Safety

> The UV curing station used after GT2 printing emits 405 nm violet light. This wavelength is at the boundary of visible and near-UV. It is not the same hazard as the 780 nm NIR printing laser, but it is bright enough to cause photokeratitis (UV eye burn) and accelerated lens clouding with repeated unprotected exposure. Eye protection is required when the UV station is operating.

---

## The UV Curing Station Parameters

| Parameter | Value |
|---|---|
| Wavelength | 405 nm (violet / near-UV) |
| Typical power | 5–20 mW/cm2 at sample |
| Exposure time (standard) | 10–20 minutes, maximum 40 minutes |
| Light source | LED array or mercury arc lamp (depends on station model) |
| Enclosure | Partial — most stations have a lid but are not fully light-tight |

---

## Is 405 nm Dangerous?

405 nm sits at the boundary between visible violet and near-UV (UV-A begins at ~400 nm). Its hazard profile is between that of a bright visible light and UV-A:

- **Not ionizing** — 405 nm does not cause DNA damage in the same way that UV-C (254 nm) or UV-B (280–315 nm) does. The risk of carcinogenesis from 405 nm exposure is very low.
- **Photokeratitis risk** — the cornea absorbs UV-A and near-UV. Extended unprotected exposure to 405 nm can cause photokeratitis (inflammation of the cornea, commonly called "welder's flash" or "snow blindness"). Symptoms are delayed by hours and include pain, tearing, and light sensitivity. The condition resolves in 24–48 hours but is acutely painful.
- **Lens hazard** — UV-A and near-UV contribute to lens clouding (cataract formation) over years of cumulative exposure. Occasional, protected exposure is not a concern; habitual unprotected exposure over many years is.
- **Bright enough to cause photochemical retinal damage** — the intensity from a UV curing station at close range can cause photochemical retinal injury with extended direct viewing even at 405 nm. Do not stare at the operating station.

**The practical guidance is simple: do not look directly at the UV curing station when it is operating, and wear UV-blocking eye protection if your face is within 30 cm of the light source.**

---

## Eye Protection for UV Curing

Standard polycarbonate safety glasses block essentially all UV below 380–400 nm and significantly attenuate 405 nm. For the UV curing step:

- **Standard lab safety glasses with polycarbonate lenses** — adequate for most use: operating the station, setting the timer, walking past while it is running
- **UV-blocking face shield** — preferred if you need to inspect the sample while the station is running, or if the station does not have a lid
- **Do not use regular prescription glasses alone** — standard glass and many plastic lens materials do not block 405 nm well. Wear safety glasses over or instead of prescription glasses.

---

## Operating the UV Curing Station Safely

1. Place the developed, IPA-rinsed sample in the station.
2. Close the lid before activating the UV source.
3. Set the timer. Standard cure: 10–20 minutes. Maximum: 40 minutes. Do not exceed 40 minutes — over-curing can cause stress cracking in some IP-series structures.
4. Activate the UV source with the lid closed.
5. Do not open the lid during operation without first turning off the UV source.
6. When the timer expires, turn off the UV source, then open the lid.
7. Allow the sample to cool briefly before handling — the LED array can heat the sample surface during a full 40-minute cure.

---

## When UV Curing Is and Is Not Required

| Situation | UV Curing Required? |
|---|---|
| IP-Dip2, IP-S, IP-Q — standard optical or mechanical structures | Optional — improves mechanical stability and surface hardness |
| IP-Visio — biological scaffolds, cell culture | Yes — removes residual photoinitiator that may be cytotoxic |
| IP-PDMS — soft structures | Usually not — PDMS-based materials may degrade with UV over-exposure |
| GP-Silica — glass precursor | Not applicable — the material undergoes sintering, not UV cure |
| Any structure that will be handled directly by users | Yes — surface cure eliminates tacky surface residue |

When in doubt, a standard 15-minute UV cure is appropriate for all IP-series structures except IP-PDMS.

---

## Station Maintenance Note

405 nm LED arrays degrade over time. If the station's effective dose decreases (structures remain tacky after the standard cure time), the LED array may need replacement. Report this to your facility supervisor rather than indefinitely extending cure times.

---

## Related Files

- [laser_safety_overview.md](./laser_safety_overview.md)
- [chemical_safety.md](./chemical_safety.md)
- [08_Development_and_Post_Processing/uv_curing_station.md](../08_Development_and_Post_Processing/uv_curing_station.md)
- [07_Step_by_Step_Workflows/Workflow_A_63x_DiLL_IP_Dip2/step_11_uv_curing.md](../07_Step_by_Step_Workflows/Workflow_A_63x_DiLL_IP_Dip2/step_11_uv_curing.md)
