# Microfluidics

## Why the GT2 Is Used for Microfluidics

Conventional microfluidic device fabrication relies on soft lithography — a process that requires a photolithography step to define a 2D master mold, followed by PDMS casting, bonding, and testing. This process takes days to weeks for a single design iteration and produces only planar (2D extruded) channel geometries.

The GT2 eliminates the photolithography step entirely and enables true 3D microfluidic geometries — channels that curve in three dimensions, overpass junctions without contact, helical mixers, and gradient structures — all in a single print session. Design-to-device time is reduced from weeks to hours.

This speed of iteration is the GT2's primary contribution to microfluidics research. It does not replace mass-production soft lithography for high-volume device manufacturing, but it is transformative for research and development.

---

## What Can Be Fabricated

Straight and curved microchannels: channels from approximately 5 um to 500 um in cross-section, with circular, rectangular, or freeform profiles.

3D channel networks: channels that cross over and under each other, spiral geometries, branching networks, and Y-junctions — all impossible with standard planar photolithography.

Passive mixers: herringbone grooves on channel walls (chaotic advection mixers), helical channel mixers, and split-and-recombine mixers. The GT2 can print the herringbone groove features directly on the channel wall without a separate lithography step.

Droplet generators: T-junctions and flow-focusing devices for generating monodisperse droplets. Channel width at the junction point controls droplet size.

Gradient generators: serpentine networks that produce concentration gradients across a channel width. Used for chemotaxis assays and drug screening.

Filters and sieves: structures with controlled pore size printed across a channel to filter particles by size. Minimum pore size approximately 2 um with the 25x objective or 500 nm with the 63x.

Valves: geometry-defined passive valves (check valves, capillary stop valves) printed as part of the channel network.

Integrated optics and microfluidics: optical waveguides or lenses printed adjacent to or crossing a microfluidic channel, enabling on-chip optical sensing.

---

## Recommended Objective and Resist

Standard microfluidic workflow: 25x objective with IP-S.

IP-S is preferred because:
- Low shrinkage (approximately 5 percent) ensures channels maintain their designed dimensions
- Good mechanical stiffness allows the channel walls to withstand fluid pressure without deformation
- Compatible with aqueous solutions and most biological buffers
- Transparent in the visible spectrum, allowing optical access to the channel interior

For biocompatible devices that will contact cells or biological samples: use IP-Visio with the 25x objective. IP-Visio has lower autofluorescence and has passed biocompatibility testing.

For flexible microfluidic devices (deformable channels, peristaltic pumping): use IP-PDMS with the 25x objective.

For high-resolution microfluidic features below 2 um: use the 63x objective with IP-Dip2 or IPX-Clear.

---

## Design Considerations

Channel sealing: the GT2 prints open-top channels by default (the top of the channel is open because the laser writes from the bottom up and the channel ceiling is the last surface printed). Sealing the channels requires a separate step: bonding a flat cover substrate to the top of the printed device using O2 plasma bonding (see oxygen_plasma_treatment.md).

Alternatively, design fully enclosed channels in the CAD model — the ceiling is included in the solid. These will print with the ceiling formed by the upper layers of the print, but require adequate development time to clear the liquid resin from inside the enclosed volume.

Minimum channel dimension: for channels that must be developable (liquid resin removed from the interior), the minimum cross-sectional dimension must be large enough for PGMEA to diffuse through. In practice, channels below 2 um in width are very difficult to fully develop with the 25x objective.

Aspect ratio of channels: channels with a height-to-width ratio above approximately 5:1 are at risk of wall collapse during development and drying. Design channel aspect ratios below 5:1 where possible, or use critical point drying for high-aspect-ratio channels.

Inlet and outlet ports: design ports as vertical openings through the substrate-facing surface of the device. These connect to tubing or reservoirs for fluid delivery. Port diameter must be large enough to insert the tubing or pipette tip used for fluid introduction (typically 500 um to 1 mm diameter for standard microfluidic tubing).

Surface wettability: IP-series polymers are hydrophobic by default. For aqueous microfluidics, apply O2 plasma for 30 to 60 seconds before use to render the channel walls hydrophilic. This treatment is temporary (24 to 48 hours) and must be repeated before each use if the device is stored.

---

## Integration With Soft Lithography

For applications that require many copies of a device, print one GT2 master and use it as a mold for soft lithography:

1. Print the GT2 structure (positive relief of the channel network)
2. UV cure and apply release agent (fluorosilane vapor treatment)
3. Cast PDMS over the master, degas, and cure at 60 degrees C
4. Peel off PDMS replica — this is the negative (channel mold)
5. Bond PDMS channel layer to a flat substrate by O2 plasma bonding
6. The GT2 master can be reused many times

This hybrid approach combines the GT2's rapid prototyping capability with the high-volume replication ability of soft lithography.

---

## Representative Results

3D serpentine mixers with helical channel geometry achieving 95 percent mixing efficiency at low Reynolds number have been printed in IP-S and characterized by fluorescence microscopy.

Droplet generators producing monodisperse droplets with coefficient of variation below 3 percent have been fabricated using 25x + IP-S, with channel widths of 50 um at the junction.

Integrated waveguide-microfluidic sensors using IPX-Clear waveguides adjacent to IP-S channels have demonstrated on-chip absorbance measurement.

Cell culture devices with 3D porous scaffolds integrated into a microfluidic network have been fabricated in IP-Visio for perfused 3D cell culture studies.

---

## Limitations

- High-volume production: the GT2 is for research and prototyping. For production quantities, convert the GT2 master to a soft lithography workflow.
- Channel sealing: fully enclosed channels require long development times and careful design. Simpler to design open-top channels and bond a cover.
- Material choice: IP-series polymers are not compatible with all organic solvents used in chemistry applications. Test chemical compatibility before using the GT2 device in organic solvent streams.

---

Proceed to: mems_structures.md
