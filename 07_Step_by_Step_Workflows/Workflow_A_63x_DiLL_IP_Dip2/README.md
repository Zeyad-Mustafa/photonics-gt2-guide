# 🧪 Workflow A — 63× Objective + IP-Dip2 (Highest Resolution)

> **Use this workflow when:** You need the finest possible features (< 200 nm), printing micro-optical components, photonic devices, or any structure requiring sub-micron precision.

---

## At a Glance

| Parameter | Value |
|---|---|
| Objective | 63× (NA 1.4, oil immersion) |
| Resist | IP-Dip2 (n = 1.511 @ 780 nm) |
| Mode | DiLL (Dip-in Laser Lithography) |
| Lateral resolution | ~160 nm |
| Axial resolution | ~500 nm |
| Max structure volume | ~0.1 mm³ |
| Typical substrates | Quartz, silicon, 170 µm borosilicate glass |
| Resin stop type | Fiber ring |

---

## Overview of All 12 Steps

```
Step 01 → Design your 3D structure (CAD software)
Step 02 → Export as STL file
Step 03 → Slice in DeScribe (generate GWL code)
Step 04 → Prepare your substrate (cleaning)
Step 05 → Apply IP-Dip2 resist (drop casting)
Step 06 → Install the 63× objective (with fiber ring)
Step 07 → Load sample into the holder
Step 08 → Find the substrate-resist interface
Step 09 → Load and run the print job
Step 10 → Development (remove uncured resin)
Step 11 → UV post-curing (405 nm station)
Step 12 → Characterize your structure
```

---

## Step 01 — Design Your Structure

**What you do:** Create your 3D structure using CAD software (AutoCAD, Fusion 360, SolidWorks, FreeCAD, or OpenSCAD).

**Objective:** Produce a clean 3D solid that can be exported as an STL.

**Key design rules for the 63× objective:**
- Minimum lateral feature: ~300 nm for stable free-standing structures (160 nm is physical minimum but unstable alone)
- Minimum recommended wall thickness: ~2 voxel widths (~600–800 nm)
- Overhanging features are possible but add risk of collapse during development
- If thin features exist (< 2 µm walls), design a **protective wall perimeter** around them to prevent wash-off during development

**Common mistake:** Designing features at the absolute resolution limit without accounting for shrinkage during polymerization (~5–15% depending on IP-Dip2 parameters).

→ **See:** [CAD_Design/designing_for_2PP.md](../../06_Software_Workflow/CAD_Design/designing_for_2PP.md)

---

## Step 02 — Export as STL

**What you do:** Export your design as an `.stl` file from your CAD software.

**Objective:** Produce a watertight, manifold STL with correct surface normals.

**Settings to use:**
- Format: Binary STL (smaller file, faster to load)
- Resolution: Medium-high (avoid too many triangles — slows DeScribe compile time)
- Units: Check that 1 unit = 1 µm in your CAD tool before export

**Validation:** Open the STL in MeshLab or Meshmixer to confirm no holes or flipped normals before proceeding.

→ **See:** [CAD_Design/stl_export_guide.md](../../06_Software_Workflow/CAD_Design/stl_export_guide.md)

---

## Step 03 — Slice in DeScribe

