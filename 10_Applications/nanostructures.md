# Nanostructures

## Why the GT2 Is Used for Nanostructures

The GT2's 63x objective achieves lateral feature sizes of approximately 160 nm — well below the wavelength of visible light and approaching the size of macromolecular assemblies. This resolution opens access to a class of structures whose properties emerge from geometry at the nanoscale: metamaterials, nanophotonic arrays, nanotopography for surface science, and templates for directed self-assembly.

The GT2's advantage over other nanofabrication tools (electron beam lithography, focused ion beam milling) in this regime is its true 3D capability combined with relatively fast throughput. Electron beam lithography is planar; focused ion beam milling is destructive; the GT2 adds material in 3D without removing it or requiring a vacuum chamber.

---

## What Can Be Fabricated

Optical metamaterials: periodic arrays of sub-wavelength structural elements whose collective optical response differs from that of any natural material. The elements are designed to have specific effective permittivity and permeability values, enabling negative refractive index, cloaking, and perfect absorption.

Chiral nanostructures: helical or propeller-shaped elements at sub-micron scale that interact differently with left-handed and right-handed circularly polarized light. Used for chiroptical sensing and polarization control.

Nanotopography arrays: regular arrays of pillars, holes, or surface features with sub-micron dimensions. Used to study cell-surface interactions at the nanoscale, to create superhydrophobic surfaces, or to produce structural color.

Phononic crystals at the sub-micron scale: periodic elastic structures that control acoustic wave propagation at gigahertz frequencies.

Templates for directed self-assembly: sub-micron polymer features that act as chemical or topographic guides for the self-assembly of block copolymers, nanoparticles, or liquid crystals into ordered arrays.

Plasmonic nanostructure templates: polymer masters for gold or silver nanostructure arrays (triangles, bowtie antennas, split rings) fabricated by liftoff or by nanocasting.

---

## Recommended Objective and Resist

The only viable combination for true nanoscale structures: 63x objective with IP-Dip2.

The 25x objective cannot reliably produce features below approximately 1 um. All nanostructure work requires the 63x.

For nanostructures that will be converted to metal or glass after printing (templates): IP-Dip2 is standard. The polymer is a sacrificial or permanent scaffold for the final functional material.

For optical nanostructures that must remain as polymer in the final device: IPX-Clear provides better optical transparency than IP-Dip2, with comparable resolution at the 63x.

---

## Design Considerations

Proximity effect: in any write-based nanofabrication system, closely spaced features expose each other to stray energy from the write process. In 2PP, the tails of the focal volume contribute some polymerization beyond the main voxel. When features are spaced closer than approximately 2 to 3 times the voxel diameter, this proximity exposure can cause unintended polymerization in the gap, merging features that should be separate.

Mitigation: use the minimum laser power that reliably produces solid features. Lower power narrows the effective voxel size and reduces proximity effects. Alternatively, increase feature spacing and accept a coarser array pitch.

Minimum gap for complete development: after printing, gaps between features must be wide enough for PGMEA to penetrate and remove uncured resin. For 63x + IP-Dip2, the minimum developable gap is approximately 300 to 500 nm. Gaps below this value will retain uncured resin after development, merging adjacent features.

Substrate interaction: at very small feature dimensions, the substrate surface chemistry affects polymerization at the lowest voxel layer. Use O2 plasma-treated substrates to ensure clean adhesion of the first layer without residue.

Calibration printing: nanostructure dimensions are more sensitive to laser power variation than larger features. Always print a power calibration array (same geometry at incremental power steps) and characterize under SEM before committing to a full array print.

Stitching for large arrays: large nanostructure arrays (above 400 um in extent) require stage stitching. At nanoscale feature sizes, stitching errors (typically 100 to 200 nm) are comparable to the feature size itself and can create visible discontinuities at tile boundaries. For arrays where uniformity across stitching boundaries is critical, design the array to avoid having structural elements that span a stitching boundary.

---

## Representative Results

IP-Dip2 chiral nanohelices with wire diameter 200 nm and helix radius 350 nm have been fabricated in arrays of thousands of elements, demonstrating circular dichroism of 10 to 20 percent at near-infrared wavelengths after gold coating.

3D optical metamaterial elements (split ring resonators with 300 nm feature size) fabricated in IP-Dip2 and coated with gold have demonstrated magnetic resonance at near-infrared wavelengths.

Nanotopography arrays of pillars with 300 nm diameter, 1 um height, and 500 nm spacing, fabricated in IP-Dip2, have been used to study the alignment and morphology of human corneal cells on sub-wavelength surface features.

IP-Dip2 templates for silver nanotriangle arrays have been used as SERS substrates with single-molecule sensitivity after silver nanocasting.

---

## Limitations

- Throughput: printing nanostructure arrays is slow. A 200 um by 200 um array of 300 nm pillars at 500 nm pitch contains approximately 160,000 pillars and requires several hours of print time on the 63x.
- Characterization requirement: features below 500 nm cannot be resolved by optical microscopy. SEM or AFM is required to verify that nanostructures printed correctly. Build SEM characterization time into your project schedule.
- Stitching uniformity: large uniform nanoarrays are challenging due to stitching discontinuities. For arrays requiring absolute uniformity across large areas, the GT2 is supplemented or replaced by e-beam lithography.

---

Proceed to: soft_structures.md
