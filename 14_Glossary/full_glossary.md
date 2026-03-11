# Full Glossary

> All terms used in this guide, defined in plain English, with cross-references to where each concept is covered in depth. Alphabetical order.

---

## A

**Aberration**
A distortion of the laser focal spot caused by imperfect optical conditions. Spherical aberration is the most common in 2PP printing — it elongates the focal spot along the Z axis and reduces peak intensity, producing larger or weaker voxels at depth. Aberration accumulates when the laser travels through materials with mismatched refractive indices. DiLL mode minimizes aberration by creating a homogeneous optical path from the objective to the focal point.
See: [01_Physics_and_Principles/](../01_Physics_and_Principles/README.md), [09_Printing_Modes/dill_mode.md](../09_Printing_Modes/dill_mode.md)

**Acrylate**
A class of chemical compound based on acrylic acid derivatives. Most IP-series photoresists are acrylate-based — the resist cures by crosslinking acrylate monomers into a polymer network when exposed to two-photon absorption. Acrylates are skin sensitizers: repeated exposure can cause irreversible allergic sensitization. Nitrile gloves are required when handling acrylate resists.
See: [12_Safety/chemical_safety.md](../12_Safety/chemical_safety.md), [04_Resists_and_Materials/README.md](../04_Resists_and_Materials/README.md)

**Adhesion layer**
A thin metal film (typically 5–20 nm of titanium, chromium, or ITO) deposited on a substrate by sputtering or evaporation before printing. Adhesion layers serve two purposes: improving the bonding between the polymer structure and the substrate, and improving interface detection by providing a strong reflective surface. Used when printing on substrates with marginal delta-n or poor polymer adhesion.
See: [11_Troubleshooting/structure_not_adhering.md](../11_Troubleshooting/structure_not_adhering.md), [11_Troubleshooting/interface_not_found.md](../11_Troubleshooting/interface_not_found.md)

**Air mode**
A GT2 printing configuration where the 20x air objective focuses through an air gap onto a spin-coated resist layer. Used for 2D and pseudo-3D patterning of i-line photoresists. No liquid immersion medium is used.
See: [09_Printing_Modes/air_mode.md](../09_Printing_Modes/air_mode.md)

**Aspect ratio**
The ratio of a feature's height to its smallest lateral dimension. A pillar 2 um in diameter and 20 um tall has an aspect ratio of 10:1. High-aspect-ratio features are more susceptible to capillary collapse during drying. The practical limit for stable air-dried features is approximately 5:1 to 8:1, depending on material stiffness and base adhesion.
See: [11_Troubleshooting/thin_features_collapsing.md](../11_Troubleshooting/thin_features_collapsing.md)

**Axial**
Along the Z axis — the axis parallel to the laser beam direction. The axial voxel dimension is always larger than the lateral voxel dimension because the laser beam is less tightly confined in Z than in XY. For the 63x objective, the axial voxel is approximately 500 nm; the lateral voxel is approximately 160 nm.
See: [13_Key_Parameters_Reference/feature_size_limits.md](../13_Key_Parameters_Reference/feature_size_limits.md)

---

## B

**Brown body**
The intermediate state of a GP-Silica structure after printing and development but before sintering. A brown body is a porous composite of silica nanoparticles held together by partially crosslinked organic binder. It is fragile and must be handled carefully. The brown body becomes transparent fused silica glass after sintering at 1500 C.
See: [07_Step_by_Step_Workflows/Workflow_D_Glass_Structures_GP_Silica/post_processing.md](../07_Step_by_Step_Workflows/Workflow_D_Glass_Structures_GP_Silica/post_processing.md)

**Build volume**
The total printable volume of the GT2, considering all stages. The large XY motor stage provides 100 x 100 mm of travel; the Z motor stage provides 8 mm. Within a single print field, the scan volume is limited by the piezo (300 x 300 x 300 um) or galvo (400 x 400 um in XY). Large structures beyond a single scan field require stitching.
See: [13_Key_Parameters_Reference/build_volume_table.md](../13_Key_Parameters_Reference/build_volume_table.md)

---

## C

**Capillary collapse**
The failure mode where thin, high-aspect-ratio features (pillars, walls, beams) are deflected and permanently bent during drying after development. Caused by surface tension forces as the liquid-air meniscus recedes across the structure during IPA evaporation. The definitive solution is critical point drying (CPD).
See: [11_Troubleshooting/thin_features_collapsing.md](../11_Troubleshooting/thin_features_collapsing.md)

