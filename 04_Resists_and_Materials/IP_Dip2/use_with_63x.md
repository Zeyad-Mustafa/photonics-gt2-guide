# IP-Dip2 — Use with the 63x Objective

> This file walks through the specific considerations and steps for printing IP-Dip2 with the 63x objective. For the complete end-to-end workflow, see Workflow A in 07_Step_by_Step_Workflows.

---

## Why IP-Dip2 and the 63x Are Inseparable

The 63x objective (NA 1.4) is an **oil-immersion** objective. It requires a liquid medium between its front lens and the substrate to achieve its rated NA. IP-Dip2 acts as both the printing resist and the immersion medium simultaneously — this is the defining feature of DiLL mode.

```
63x objective (front lens, NA 1.4)
        |
        | <-- IP-Dip2 resist (acts as immersion medium)
        |
    Substrate surface (borosilicate glass, quartz, or silicon)
        |
   [printing happens here, at or just above this surface]
```

There is no separate immersion oil applied before printing. The resist itself fills the optical gap. This is why n = 1.511 for IP-Dip2 — it approximates the refractive index of immersion oil (1.518) closely enough that the 63x objective performs at near-rated NA.

---

## Substrate Requirements for 63x + IP-Dip2

Not every substrate works with the 63x/IP-Dip2 combination. Requirements:

| Substrate | Compatible? | Notes |
|---|---|---|
| Borosilicate glass, 170 um thick | Yes (preferred) | Standard coverslip; n ~ 1.515 matches oil path |
| Quartz substrate | Yes | n ~ 1.46 — slight mismatch but functional |
| Silicon wafer | Yes (with limitations) | Opaque — interface detection uses reflection only |
| ITO-coated glass | Yes | ITO side must face the objective |
| Standard glass slides (1 mm thick) | No | Too thick — oil-immersion WD (360 um) is insufficient to reach the substrate-resist interface through 1 mm glass |

> The 170 um borosilicate glass (standard No. 1.5 coverslip) is the preferred substrate for 63x/IP-Dip2. It is thin enough that the working distance is not consumed by passing through the glass, and its n matches the oil path.

---

## Resist Application: How to Apply IP-Dip2

1. Place the substrate (170 um coverslip or equivalent) in the Universal sample holder, functional side facing down.
2. On the upward-facing surface of the substrate, apply a **small drop** of IP-Dip2 — approximately 5-15 uL (1-3 drops from a pipette or the bottle dropper).
3. The drop should be domed (semi-spherical), not spread flat.
4. Do not spread the resist with a tool. Allow it to wet the surface naturally.
5. Immediately close the top hatch to protect the resist from ambient light.

> Do not flood the substrate with resist. A large flat pool makes interface detection harder and wastes material. The resist should form a clear, slightly domed droplet.

---

## Fiber Ring Installation

The 63x objective requires a **fiber ring** (a silicone seal ring) to be installed on the objective barrel before printing. This ring:
- Prevents the resist from wicking up the sides of the objective
- Contains the resist drop in the focal zone
- Protects the objective barrel from chemical exposure

> The 25x and 10x objectives do NOT use a fiber ring. Only the 63x requires this step.

Installing the fiber ring:
1. Slide the ring onto the 63x objective barrel until it seats in the groove just above the front lens
2. Confirm it is level and fully seated
3. Do not use the objective without the ring — resist will contaminate the turret

See **[03_Objectives/63x_objective/fiber_ring_installation.md](../../03_Objectives/63x_objective/fiber_ring_installation.md)** for detailed installation steps.

---

## Laser Power and Speed Parameters

Starting parameters for IP-Dip2 with the 63x objective (adjust based on calibration):

| Parameter | Starting Value | Notes |
|---|---|---|
| Scan mode | Piezo | Galvo also possible for larger features |
| Laser power | 15-25% | Run a calibration array first |
| Scan speed | 10,000-50,000 um/s | Higher speed = less dose = smaller voxels |
| Slice distance | 0.2-0.5 um | Very fine slicing needed for sub-micron Z resolution |
| Hatch distance | 0.1-0.3 um | Match to voxel lateral size |

> These are starting points only. Every machine, resist batch, and substrate combination requires its own calibration. Print a power-speed array (also called a "dose matrix") before your first full print.

---

## Interface Finding with IP-Dip2

The interface between the borosilicate substrate and IP-Dip2 has a refractive index difference of:

Dn = n(IP-Dip2) - n(glass) = 1.511 - 1.515 = -0.004

This is below the minimum Dn of 0.04 required for reliable auto-interface detection when printing through the glass from below. In practice:

- Interface detection with 63x/IP-Dip2 uses **reflection from the top surface of the substrate** (the side facing the resist), not the bottom
- The system may require manual adjustment of the Z position to find the interface
- Watch the AxioVision camera for interference fringes — when they appear, you are within a few micrometers of the substrate surface

> If interface detection consistently fails with IP-Dip2 on glass, try switching to manual interface finding mode in NanoWrite and watching for the fringe pattern in AxioVision. See **[11_Troubleshooting/interface_not_found.md](../../11_Troubleshooting/interface_not_found.md)**.

---

## Cleaning the 63x Objective After Printing

After each print with IP-Dip2:

1. Remove the sample holder using the Exchange Holder dialog.
2. While the objective is in the retracted position, gently wipe the front lens with a lens tissue moistened with IPA.
3. Remove and clean the fiber ring — soak in IPA for a few minutes, then dry.
4. Inspect the objective under the camera for any resist residue on the front lens. Residue will degrade performance in subsequent prints.

> Never use acetone on the objective lens. Use only IPA and lens-grade tissue. Acetone can damage the anti-reflection coatings.

---

## Related Files

- [overview.md](./overview.md)
- [properties.md](./properties.md)
- [handling_and_storage.md](./handling_and_storage.md)
- [03_Objectives/63x_objective/overview.md](../../03_Objectives/63x_objective/overview.md)
- [03_Objectives/63x_objective/fiber_ring_installation.md](../../03_Objectives/63x_objective/fiber_ring_installation.md)
- [07_Step_by_Step_Workflows/Workflow_A_63x_DiLL_IP_Dip2/README.md](../../07_Step_by_Step_Workflows/Workflow_A_63x_DiLL_IP_Dip2/README.md)
- [11_Troubleshooting/interface_not_found.md](../../11_Troubleshooting/interface_not_found.md)