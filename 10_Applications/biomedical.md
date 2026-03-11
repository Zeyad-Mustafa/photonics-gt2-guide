# Biomedical Applications

## Why the GT2 Is Used in Biomedical Research

Biological systems are inherently three-dimensional. Cell behavior, tissue organization, and organ function all depend on 3D spatial cues — the arrangement of neighboring cells, the architecture of the extracellular matrix, the presence of gradients, channels, and mechanical variations in the environment. Standard 2D cell culture on flat plastic dishes captures almost none of this complexity.

The GT2 provides the ability to fabricate 3D microenvironments with control over geometry at the scale of individual cells (10 to 100 um) and at the scale of subcellular features (below 1 um). This enables fabrication of scaffolds, devices, and structures that mimic the physical architecture of biological tissues, direct cell behavior, or interface with biological systems at the cellular scale.

---

## What Can Be Fabricated

Cell scaffolds: porous 3D polymer structures that support cell attachment and growth in 3D. Scaffold geometry (pore size, interconnectivity, surface curvature, fiber diameter) can be precisely controlled to guide cell morphology, migration, and differentiation.

Organ-on-chip devices: integrated microfluidic and scaffold systems that recreate the cellular architecture and fluid environment of specific organs (lung, liver, kidney, gut). The GT2 can print both the microfluidic network and the 3D scaffold in a single structure.

Mechanobiology substrates: platforms with controlled mechanical stiffness patterns, topographic features, or dynamic deformation capability for studying how cells sense and respond to mechanical cues.

Neural interfaces: 3D electrode arrays or scaffold-electrode combinations that interface with neural tissue. The scaffold provides structural support while metal-coated features provide electrical contact.

Drug delivery vehicles: 3D printed microparticles or microcapsules with controlled wall thickness and porosity for timed drug release.

Surgical models and phantoms: patient-specific anatomical models at reduced scale for surgical planning, training, or optical property calibration.

Biosensing platforms: 3D structures that concentrate analytes, increase surface area for capture antibodies, or guide fluid flow to improve biosensor performance.

---

## Recommended Objective and Resist

Primary biomedical combination: 25x objective with IP-Visio.

IP-Visio is specifically formulated for biomedical applications:
- Biocompatibility tested according to ISO 10993
- Very low autofluorescence — compatible with fluorescence microscopy imaging of cells on the scaffold without background interference from the material
- Transparent in the visible spectrum
- Cell-compatible surface chemistry (can be functionalized with adhesion proteins)
- Compatible with aqueous biological buffers and cell culture media

For the highest resolution biomedical structures (below 1 um features): 63x objective with IP-Dip2. Note that IP-Dip2 has not been as extensively biocompatibility-tested as IP-Visio — verify biocompatibility for your specific application before cell experiments.

For flexible substrates that match tissue stiffness: 25x objective with IP-PDMS. IP-PDMS provides stiffness in the range of 1 to 5 MPa, which overlaps with soft tissue stiffness and is appropriate for mechanobiology experiments.

---

## Biocompatibility Considerations

Direct contact with cells: IP-Visio has the most extensive biocompatibility testing of any Nanoscribe resin. For other resins used in cell contact applications, test cytotoxicity using a standard assay (MTT, Live/Dead, or equivalent) before committing to a biological experiment.

Sterilization: printed structures must be sterilized before cell seeding. Recommended methods:
- UV irradiation (254 nm UV-C for 30 minutes) — effective for surface sterilization but does not penetrate deeply into porous structures
- Ethanol (70 percent in water, 30 minutes soak) followed by rinsing with sterile PBS — effective for most IP-series polymers; confirm that the ethanol soak does not cause dimensional changes before use
- Autoclave — not recommended; temperatures above 120 degrees C will deform IP-series polymer structures

Surface functionalization for cell adhesion: bare IP-series polymer surfaces support minimal cell adhesion by default. To promote cell attachment, functionalize the surface with extracellular matrix (ECM) proteins:
- Fibronectin coating: adsorb fibronectin from solution (10 to 50 ug/mL in PBS, 1 hour at 37 degrees C) to promote attachment of most adherent cell types
- Collagen coating: for epithelial and endothelial cells
- Laminin coating: for neuronal applications
- RGD peptide grafting: covalent conjugation of RGD (arginine-glycine-aspartate) sequences for controlled integrin-mediated adhesion

Surface functionalization is facilitated by prior O2 plasma treatment (30 to 60 seconds) which creates reactive surface groups that improve protein adsorption.

---

## Scaffold Design Considerations

Pore size for cell infiltration: for cells to migrate into a 3D scaffold interior, the pore diameter must be at least 1.5 to 2 times the cell diameter. Most mammalian cells are 10 to 20 um in diameter, requiring pore diameters of at least 20 to 40 um. Pores below this size restrict cell entry to the scaffold surface only.

Interconnectivity: pores must be interconnected (open to each other) for cells to migrate through the scaffold and for media perfusion to deliver nutrients and remove waste. Design scaffolds with interconnected pore networks — avoid closed-cell geometries.

Strut diameter: scaffold struts (the solid elements that define pore boundaries) must be wide enough to be stable after development. For 25x + IP-Visio, minimum stable strut diameter is approximately 2 um. For mechanical robustness during cell culture, use strut diameters of 5 um or above.

Mechanical stiffness match: cell behavior (proliferation, differentiation, morphology) is strongly influenced by the stiffness of the substrate. Design scaffold geometry and material choice to match the target tissue stiffness:
- Neuronal tissue: 0.1 to 1 kPa — use very compliant geometry or IP-PDMS
- Soft tissue (fat, breast): 1 to 10 kPa — use IP-PDMS or compliant IP-Visio geometry
- Muscle: 10 to 100 kPa — use IP-Visio or IP-S with open-cell geometry
- Bone: 25 to 40 GPa — IP-series polymers cannot match bone stiffness directly; use as template for mineralization or metal deposition

---

## Representative Results

Gyroid scaffold structures in IP-Visio supporting 3D culture of human mesenchymal stem cells with uniform cell distribution throughout the scaffold volume have been demonstrated.

IP-PDMS micropost arrays for traction force microscopy, measuring cell-generated forces from post deflection, have been fabricated with post diameters of 3 um and heights of 10 um using the 25x objective.

Organ-on-chip lung models combining IP-S microfluidic channels with IP-Visio alveolar scaffolds, seeded with human lung epithelial cells, have demonstrated barrier function and response to pharmaceutical compounds.

Neural scaffold arrays with 3D electrode capability, fabricated from IP-Dip2 and coated with platinum by PVD, have demonstrated electrical recording from primary neurons cultured on the 3D structure.

---

## Limitations

- Long-term culture: IP-series polymers have not been tested for stability under extended cell culture conditions (months to years). Monitor for degradation or dimensional changes in long-term experiments.
- Protein adsorption variation: non-specific protein adsorption from cell culture media modifies surface chemistry over time. Control experiments comparing protein-coated and uncoated surfaces are important.
- Nutrient transport: very dense or large scaffolds without perfusion channels will have nutrient gradients in the interior. Design integrated microfluidic perfusion for scaffolds above approximately 500 um in any dimension.

---

Proceed to: photonic_devices.md