**Class IV laser**
The highest hazard classification for lasers under the IEC 60825 and ANSI Z136 standards. Class IV lasers can cause immediate permanent eye or skin injury from direct beam exposure, specular reflections, and in some cases diffuse reflections. The GT2's 780 nm femtosecond laser is Class IV. The enclosure and SPS system contain this hazard during normal operation.
See: [12_Safety/laser_safety_overview.md](../12_Safety/laser_safety_overview.md)

**Crosslinking**
The process by which individual polymer chains become chemically bonded to each other, forming a three-dimensional network. In 2PP printing, two-photon absorption activates a photoinitiator that generates radicals, which initiate crosslinking of acrylate monomers. A fully crosslinked polymer network is rigid, insoluble in PGMEA, and mechanically stable. An incompletely crosslinked network dissolves or deforms during development.
See: [01_Physics_and_Principles/](../01_Physics_and_Principles/README.md)

**CPD (Critical Point Drying)**
A drying technique that replaces the liquid in and around a structure with supercritical CO2, which transitions to gas without forming a meniscus (surface tension = 0). Used to prevent capillary collapse of thin, high-aspect-ratio features that would be destroyed by air drying. The substrate is developed in PGMEA, transferred to IPA (miscible with liquid CO2), then processed in a CPD chamber.
See: [11_Troubleshooting/thin_features_collapsing.md](../11_Troubleshooting/thin_features_collapsing.md), [11_Troubleshooting/structure_washed_off.md](../11_Troubleshooting/structure_washed_off.md)

---

## D

**Debinding**
The first stage of GP-Silica post-processing. A furnace program slowly heats the brown body to ~600 C, burning away the organic binder (photoinitiator and polymer network) and leaving only the silica nanoparticle skeleton. The temperature ramp rate through the 200–400 C range must be slow (0.5 C/min) to avoid cracking from rapid gas evolution as the binder decomposes.
See: [07_Step_by_Step_Workflows/Workflow_D_Glass_Structures_GP_Silica/post_processing.md](../07_Step_by_Step_Workflows/Workflow_D_Glass_Structures_GP_Silica/post_processing.md)

**Delta-n (Δn)**
The difference in refractive index between two materials at an interface. Interface detection on the GT2 works by detecting the reflection change when the laser crosses a material interface. A larger delta-n produces a stronger, more detectable reflection. Minimum practical delta-n for reliable detection is approximately 0.04. IP-Dip2 on borosilicate glass (delta-n ~0.004) is at the detection limit; IP-S on ITO glass (delta-n ~0.32) is highly reliable.
See: [11_Troubleshooting/interface_not_found.md](../11_Troubleshooting/interface_not_found.md), [09_Printing_Modes/dill_mode.md](../09_Printing_Modes/dill_mode.md)

**DeScribe**
Nanoscribe's slicing and job preparation software. DeScribe imports STL files, applies printing parameters (objective, scan mode, slice distance, hatch distance, laser power, scan speed), and generates a GWL file for NanoWrite. DeScribe runs on a separate GPU workstation, not on the NanoWrite PC.
See: [06_Software_Workflow/DeScribe_Software/](../06_Software_Workflow/DeScribe_Software/)

**Development**
The post-printing step in which unpolymerized (unexposed) resist is dissolved and removed, leaving only the crosslinked polymer structure. For IP-series resists, development is performed in PGMEA for 20–25 minutes, followed by an IPA rinse to remove residual PGMEA. Development must be performed in a fume hood.
See: [08_Development_and_Post_Processing/what_is_development.md](../08_Development_and_Post_Processing/what_is_development.md)

**DiLL (Dip-in Laser Lithography)**
The primary GT2 printing mode. The objective tip is submerged directly in the liquid photoresist, which serves simultaneously as the printing medium and the immersion medium. DiLL eliminates the glass-resist interface between the objective and the focal point, removing the spherical aberration that accumulates when printing through a cover glass. Compatible with 10x, 25x, and 63x objectives.
See: [09_Printing_Modes/dill_mode.md](../09_Printing_Modes/dill_mode.md)

**Dose**
The total amount of optical energy deposited in a volume of resist. Dose is determined by laser power, scan speed, pulse repetition rate, and spot size. Polymerization occurs when the local dose exceeds the threshold. Higher dose produces larger, more fully crosslinked voxels (up to the overexposure limit). Lower dose produces smaller or incompletely polymerized voxels (down to the underexposure limit).
See: [11_Troubleshooting/overexposure_and_blooming.md](../11_Troubleshooting/overexposure_and_blooming.md), [11_Troubleshooting/underexposure_and_voids.md](../11_Troubleshooting/underexposure_and_voids.md)

---

## E

