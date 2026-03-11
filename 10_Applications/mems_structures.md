# MEMS Structures

## Why the GT2 Is Used for MEMS Fabrication

Conventional MEMS (micro-electro-mechanical systems) fabrication relies on surface micromachining and bulk micromachining of silicon — processes that are powerful but require cleanroom photolithography, multiple deposition and etch steps, and weeks of processing time. Geometry is essentially limited to 2D extruded shapes defined by photomask patterns.

The GT2 enables 3D MEMS-like structures — springs, cantilevers, membranes, resonators, and actuators — in a single print session with no masks, no wet chemistry beyond development, and no specialized cleanroom equipment. The design cycle is reduced from weeks to hours.

The tradeoff is material: GT2 structures are polymer-based, not silicon or metal. Polymer MEMS has different stiffness, lower electrical conductivity, and different thermal properties than silicon MEMS. However, for applications where these differences are acceptable — or where the polymer is used as a template for subsequent metallization — the GT2 is a powerful prototyping and fabrication tool.

---

## What Can Be Fabricated

Cantilevers: single-clamped beams ranging from a few microns to several hundred microns in length. Used as force sensors, atomic force microscope probes, and biological sensors. The GT2 can print cantilevers with integrated tip features (pyramidal or conical tips) for contact measurement applications.

Springs and flexures: coiled springs, serpentine flexures, and leaf springs for mechanical energy storage and force-displacement conversion. 3D coil springs with sub-10 um wire diameter are achievable with the 25x objective.

Membranes: thin suspended films over a cavity or opening. Used as pressure sensors, acoustic sensors, and microfluidic actuators. Minimum membrane thickness of approximately 1 um with the 63x objective.

Hinges and joints: rotating or folding joints for origami-like 3D assembly or for devices that fold after printing.

Resonators: structures designed to vibrate at a specific mechanical resonance frequency for mass sensing, inertial sensing, or signal filtering.

Micro-grippers: compliant mechanisms that grip and release objects at the microscale. Used in microassembly and cell manipulation.

Interdigitated comb drives (template): the polymer comb structure can be used as a template for metal deposition, producing functional electrostatic comb drive actuators after metallization.

---

## Recommended Objective and Resist

Standard MEMS workflow: 25x objective with IP-S.

IP-S is preferred because:
- Relatively high Young's modulus (approximately 1.5 to 2.5 GPa after UV cure) suitable for spring and cantilever applications
- Low shrinkage reduces residual stress in suspended structures
- Good surface finish for tribological applications

For the highest resolution mechanical structures (sub-micron wire springs, nanoscale cantilevers): 63x objective with IP-Dip2.

For flexible or compliant structures that must deform significantly without fracture: 25x objective with IP-PDMS (much lower Young's modulus, approximately 1 to 5 MPa).

---

## Mechanical Properties of IP-Series Resins

Understanding the mechanical properties of the printed material is essential for MEMS design.

| Property | IP-S (typical) | IP-Dip2 (typical) | IP-PDMS (typical) |
|---|---|---|---|
| Young's modulus | 1.5 to 2.5 GPa | 1.0 to 2.0 GPa | 1 to 5 MPa |
| Tensile strength | 30 to 60 MPa | 20 to 50 MPa | 1 to 5 MPa |
| Elongation at break | 3 to 8 percent | 3 to 6 percent | 50 to 200 percent |
| Density | approximately 1.2 g/cm cubed | approximately 1.2 g/cm cubed | approximately 1.05 g/cm cubed |

Values are approximate and depend on laser parameters, UV cure duration, and resin lot. Measure mechanical properties from test specimens printed under your specific conditions for any application requiring precise stiffness values.

---

## Design Considerations

Stress in suspended structures: polymer MEMS structures are printed in a state of residual stress due to polymerization shrinkage. Suspended structures (cantilevers, membranes) may deflect out of plane after development due to this stress. Minimize residual stress by:
- Using IP-S (lowest shrinkage resin)
- Printing symmetric cross-sections where possible
- Designing thick anchor regions relative to the suspended feature

Anchor design: the anchor (the region that connects the suspended structure to the substrate) must be wide enough to prevent stress concentration and fracture at the clamping point. Design the anchor-to-beam width ratio to be at least 3:1.

Clearance for release: suspended structures must clear the substrate surface. Design a gap between the bottom of the suspended structure and the substrate of at least 5 um (for 25x) to ensure complete development of the undercut region.

Metallization for electrical functionality: bare IP-series polymers are electrical insulators. For electrically active MEMS devices, coat the printed structure with a conductive metal layer by PVD (see secondary_fabrication.md). A conformal gold or platinum coating 50 to 100 nm thick provides electrical conductivity while minimally affecting mechanical stiffness.

Resonance frequency estimation: for a simple cantilever beam, the fundamental resonance frequency is:

f = (1 / 2 pi) times the square root of (k / m)

where k is the spring constant (E times I divided by L cubed, for a rectangular beam with Young's modulus E, second moment of area I, and length L) and m is the effective mass. Use these estimates to verify your design before printing.

---

## Representative Results

Polymer cantilevers with integrated metal coating used as electrochemical sensors with sub-nanomolar detection limits have been demonstrated using 25x + IP-S followed by gold PVD.

3D micro-coil springs with wire diameter 3 um and spring constant below 0.01 N/m, used for cell stiffness measurements, have been printed with the 63x + IP-Dip2.

Compliant micro-grippers actuated by swelling in aqueous solution, printed in IP-PDMS, have demonstrated repeatable gripping of 10 um diameter objects.

Polymer mechanical metamaterials with programmable negative Poisson ratio, printed in IP-S with shell and scaffold mode, have demonstrated auxetic deformation behavior under compression.

---

## Limitations

- Electrical conductivity: bare polymer is insulating. Add metal coating for electrical function.
- Temperature stability: IP-series polymers begin to soften above approximately 100 to 120 degrees C. Not suitable for high-temperature MEMS applications.
- Long-term stability: polymer creep under sustained load can change the mechanical response of springs and membranes over time. For applications requiring long-term dimensional stability, characterize creep behavior under your specific loading conditions.
- Fatigue: polymer MEMS structures subjected to repeated cyclic loading have limited fatigue life compared to silicon or metal. Characterize fatigue behavior if your application involves oscillating loading.

---

Proceed to: biomedical.md
