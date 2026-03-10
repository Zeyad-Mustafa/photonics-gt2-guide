# IPX-Clear — Optical Applications

---

## Micro-Lenses and Lens Arrays

IPX-Clear's high transparency and smooth surface finish (when printed with the 25x or 63x objective) make it ideal for **micro-optical lenses**:

- **Single plano-convex or bi-convex microlenses** for collimating or focusing light from optical fibers or LEDs
- **Microlens arrays** for light field cameras, wavefront sensors, or uniform illumination
- **Freeform lenses** with aspheric or non-rotationally symmetric profiles — trivial to design in CAD, impossible to fabricate by conventional polishing at micro scale

Achievable lens diameters: 5 um to ~1 mm (print multiple fields for larger arrays).
Surface roughness Ra < 20 nm is achievable with optimized parameters.

Design note: account for IPX-Clear's refractive index (n ~ 1.50) when calculating focal lengths and lens curvatures in your optical design software.

---

## Optical Waveguides

IPX-Clear can serve as the **core material** for optical waveguides when surrounded by a lower-index cladding:

- A printed IPX-Clear waveguide (n ~ 1.50) on a glass substrate (n ~ 1.46-1.52) may or may not achieve total internal reflection depending on the substrate. For best waveguiding, use a substrate with n < 1.50 (e.g., certain specialty glasses, fluoropolymer substrates, or air-clad structures).
- Free-standing waveguide bridges can guide light through air-clad structures (air n = 1.00 — large index contrast).
- Waveguide-to-fiber coupling tapers can be printed to reduce insertion loss when connecting to standard single-mode fiber (SMF-28).

---

## Beam Splitters and Diffractive Optics

- **Cube or plate beam splitters** at micro scale for integrated optical circuits
- **Diffraction gratings** (with the 63x objective): grating periods as small as ~500 nm are achievable, enabling first-order diffraction in the visible spectrum
- **Fresnel lenses**: thinner than refractive lenses, useful where axial space is limited

---

## Photonic Integrated Circuits

In conjunction with optical fibers and photonic chips, IPX-Clear enables printing of **3D photonic wire bonds** — optical connections between chips, fibers, or waveguide ports that cannot be connected by planar lithography alone:

- Coupling optics between photonic chips with different waveguide heights
- Mode converters between different waveguide cross-sections
- Free-space optical paths in 3D between integrated components

---

## Optical Sensing Structures

- **Evanescent field sensors**: waveguides with controlled cladding removal to expose the evanescent field to analytes
- **Whispering gallery mode resonators**: toroidal or spherical resonators printed in IPX-Clear with very smooth surfaces (high Q-factor requires surface roughness < ~10 nm — at the boundary of what the 63x can achieve with optimized parameters)

---

## Related Files

- [overview.md](./overview.md)
- [handling_and_storage.md](./handling_and_storage.md)
- [10_Applications/micro_optics.md](../../10_Applications/micro_optics.md)
- [10_Applications/photonic_devices.md](../../10_Applications/photonic_devices.md)
- [03_Objectives/63x_objective/voxel_dimensions.md](../../03_Objectives/63x_objective/voxel_dimensions.md)