**E-stop (Emergency Stop)**
A hardwired red mushroom-head pushbutton that, when pressed, immediately cuts power to all GT2 motion systems and forces the SPS into Safe State (laser shutter closed). Located on the GT2 enclosure or control panel. Used in emergencies requiring immediate system shutdown: objective crash, unexpected motion, fire, or other hazardous conditions. Released by twisting clockwise.
See: [12_Safety/sps_safety_system.md](../12_Safety/sps_safety_system.md), [12_Safety/emergency_procedures.md](../12_Safety/emergency_procedures.md)

**Exchange Holder dialog**
A software dialog in NanoWrite that must be used every time a sample holder is loaded or unloaded. The dialog tells NanoWrite which holder type is physically installed so the software can calculate the correct approach range and Z offset. Using the wrong holder type in this dialog is the primary cause of objective crashes.
See: [02_Machine_Components/sample_holder_types.md](../02_Machine_Components/sample_holder_types.md)

---

## F

**Femtosecond (fs)**
One quadrillionth of a second (10^-15 s). The GT2 laser produces pulses 100 fs long. Femtosecond pulses have extremely high peak intensity (watts per cm2) relative to their average power, enabling two-photon absorption at the focal point while leaving the surrounding resist undamaged between pulses.
See: [02_Machine_Components/laser_system.md](../02_Machine_Components/laser_system.md), [01_Physics_and_Principles/](../01_Physics_and_Principles/README.md)

**Focal spot**
The three-dimensional region at the objective focus where laser intensity is highest. In 2PP printing, the voxel forms within the focal spot. The size and shape of the focal spot depend on the objective NA, wavelength, and any aberrations in the optical path. Lateral (XY) dimensions are approximately 160 nm for the 63x; axial (Z) dimensions are approximately 500 nm.
See: [01_Physics_and_Principles/](../01_Physics_and_Principles/README.md)

**Fume hood**
A ventilated enclosure that draws air away from the operator, preventing inhalation of chemical vapors. All PGMEA development steps must be performed in a fume hood. The sash must be kept at or below the marked working line during use.
See: [12_Safety/chemical_safety.md](../12_Safety/chemical_safety.md)

---

## G

**Galvo scan mode**
A GT2 scanning configuration in which two galvanometer mirrors steer the laser beam in XY while the sample remains stationary. Z movement between layers is handled by the piezo stage. Galvo mode is faster than piezo mode (up to 100 mm/s vs. 10 mm/s) but less accurate (~1–2 um vs. ~10 nm). XY scan field is 400 x 400 um.
See: [09_Printing_Modes/galvo_scan_mode.md](../09_Printing_Modes/galvo_scan_mode.md)

**Galvanometer mirror (galvo)**
A small mirror mounted on a galvanometer (an electromagnetic angular actuator) that can rotate rapidly to steer a laser beam. Two galvo mirrors (one for X, one for Y) are used in the GT2 to provide fast beam scanning without moving the sample.
See: [02_Machine_Components/galvo_vs_piezo_scanning.md](../02_Machine_Components/galvo_vs_piezo_scanning.md)

**GP-Silica**
A Nanoscribe photoresist consisting of fused silica nanoparticles suspended in an organic carrier with a photoinitiator. When printed and sintered at 1500 C, GP-Silica produces transparent fused silica glass structures. Has an 8-hour window between application and print completion. Shrinks approximately 25–30% during sintering.
See: [04_Resists_and_Materials/GP_Silica/](../04_Resists_and_Materials/GP_Silica/), [07_Step_by_Step_Workflows/Workflow_D_Glass_Structures_GP_Silica/](../07_Step_by_Step_Workflows/Workflow_D_Glass_Structures_GP_Silica/)

**GWL (Galvo Write Language)**
The job file format used by NanoWrite. A GWL file is a text-based script containing X, Y, Z position commands, laser power commands, and scan speed settings that NanoWrite executes to drive the GT2 hardware. GWL files are generated by DeScribe from the sliced STL model. They can be inspected and, for advanced users, edited manually.
See: [06_Software_Workflow/DeScribe_Software/](../06_Software_Workflow/DeScribe_Software/)

---

## H

**Hatch distance**
The spacing (in micrometers) between adjacent scan lines within a single layer. Together with slice distance, hatch distance determines the overlap between adjacent voxels and therefore the density and uniformity of the printed material. Too large: gaps between scan lines (underexposure voids). Too small: unnecessary exposure time. Typical values: 0.3 um (63x), 0.5 um (25x), 1–2 um (10x).
See: [11_Troubleshooting/underexposure_and_voids.md](../11_Troubleshooting/underexposure_and_voids.md), [11_Troubleshooting/print_taking_too_long.md](../11_Troubleshooting/print_taking_too_long.md)

