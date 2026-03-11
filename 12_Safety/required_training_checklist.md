# Required Training Checklist

> This checklist documents the minimum knowledge and practical competencies required before operating the GT2 without direct supervision. Both the trainee and the supervising operator must sign off on each item. Keep a copy in the facility records.

---

## Purpose

This checklist is not a substitute for hands-on training with a qualified supervisor. Its purpose is to:

1. Ensure no critical topic is omitted from training
2. Create a documented record that training was completed
3. Give the trainee a structured review of what they need to know before their first independent session
4. Identify any gaps that require additional instruction before sign-off

---

## Trainee Information

| Field | Entry |
|---|---|
| Trainee name | |
| Trainee email | |
| Department / group | |
| Supervising operator name | |
| Training dates | |
| Facility / GT2 location | |

---

## Section 1: Safety Knowledge

The trainee can correctly answer questions on each topic without prompting.

| Item | Trainee initials | Supervisor initials |
|---|---|---|
| 1.1 Laser wavelength (780 nm), class (Class IV), and why NIR is specifically dangerous (invisible, no blink reflex, no pain) | | |
| 1.2 The rule: hatch must never be opened while the laser is active at printing power | | |
| 1.3 E-stop location and how to activate it | | |
| 1.4 Immediate response to suspected laser eye exposure (go to medical care immediately, do not wait for symptoms) | | |
| 1.5 Acrylate sensitization: what it is, why nitrile gloves are required, that sensitization is irreversible | | |
| 1.6 PGMEA hazard: reproductive toxin category, fume hood requirement for all development steps | | |
| 1.7 IPA flammability and storage requirements | | |
| 1.8 Eyewash station location and 15-minute minimum flush procedure | | |
| 1.9 Spill procedure for small chemical spills (< 10 mL) | | |
| 1.10 UV curing station: 405 nm hazard, required eye protection, lid-closed operation rule | | |

---

## Section 2: Machine Knowledge

The trainee can identify components and explain their function.

| Item | Trainee initials | Supervisor initials |
|---|---|---|
| 2.1 Location and function of: laser enclosure, SPS panel, E-stop, key switch, hatch interlock | | |
| 2.2 SPS startup sequence (correct order: key, E-stop check, hatch, warm-up, green Process light) | | |
| 2.3 Difference between galvo scan mode and piezo scan mode; when each is appropriate | | |
| 2.4 Three sample holder types (Universal, Multi-DiLL Silicon Wafer, 5-inch Mask) and which objective each is used with | | |
| 2.5 How to use the Exchange Holder dialog and why it must be used every time | | |
| 2.6 What interface detection is and what delta-n means | | |
| 2.7 Laser warm-up requirement (45 minutes minimum) and consequence of printing before warm-up | | |
| 2.8 What the AxioVision camera shows during approach and how to recognize correct interference fringes | | |

---

## Section 3: Resist and Substrate Handling

The trainee has performed each step under supervision.

| Item | Trainee initials | Supervisor initials |
|---|---|---|
| 3.1 Substrate cleaning procedure (acetone > IPA > DI water > N2 dry) | | |
| 3.2 IP-Dip2 or IP-S resist application: correct volume, bubble inspection | | |
| 3.3 IP-Q drop casting: dome shape verification, correct volume (1–2 drops only) | | |
| 3.4 Objective installation: fiber ring vs. silicone ring selection; finger-tight rule | | |
| 3.5 Development in PGMEA: fume hood setup, timing, IPA rinse, waste disposal | | |
| 3.6 UV curing station operation: lid closed, timer set, eye protection worn | | |

---

## Section 4: Software Workflow

The trainee has completed at least one full print cycle under supervision, from STL import to developed structure.

| Item | Trainee initials | Supervisor initials |
|---|---|---|
| 4.1 STL export from CAD: watertight mesh, correct units (micrometers), outward normals | | |
| 4.2 DeScribe: objective selection, scan mode selection, slice distance, hatch distance, laser power, scan speed | | |
| 4.3 DeScribe: F5 preview before generating GWL | | |
| 4.4 NanoWrite: loading a GWL file, running interface detection, confirming Z = 0 | | |
| 4.5 NanoWrite: starting a print job and monitoring progress via AxioVision camera | | |
| 4.6 NanoWrite: normal print completion — waiting for job complete confirmation before opening hatch | | |
| 4.7 Shutdown procedure after printing | | |

---

## Section 5: Troubleshooting Awareness

The trainee can describe the correct first response to each situation.

| Item | Trainee initials | Supervisor initials |
|---|---|---|
| 5.1 SPS Safe State: most common cause (hatch not closed) and correct response | | |
| 5.2 "Interface not found" error: three most likely causes and first steps | | |
| 5.3 Flat IP-Q drop: how to recognize it and what to do | | |
| 5.4 Print time longer than expected: two immediate adjustments (galvo mode, scaffold printing) | | |
| 5.5 Structure not present after development: difference between non-adhesion and wash-off | | |
| 5.6 Objective crash: immediate action (E-stop), do not touch until safe retraction, report | | |

---

## Section 6: Facility-Specific Requirements

To be completed by facility supervisor. Add additional items as required by your facility's policies.

| Item | Trainee initials | Supervisor initials |
|---|---|---|
| 6.1 Booking / reservation system for the GT2 | | |
| 6.2 Log book or electronic usage logging procedure | | |
| 6.3 Who to contact if the system has a problem (facility supervisor contact) | | |
| 6.4 Waste disposal locations for PGMEA, IPA, and resist waste | | |
| 6.5 Facility-specific laser safety training completion (if required separately) | | |
| 6.6 Chemical hygiene training completion (if required separately) | | |
| 6.7 Other (specify): | | |

---

## Sign-Off

**Trainee declaration:**

I confirm that I have completed the training items above, that I understand the safety requirements for operating the GT2, and that I will follow the procedures documented in this guide and in my facility's SOPs.

Trainee signature: _________________________ Date: ___________

**Supervisor declaration:**

I confirm that the trainee above has demonstrated adequate knowledge and practical competency to operate the GT2 independently for standard printing workflows (select applicable objectives and resists):

- [ ] 25x + IP-S (Workflow B)
- [ ] 63x + IP-Dip2 (Workflow A)
- [ ] 10x + IP-Q (Workflow C)
- [ ] GP-Silica glass printing (Workflow D) — requires additional furnace training
- [ ] Other: ____________________

Supervisor signature: _________________________ Date: ___________

---

## Notes

Use this space to record any additional training items, limitations on independent operation, or follow-up requirements:

_______________________________________________
_______________________________________________
_______________________________________________

---

## Related Files

- [laser_safety_overview.md](./laser_safety_overview.md)
- [chemical_safety.md](./chemical_safety.md)
- [sps_safety_system.md](./sps_safety_system.md)
- [emergency_procedures.md](./emergency_procedures.md)
- [07_Step_by_Step_Workflows/README.md](../07_Step_by_Step_Workflows/README.md)