**What you do:** Open DeScribe **on the CNF GPU computer** (NOT the Nanoscribe's own PC — it has no graphics card), import your STL, set parameters, and generate GWL code.

**Objective:** Produce the `_data.gwl` and `_job.gwl` files the GT2 needs.

**DeScribe settings for 63× + IP-Dip2:**
- Objective: Select **63×** from Input dropdown
- Resin: **IP-Dip2**
- Slicing distance: 0.3–0.5 µm (smaller = better quality, slower print)
- Hatching distance: 0.2–0.4 µm
- Laser power: Typically 15–30% (calibrate for your specific lab)
- Scan speed: Start at 10,000–25,000 µm/s

**After slicing:**
- Press **F5** to compile — this generates the 3D preview
- Use **Play** to watch the animation and visually verify layer-by-layer
- Check the **estimated print time** — if too long, adjust hatching/slicing distance

**Files generated:**
- `yourstructure_data.gwl` — contains all coordinates
- `yourstructure_job.gwl` — master control file (edit this for positioning)

⚠️ Copy **both files AND the folder** created by DeScribe to the Nanoscribe computer.

→ **See:** [DeScribe_Software/slicing_parameters.md](../../06_Software_Workflow/DeScribe_Software/slicing_parameters.md)

---

## Step 04 — Prepare Your Substrate

**What you do:** Clean your substrate thoroughly before applying any resin.

**Standard cleaning procedure:**
1. Rinse with **acetone** (removes organic contamination)
2. Rinse with **isopropanol (IPA)** (removes acetone residue)
3. Rinse with **deionized water**
4. Dry with nitrogen gun
5. Optional: **Oxygen plasma treatment** (120 s, 100 W) — improves surface wettability and adhesion. **⚠️ Note:** This changes the surface energy; the resin drop will spread wider.

**For quartz substrates (most common with 63×):**
- Inspect for scratches and dust under optical microscope
- Ensure substrate thickness is within holder tolerance

→ **See:** [05_Substrates/substrate_cleaning_procedure.md](../../05_Substrates/substrate_cleaning_procedure.md)

---

## Step 05 — Apply IP-Dip2 Resist

**What you do:** Place a small drop of IP-Dip2 on the substrate.

**Objective:** Create a **semi-spherical** droplet that sits above the substrate surface.

**How to apply:**
1. Take IP-Dip2 from refrigerated storage — allow to reach room temperature first (~15 min)
2. Using the provided pipette, place **1 small drop** on the center of the substrate
3. The drop should be **semi-spherical** (not flat) — this is important for interface finding
4. ⚠️ **Do not let the drop sit for more than 15–20 minutes** before printing — it will spread and flatten

**Why semi-spherical matters:** A flat drop makes it difficult for the Interface Finder to detect the substrate-resin boundary. A curved drop gives a clear optical contrast.

→ **See:** [04_Resists_and_Materials/IP_Dip2/overview.md](../../04_Resists_and_Materials/IP_Dip2/overview.md)

---

## Step 06 — Install the 63× Objective

**What you do:** Physically mount the 63× objective in the microscope module.

**Before starting:**
1. Make sure the **green "Process" light is OFF**
2. In NanoWrite, click **"Exchange Holder"** → click **"Open"** → wait for button to flash
3. Gently open the top hatch

**Installation:**
1. Remove the **black cap** from the center (position 3) objective slot
2. **Install the fiber ring** on the objective (the 63× uses a fiber ring, NOT the silicone stop used by 10× and 25×)
3. Insert the objective into the turret — rotate **only until it stops**. Do NOT overtighten.
4. On the microscope controller touchscreen, select **Position 3 → "63× Oil"**

⚠️ Only one objective should be in the turret at a time (to avoid resin contamination or crashing).

→ **See:** [03_Objectives/63x_objective/installation_steps.md](../../03_Objectives/63x_objective/installation_steps.md)

---

## Step 07 — Load Sample Holder

**What you do:** Mount your prepared substrate (with resist drop) into the correct sample holder and insert it into the machine.

**For 63× DiLL:**
- Use the **Universal holder** or **DiLL holder** for standard substrates
- Place substrate with the **resist-side facing DOWN** toward the objective
- Secure substrate with tape at the edges
- Insert holder and close the lid

**In NanoWrite:**
- Click on your sample position in the **"Choose Sample Holder"** window (it highlights green)
- Confirm holder selection → click **OK**

→ **See:** [02_Machine_Components/sample_holder_types.md](../../02_Machine_Components/sample_holder_types.md)

---

## Step 08 — Find the Substrate-Resist Interface

**What you do:** Let the system automatically detect the boundary between the substrate and the resin.

**Objective:** The GT2 must know exactly where the substrate surface is to position the first print layer correctly.

**How it works:**
- Click **"Approach Sample"** in NanoWrite
- The system detects the interface using optical reflection — look for **small interference fringes** in the Interface Finder window
- When fringes appear, the system has found the interface

**If interface is not found:**
- Refractive index difference (Δn) must be > 0.04 for auto-detection
- Check that you're using the correct substrate (quartz/silicon, not a mismatched material)
- Ensure the resist drop hasn't dried out or flattened too much

→ **See:** [05_Substrates/interface_detection_requirements.md](../../05_Substrates/interface_detection_requirements.md)

---

## Step 09 — Run the Print Job

**What you do:** Load your `.gwl` job file and start printing.

**Steps in NanoWrite:**
1. Load `yourstructure_job.gwl` via File → Open Job
2. Check the **Estimated Print Time** in the status panel — confirm it is reasonable
3. Click **"Start"**
4. Monitor via the **AxioVision camera feed** — you should see the laser writing in real time
5. Do NOT leave the machine unattended for the first few minutes

**What you'll see:** The laser focal point moves in a hatching pattern layer by layer, bottom to top.

→ **See:** [06_Software_Workflow/NanoWrite_Software/monitoring_print.md](../../06_Software_Workflow/NanoWrite_Software/monitoring_print.md)

---

## Step 10 — Development

**What you do:** Chemically remove the uncured (liquid) resin, leaving only your polymerized structure behind.

**For IP-Dip2:**
1. Carefully remove sample from holder
2. Submerge in **PGMEA** (propylene glycol monomethyl ether acetate) for **20 minutes**
3. Transfer to **IPA** for **5 minutes** (rinse)
4. Gently blow dry with nitrogen

⚠️ **Thin features warning:** If your structure has walls < 2 µm, the development solvent flow can physically knock them over. Use very gentle agitation only.

→ **See:** [08_Development_and_Post_Processing/development_solvents.md](../../08_Development_and_Post_Processing/development_solvents.md)

---

## Step 11 — UV Post-Curing

**What you do:** Expose the developed structure to UV light at the curing station to fully harden the polymer.

**Settings:**
- Wavelength: **405 nm** (near-UV)
- Intensity: ~1.2 W/cm² for structures up to 1 mm height
- Time: **5–20 minutes** depending on structure height and resin volume
- ⚠️ **Do NOT run for more than 40 minutes** — risk of overheating the curing station

**During curing:**
- Close the station door completely
- Observe through the **yellow filter window** — you will see strong fluorescence from your structure
- The station auto-shuts off after the set time

→ **See:** [08_Development_and_Post_Processing/uv_curing_station.md](../../08_Development_and_Post_Processing/uv_curing_station.md)

---

## Step 12 — Characterize Your Structure

**What you do:** Image and measure your printed structure to verify it matches your design.

**Recommended tools:**
- **Optical microscopy** (quick check, visible features > 1 µm)
- **Scanning Electron Microscopy (SEM)** — for sub-µm feature verification
- **Atomic Force Microscopy (AFM)** — for surface roughness characterization
- **White-light interferometry** — for height profiles

**What to document:**
- Top-view and side-view images
- Key dimension measurements vs. design specs
- Surface roughness if relevant
- Adhesion quality (any delamination?)

→ **See:** [07_Step_by_Step_Workflows/Workflow_A_63x_DiLL_IP_Dip2/step_12_characterization.md](step_12_characterization.md)

---

## Common Issues in Workflow A

| Problem | Likely Cause | Fix |
|---|---|---|
| Structure not sticking | Poor substrate cleaning | Redo cleaning, try O₂ plasma |
| Interface not found | Δn too low, flat drop | Use quartz/silicon, re-deposit drop |
| Features missing after development | Underexposure | Increase laser power or reduce scan speed |
| Features merged/blooming | Overexposure | Decrease laser power |
| Structure washed away | Features too thin | Add perimeter walls in CAD design |
| Model shows as bounding box in DeScribe | Rendering mode issue | 3D Preview → Rendering Mode → "Auto" |

→ **Full guide:** [11_Troubleshooting/README.md](../../11_Troubleshooting/README.md)

---

> ✅ **You've completed Workflow A.** For lower-resolution but faster printing, see **[Workflow B — 25× + IP-S](../Workflow_B_25x_DiLL_IP_S/README.md)**.