**Hysteresis**
In the context of the GT2 piezo stage: the phenomenon where the mechanical extension of a piezo crystal at a given applied voltage depends on the history of previous voltages. The GT2 uses closed-loop capacitive feedback to measure and correct for hysteresis, achieving the specified ~10 nm positional accuracy.
See: [09_Printing_Modes/piezo_scan_mode.md](../09_Printing_Modes/piezo_scan_mode.md)

---

## I

**Interface detection**
The automated procedure by which the GT2 locates the substrate surface (Z = 0) before printing. The laser (at sub-threshold power) scans upward in Z while monitoring reflected intensity. A change in reflectivity at the resist-substrate interface (due to delta-n) signals the Z = 0 position. All GWL Z coordinates are measured from this point.
See: [09_Printing_Modes/dill_mode.md](../09_Printing_Modes/dill_mode.md), [11_Troubleshooting/interface_not_found.md](../11_Troubleshooting/interface_not_found.md)

**Inverted immersion mode**
A GT2 printing configuration using the 25x or 63x objective with a liquid immersion medium between the objective and a substrate carrying a spin-coated resist layer on its upper surface. Combines the resolution of a high-NA objective with spin-coated resist preparation.
See: [09_Printing_Modes/inverted_immersion_mode.md](../09_Printing_Modes/inverted_immersion_mode.md)

**IP-Dip2**
Nanoscribe's primary photoresist for the 63x objective in DiLL mode. n = 1.511 at 780 nm. Shrinkage approximately 10–15%. Developed in PGMEA. The "2" designation indicates an improved formulation relative to the original IP-Dip.
See: [04_Resists_and_Materials/IP_Dip2/](../04_Resists_and_Materials/IP_Dip2/)

**IP-PDMS**
A Nanoscribe photoresist formulated to produce soft, elastic (PDMS-like) structures after printing. Used for microfluidic devices, soft robotics, and flexible scaffolds. Lower elastic modulus than standard IP-series resists.
See: [04_Resists_and_Materials/IP_PDMS/](../04_Resists_and_Materials/IP_PDMS/)

**IP-Q**
A Nanoscribe photoresist optimized for the 10x objective. n = 1.48. Applied by drop casting onto silicon wafers; must form a semi-spherical dome shape for reliable interface detection. Lower viscosity than IP-S or IP-Dip2.
See: [04_Resists_and_Materials/IP_Q/](../04_Resists_and_Materials/IP_Q/)

**IP-S**
A Nanoscribe photoresist optimized for the 25x objective. n = 1.478. Lower shrinkage (~5%) than IP-Dip2. Used for mesoscale structures where dimensional accuracy is important.
See: [04_Resists_and_Materials/IP_S/](../04_Resists_and_Materials/IP_S/)

**IP-Visio**
A Nanoscribe photoresist with very low autofluorescence and biocompatibility certification. Used for cell scaffolds, lab-on-chip devices, and other biological applications. Compatible with the 25x objective.
See: [04_Resists_and_Materials/IP_Visio/](../04_Resists_and_Materials/IP_Visio/)

**IPA (Isopropanol)**
The rinse solvent used after PGMEA development. IPA removes residual PGMEA from the structure surface and the substrate. Flash point 12 C — flammable at room temperature. Must be stored in a flammables cabinet and kept away from ignition sources.
See: [12_Safety/chemical_safety.md](../12_Safety/chemical_safety.md), [08_Development_and_Post_Processing/ipa_rinse_procedure.md](../08_Development_and_Post_Processing/ipa_rinse_procedure.md)

**ITO (Indium Tin Oxide)**
A transparent conducting oxide used as a thin coating on glass substrates. ITO-coated glass (ITO glass) is the standard substrate for the 25x + IP-S workflow. The high refractive index of ITO (n ~1.8) relative to IP-S (n = 1.478) gives a large delta-n (~0.32) for highly reliable interface detection. The ITO-coated side must face the objective during printing.
See: [07_Step_by_Step_Workflows/Workflow_B_25x_DiLL_IP_S/step_04_prepare_ITO_substrate.md](../07_Step_by_Step_Workflows/Workflow_B_25x_DiLL_IP_S/step_04_prepare_ITO_substrate.md)

**IPX-Clear**
A Nanoscribe photoresist in the IPX series with very high optical transparency. Compatible with 10x, 25x, and 63x objectives. Used for optical components such as lenses, waveguides, and beam splitters where transparency is critical.
See: [04_Resists_and_Materials/IPX_Clear/](../04_Resists_and_Materials/IPX_Clear/)

