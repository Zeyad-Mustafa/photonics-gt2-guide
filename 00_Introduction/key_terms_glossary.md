# 📖 Key Terms Glossary — Essential Vocabulary Before You Begin

> Read this before anything else. These 30 terms will appear constantly throughout the guide. Understanding them now will make every other section click immediately.

---

## A

**Axial Direction**
The vertical direction — up and down along the laser beam path (Z-axis). Voxels are always longer in the axial direction than in the lateral direction.

---

## D

**Development**
The post-printing chemical step where you wash away uncured (still liquid) resin using a solvent like PGMEA or IPA. Only the polymerized (solid) parts of your structure remain after development.

**DiLL — Dip-in Laser Lithography**
The primary printing mode of the GT2. The objective lens physically dips directly into the liquid resin on the substrate, eliminating the glass-air interface and improving focus quality dramatically.

**DeScribe**
Nanoscribe's proprietary slicing software. Converts your STL file into a GWL script the machine can execute. Run on the CNF GPU computer, not on the GT2's own PC.

---

## F

**Femtosecond**
One quadrillionth of a second (10⁻¹⁵ seconds). The GT2's laser fires pulses that are 100 femtoseconds long. For reference: 100 femtoseconds is to 1 second what 1 second is to 300 million years.

**Focal Point**
The precise spot inside the resin where the laser beam converges to its tightest concentration of energy. This is where polymerization occurs.

---

## G

**Galvo Scanning**
A fast scanning method using galvanometer mirrors to steer the laser beam. Covers a 400×400 µm field quickly. Used for speed-priority printing. Less positionally accurate than piezo scanning.

**GWL — Gwl Writing Language**
The native script format of the Nanoscribe GT2. Think of it as G-code for nanoscale printing. DeScribe generates GWL files from your STL. You can also write GWL manually for automation.

---

## H

**Hatching**
The fill pattern written inside each layer of your structure. Like mowing a lawn in parallel lines. Hatch distance controls how close together the lines are — smaller distance = denser fill = stronger structure, but slower print.

**Hatch Distance**
The spacing between adjacent scan lines within a layer. Typical values: 0.2–0.5 µm for 63× objective, 0.5–1 µm for 25×, 1–2 µm for 10×.

---

## I

**Interface**
The boundary between the substrate (glass, silicon) and the liquid resin sitting on top of it. The GT2 must find this interface before printing to know exactly where to start building the structure.

**IP-Series Resins**
Nanoscribe's proprietary family of photopolymer resins. IP stands for "InfraRed Photopolymer." Each variant (IP-Dip2, IP-S, IP-Q, IP-Visio, IP-PDMS, etc.) is optimized for different objectives, applications, and properties.

**ITO — Indium Tin Oxide**
A transparent conductive coating applied to glass substrates. ITO-coated glass is the standard substrate for the 25× DiLL workflow. The ITO side must face **down** toward the objective.

---

## L

**Laser Power**
Expressed as a percentage (0–100%) in DeScribe and NanoWrite. Controls how much energy is delivered to each voxel. Too low = underexposure (structure doesn't form). Too high = overexposure (blooming, merged features).

**Lateral Direction**
The horizontal direction — side to side (X and Y axes). The voxel's lateral dimension determines the finest horizontal feature size (~160 nm with 63× objective).

---

## M

**Monomer**
A small individual molecule that can link with others to form a polymer chain. The liquid resin in the GT2 is full of monomers. After polymerization, they become a solid polymer.

---

## N

**NA — Numerical Aperture**
A number that describes how tightly an objective can focus light. Higher NA = smaller focal spot = better resolution. The 63× objective has NA 1.4 (highest). The 10× has NA 0.3 (lowest).

**NanoWrite**
Nanoscribe's machine control software. Runs on the GT2's dedicated PC. Used to approach the sample, load GWL job files, and monitor the print in real time.

---

## O

**Objective**
The precision microscope lens that focuses the laser into the resin. The GT2 has 4 interchangeable objectives (10×, 20×, 25×, 63×). Your choice of objective determines resolution, speed, and compatible materials.

**Overexposure**
When too much laser energy is delivered — the polymerized voxel grows larger than intended, causing features to merge or blur. Fix: reduce laser power or increase scan speed.

---

## P

**PGMEA — Propylene Glycol Monomethyl Ether Acetate**
The primary development solvent for most IP-series resins. Used to wash away uncured resin after printing. Handle in a fume hood — it is a mild irritant.

**Photopolymer**
A material that solidifies when exposed to light. The GT2's resins are photopolymers — specifically two-photon photopolymers, meaning they only react to simultaneous two-photon absorption at the focal point.

**Photoinitiator**
A molecule inside the resin that absorbs the two photons and starts the polymerization chain reaction. Without photoinitiators, the resin would not react to light at all.

**Piezo Scanning**
A high-precision scanning method where the sample stage moves on piezoelectric actuators. Range: 300×300×300 µm. Accuracy: ~10 nm. Slower than galvo but more precise. Used for fine structures.

**Polymer**
A large molecule made of repeating monomer units linked in chains. The solid structure you get after 2PP printing is a polymer network. Properties (stiffness, transparency, biocompatibility) depend on the specific resin used.

---

## R

**Resin / Resist**
Used interchangeably in this guide. The liquid photopolymer material the GT2 prints with. "Resist" comes from the semiconductor industry. "Resin" is more common in 3D printing contexts. Both mean the same thing here.

---

## S

**Scan Speed**
How fast the focal point moves through the resin during printing (µm/s). Higher speed = less exposure time per voxel = lighter polymerization. Lower speed = more exposure = stronger but potentially overexposed structures.

**Slicing**
The process of dividing your 3D model into horizontal layers that the printer can follow one at a time. DeScribe performs slicing when you click "Slice." Slice distance controls layer thickness.

**Slice Distance**
The vertical spacing between adjacent layers. Typical values: 0.3–0.5 µm for 63×, 0.5–1 µm for 25×. Smaller = smoother vertical surfaces, longer print time.

**SPS — Safety Precedence Sequence**
The GT2's laser safety interlock system. If the top hatch is open or any safety condition is not met, the SPS cuts the laser automatically. The green "Process" light indicates the SPS is active and laser could fire.

**STL — Standard Tessellation Language**
The standard file format for 3D models used in 3D printing. Your CAD software exports an STL, which DeScribe then imports for slicing. The surface of your model is represented as a mesh of triangles.

---

## U

**Underexposure**
When too little laser energy is delivered — voxels don't fully polymerize, leading to missing features, weak structures, or complete print failure. Fix: increase laser power or reduce scan speed.

---

## V

**Voxel**
Volume + Pixel = Voxel. The smallest 3D unit the GT2 can write. Shaped like a prolate ellipsoid (like a rugby ball standing upright). Width is the lateral dimension; height is the axial dimension. Everything the GT2 builds is made of overlapping voxels.

---

## W

**WD — Working Distance**
The distance from the front of the objective lens to the focal point inside the sample. Important for knowing how deep into a material you can print. 63× has 360 µm WD; 10× has 700 µm WD.

---

> 🔗 **Next:** [Machine Overview Diagram →](machine_overview_diagram.md)