**IPX-Q**
A Nanoscribe photoresist in the IPX series designed for the 10x objective. Offers improved resolution compared to IP-Q. Slight amber color in the vial is normal.
See: [04_Resists_and_Materials/IPX_Q/](../04_Resists_and_Materials/IPX_Q/)

---

## L

**Lateral**
In the XY plane — perpendicular to the laser beam direction. The lateral voxel size determines the minimum feature size in X and Y. For the 63x objective, the lateral voxel is approximately 160 nm; for the 25x, approximately 500 nm; for the 10x, approximately 2–5 um.
See: [13_Key_Parameters_Reference/feature_size_limits.md](../13_Key_Parameters_Reference/feature_size_limits.md)

---

## M

**Manifold mesh**
A 3D mesh (STL file) in which every edge is shared by exactly two faces and every face has a consistent outward-facing normal. A manifold (also called "watertight") mesh encloses a well-defined volume with no holes, gaps, or self-intersections. DeScribe requires a manifold mesh for correct slicing — non-manifold meshes produce missing layers, phantom voxels, or incorrect fill.
See: [07_Step_by_Step_Workflows/Workflow_A_63x_DiLL_IP_Dip2/step_02_export_stl.md](../07_Step_by_Step_Workflows/Workflow_A_63x_DiLL_IP_Dip2/step_02_export_stl.md)

**Monomer**
A small molecule that can be linked with others to form a polymer chain. In IP-series resists, acrylate monomers are linked together (polymerized) by the radical chain reaction initiated by the photoinitiator during two-photon exposure. Before exposure, the resist is a liquid solution of monomers; after exposure, it is a crosslinked polymer solid.
See: [04_Resists_and_Materials/README.md](../04_Resists_and_Materials/README.md)

**Multi-DiLL Silicon Wafer Holder**
The sample holder required for 10x printing with IP-Q on silicon wafers. This holder accepts 4-inch silicon wafers and is not compatible with the 25x or 63x objectives. Must be selected in the Exchange Holder dialog before loading.
See: [02_Machine_Components/sample_holder_types.md](../02_Machine_Components/sample_holder_types.md)

---

## N

**NA (Numerical Aperture)**
A dimensionless number that describes the angular range of light that a lens can accept or emit. Higher NA means a tighter focus and therefore a smaller focal spot and smaller minimum voxel. The GT2 objectives have NA values of 0.3 (10x), 0.5 (20x), 0.8 (25x), and 1.4 (63x). NA determines the fundamental resolution limit of the print.
See: [03_Objectives/](../03_Objectives/README.md), [13_Key_Parameters_Reference/objective_specs_full_table.md](../13_Key_Parameters_Reference/objective_specs_full_table.md)

**NanoWrite**
Nanoscribe's print control software. NanoWrite runs on the GT2's dedicated PC (not the DeScribe workstation), controls the hardware in real time, runs interface detection, executes GWL job files, and displays the live camera feed from AxioVision. NanoWrite does not do slicing — that is DeScribe's role.
See: [06_Software_Workflow/NanoWrite_Software/](../06_Software_Workflow/NanoWrite_Software/)

**NIR (Near-Infrared)**
Electromagnetic radiation with wavelengths from approximately 700–2500 nm, just beyond the red end of the visible spectrum. The GT2 laser operates at 780 nm NIR. NIR is invisible to the human eye, which makes NIR laser hazards particularly dangerous — there is no visible warning that the beam is present.
See: [12_Safety/laser_safety_overview.md](../12_Safety/laser_safety_overview.md)

---

## O

**OD (Optical Density)**
A logarithmic measure of light attenuation. A filter with OD 3 transmits 0.1% (10^-3) of incident light; OD 7 transmits 10^-7 (one ten-millionth). Laser safety eyewear is rated by OD at specific wavelengths. Open-beam work on the GT2 laser requires OD 7+ eyewear at 780 nm.
See: [12_Safety/laser_safety_overview.md](../12_Safety/laser_safety_overview.md)

**Oil immersion mode**
A GT2 printing configuration in which immersion oil (Zeiss Immersol 518F, n = 1.518) fills the gap between the 63x objective and the bottom surface of a 170 um borosilicate glass coverslip, with resist on the top surface of the coverslip. Used when the resist must be accessed from the opposite side of a substrate.
See: [09_Printing_Modes/oil_immersion_mode.md](../09_Printing_Modes/oil_immersion_mode.md)

**Overexposure**
A condition where the laser dose at the focal point exceeds the upper boundary of the process window, producing voxels that are larger than intended. Overexposed structures have features larger than designed: walls are thicker, holes are smaller or closed, adjacent features merge. Corrected by reducing laser power or increasing scan speed.
See: [11_Troubleshooting/overexposure_and_blooming.md](../11_Troubleshooting/overexposure_and_blooming.md)

---

## P

**PGMEA (Propylene Glycol Methyl Ether Acetate)**
The primary developer solvent for IP-series and IPX-series photoresists. PGMEA dissolves uncrosslinked (unexposed) resist while leaving the polymerized structure intact. Classification: Category 2 reproductive toxin. All PGMEA use must occur in a fume hood. Waste must be disposed of as hazardous chemical waste.
See: [12_Safety/chemical_safety.md](../12_Safety/chemical_safety.md), [08_Development_and_Post_Processing/development_solvents.md](../08_Development_and_Post_Processing/development_solvents.md)

**Photoinitiator**
A molecule in the photoresist that absorbs photons and generates reactive radical species, which then initiate crosslinking of the acrylate monomers. In 2PP printing, the photoinitiator absorbs two photons simultaneously — a nonlinear process that only occurs at the intensity peak of the focal spot. This is what gives 2PP its sub-diffraction resolution.
See: [01_Physics_and_Principles/](../01_Physics_and_Principles/README.md), [04_Resists_and_Materials/README.md](../04_Resists_and_Materials/README.md)

**Photoresist**
A light-sensitive material that changes its chemical properties upon exposure to light. In GT2 printing, photoresists are liquid acrylate formulations that polymerize (solidify) when exposed to 780 nm femtosecond laser pulses via two-photon absorption. After development, the exposed (polymerized) regions remain; the unexposed regions are dissolved.
See: [04_Resists_and_Materials/README.md](../04_Resists_and_Materials/README.md)

**Piezo scan mode**
A GT2 scanning configuration in which the piezo stage moves the sample in X, Y, and Z while the beam and objective remain stationary. Piezo mode offers ~10 nm positional accuracy and supports tilt correction. Range is 300 x 300 x 300 um. Slower than galvo mode but more accurate.
See: [09_Printing_Modes/piezo_scan_mode.md](../09_Printing_Modes/piezo_scan_mode.md)

**Piezoelectric stage**
A precision motion stage that uses the expansion of piezoelectric crystals (which change dimension when voltage is applied) to move the sample. The GT2's piezo stage has a range of 300 x 300 x 300 um and a positional accuracy of ~10 nm with closed-loop feedback.
See: [02_Machine_Components/microscope_module.md](../02_Machine_Components/microscope_module.md)

**Polymerization threshold**
The minimum laser intensity at the focal point required to initiate crosslinking of the resist. Below this threshold, no polymerization occurs and no voxel is formed. The threshold is a property of the specific resist and is affected by photoinitiator concentration, pulse energy, and resist age.
See: [01_Physics_and_Principles/](../01_Physics_and_Principles/README.md)

**Proximity effect**
In dense arrays or tightly spaced features, each voxel's peripheral (sub-threshold) exposure contributes to the total dose received by neighboring voxels. The accumulated dose in dense regions effectively raises the local exposure above the threshold for a larger volume, causing features in dense areas to be systematically larger than isolated features printed at the same parameters.
See: [11_Troubleshooting/overexposure_and_blooming.md](../11_Troubleshooting/overexposure_and_blooming.md)

---

## R

**Refractive index (n)**
A dimensionless number describing how much a material slows light relative to vacuum. The refractive index of a material determines how light bends at its surface and how the material interacts optically with neighboring materials. Matching refractive indices across the optical path reduces aberration. The mismatch (delta-n) between resist and substrate determines interface detection reliability.
See: [09_Printing_Modes/dill_mode.md](../09_Printing_Modes/dill_mode.md), [11_Troubleshooting/interface_not_found.md](../11_Troubleshooting/interface_not_found.md)

---

## S

**Safe State**
The condition of the GT2 when the SPS has determined that one or more safety conditions are not met. In Safe State, the laser shutter is forced closed and the system cannot print. The green Process light is off in Safe State.
See: [12_Safety/sps_safety_system.md](../12_Safety/sps_safety_system.md), [11_Troubleshooting/sps_safe_state_error.md](../11_Troubleshooting/sps_safe_state_error.md)

**Scaffold printing**
A printing strategy in which the interior of a structure is replaced with a sparse lattice (scaffold) instead of solid infill. The scaffold provides mechanical support for the outer shell during development while dramatically reducing print time and material volume.
See: [08_Development_and_Post_Processing/scaffold_and_shell_printing.md](../08_Development_and_Post_Processing/scaffold_and_shell_printing.md), [11_Troubleshooting/print_taking_too_long.md](../11_Troubleshooting/print_taking_too_long.md)

**Scan speed**
The speed (in micrometers per second) at which the focal point moves through the resist during printing. Scan speed and laser power together determine the dose deposited per voxel. Typical ranges: 10,000–50,000 um/s (63x piezo), 50,000–150,000 um/s (25x galvo), 100,000–200,000 um/s (10x galvo).
See: [13_Key_Parameters_Reference/scanning_speed_table.md](../13_Key_Parameters_Reference/scanning_speed_table.md)

**Sensitizer / sensitization**
A sensitizer is a chemical that can cause allergic sensitization — a permanent immune system hypersensitivity — with repeated exposure. Acrylate monomers in IP-series resists are sensitizers. Once sensitized, even trace contact can trigger an allergic reaction. Sensitization is irreversible. Strict glove discipline prevents sensitization.
See: [12_Safety/chemical_safety.md](../12_Safety/chemical_safety.md)

**Shell printing**
A printing strategy in which only the outer surface of a structure is printed as a hollow shell, leaving the interior as unpolymerized resist that washes away during development. Reduces print time significantly compared to solid infill. Often combined with scaffold printing for tall or large-volume structures.
See: [08_Development_and_Post_Processing/scaffold_and_shell_printing.md](../08_Development_and_Post_Processing/scaffold_and_shell_printing.md)

**Shrinkage**
The reduction in physical dimensions that occurs when a photopolymer cures. Crosslinking draws polymer chains closer together, reducing volume. IP-series resists typically shrink 5–15% depending on formulation and exposure. GP-Silica shrinks 25–30% during sintering. Shrinkage must be compensated in the CAD model by scaling up the design before printing.
See: [04_Resists_and_Materials/IP_Dip2/shrinkage_and_compensation.md](../04_Resists_and_Materials/IP_Dip2/shrinkage_and_compensation.md)

**Sintering**
The second stage of GP-Silica post-processing. After debinding, the silica nanoparticle skeleton is heated to 1500 C, causing the particles to fuse into a continuous, dense, transparent glass. Sintering reduces the structure volume by approximately 25–30% relative to the printed dimensions.
See: [07_Step_by_Step_Workflows/Workflow_D_Glass_Structures_GP_Silica/post_processing.md](../07_Step_by_Step_Workflows/Workflow_D_Glass_Structures_GP_Silica/post_processing.md)

**Slice distance**
The Z spacing (in micrometers) between successive layers in a print job. Together with hatch distance, slice distance determines voxel overlap in Z and therefore the density and mechanical integrity of the printed material. Typical values: 0.5 um (63x), 1.0 um (25x), 2–5 um (10x).
See: [11_Troubleshooting/underexposure_and_voids.md](../11_Troubleshooting/underexposure_and_voids.md), [11_Troubleshooting/print_taking_too_long.md](../11_Troubleshooting/print_taking_too_long.md)

**SPS (Safety Precedence Sequence)**
The GT2's hardware safety interlock controller. The SPS monitors the enclosure hatch state, E-stop, key switch, and other conditions, and allows the laser shutter to open only when all conditions are simultaneously satisfied. The SPS cannot be overridden by NanoWrite software during normal operation.
See: [12_Safety/sps_safety_system.md](../12_Safety/sps_safety_system.md), [02_Machine_Components/safety_enclosure_and_sps.md](../02_Machine_Components/safety_enclosure_and_sps.md)

**STL (Stereolithography / Standard Tessellation Language)**
The file format used to describe 3D geometry for printing. An STL file represents the surface of a 3D object as a mesh of triangular faces. DeScribe imports STL files to generate GWL job files. STL files must be manifold (watertight), have outward-facing normals, and use correct units (micrometers) for GT2 printing.
See: [07_Step_by_Step_Workflows/Workflow_A_63x_DiLL_IP_Dip2/step_02_export_stl.md](../07_Step_by_Step_Workflows/Workflow_A_63x_DiLL_IP_Dip2/step_02_export_stl.md)

**Stitching**
The process of printing adjacent scan fields and joining them to produce a structure larger than a single scan field (400 x 400 um for galvo; 300 x 300 um for piezo). The large XY motor stage repositions the sample between fields. Imperfect stitching produces visible seams at field boundaries.
See: [09_Printing_Modes/galvo_scan_mode.md](../09_Printing_Modes/galvo_scan_mode.md)

---

## T

**TPA (Two-Photon Absorption)**
The nonlinear optical process at the core of 2PP printing. A molecule absorbs two photons simultaneously, gaining energy equal to the sum of the two photon energies. At 780 nm, two photons together have the same energy as one 390 nm UV photon. This energy is sufficient to activate the photoinitiator and initiate polymerization. TPA requires very high instantaneous intensity (available only at the focal point of a femtosecond laser) and scales with the square of intensity — this nonlinearity confines polymerization to a sub-diffraction volume.
See: [01_Physics_and_Principles/](../01_Physics_and_Principles/README.md)

**Tilt correction mode**
A GT2 piezo scan mode feature that compensates for substrates that are not perfectly horizontal. Before printing, the system samples the substrate surface at multiple X, Y positions and fits a plane equation. During printing, every Z coordinate is offset by the tilt correction to keep layers parallel to the actual substrate surface.
See: [09_Printing_Modes/tilt_correction_mode.md](../09_Printing_Modes/tilt_correction_mode.md)

**2PP (Two-Photon Polymerization)**
The fabrication technique used by the GT2. A tightly focused femtosecond laser beam initiates polymerization via two-photon absorption only at the focal point, where intensity is high enough to drive the nonlinear TPA process. This confines polymerization to a sub-diffraction volume (the voxel), enabling 3D structures with features below the diffraction limit of light.
See: [01_Physics_and_Principles/](../01_Physics_and_Principles/README.md)

---

## U

**Underexposure**
A condition where the laser dose at the focal point is below the threshold required for complete polymerization. Underexposed structures have voids, porous regions, gaps between scan lines, or are mechanically weak. Corrected by increasing laser power or decreasing scan speed, or by reducing hatch/slice distance.
See: [11_Troubleshooting/underexposure_and_voids.md](../11_Troubleshooting/underexposure_and_voids.md)

**Universal Sample Holder**
The general-purpose sample holder for the GT2, compatible with the 25x and 63x objectives. Accepts glass substrates, ITO glass, quartz, and other flat samples. Not compatible with the 10x objective (use the Multi-DiLL Silicon Wafer Holder for 10x work).
See: [02_Machine_Components/sample_holder_types.md](../02_Machine_Components/sample_holder_types.md)

**UV curing**
Post-development exposure to 405 nm UV light to complete crosslinking of the polymer surface and interior. UV curing increases mechanical hardness, reduces surface tackiness, and removes residual photoinitiator (important for biocompatibility in IP-Visio structures). Maximum cure time: 40 minutes. Eye protection required.
See: [08_Development_and_Post_Processing/uv_curing_station.md](../08_Development_and_Post_Processing/uv_curing_station.md), [12_Safety/uv_curing_eye_safety.md](../12_Safety/uv_curing_eye_safety.md)

---

## V

**Voxel**
The three-dimensional unit cell of a 2PP-printed structure — analogous to a pixel in a 2D image, but in three dimensions. Each voxel is an ellipsoid of polymerized resist formed by a single pass of the focal point. Lateral diameter is smaller than axial height. The smallest printable feature is approximately one voxel in size. Structures are built by writing many overlapping voxels in a programmed pattern.
See: [01_Physics_and_Principles/](../01_Physics_and_Principles/README.md), [13_Key_Parameters_Reference/feature_size_limits.md](../13_Key_Parameters_Reference/feature_size_limits.md)

---

## W

**WD (Working Distance)**
The distance between the front element of an objective lens and the focal plane when the objective is focused at its designed depth. The working distance limits how far into the resist the GT2 can print. Key values: 63x ~360 um, 25x ~380 um, 10x ~700 um, 20x ~1.2 mm. In oil immersion mode, the cover glass consumes part of the working distance.
See: [13_Key_Parameters_Reference/objective_specs_full_table.md](../13_Key_Parameters_Reference/objective_specs_full_table.md)

**Warm-up**
The 45-minute period after laser power-on during which the femtosecond laser stabilizes its output power and pulse characteristics. Printing before the warm-up is complete produces unreliable and irreproducible results — laser power at the stated percentage setting is only calibrated after the warm-up period. Never start an interface detection or print job until the warm-up is confirmed complete.
See: [02_Machine_Components/laser_system.md](../02_Machine_Components/laser_system.md), [06_Software_Workflow/NanoWrite_Software/startup_procedure.md](../06_Software_Workflow/NanoWrite_Software/startup_procedure.md)

**Watertight mesh**
See: **Manifold mesh**

---

## Z

**Z = 0**
The reference position set by interface detection — the Z coordinate of the substrate surface as detected by the GT2. All Z coordinates in the GWL file are positive offsets from Z = 0 (i.e., Z = 1 um means 1 um above the substrate surface). If Z = 0 is set incorrectly, the structure prints in the wrong location.
See: [09_Printing_Modes/dill_mode.md](../09_Printing_Modes/dill_mode.md), [11_Troubleshooting/interface_not_found.md](../11_Troubleshooting/interface_not_found.md)
