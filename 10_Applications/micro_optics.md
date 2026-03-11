# Micro-Optics

## Why the GT2 Is Used for Micro-Optics

Micro-optical elements are among the most demanding applications for any fabrication technology. A lens or beam shaper works by controlling the phase and amplitude of a wavefront across its aperture. Any deviation from the designed surface profile — roughness, form error, subsurface damage — directly degrades optical performance. The GT2 produces surfaces with roughness below 10 nm Ra and can realize freeform 3D surfaces that are impossible to fabricate by conventional grinding and polishing or by standard photolithography.

The combination of smooth surfaces, true 3D capability, and the ability to print directly on optical substrates (quartz, silicon, glass) makes the GT2 the primary tool for prototyping and small-batch production of micro-optical elements in research environments.

---

## What Can Be Fabricated

Spherical and aspherical microlenses: single lenses from 10 um to several hundred um in diameter, with controlled radius of curvature and conic constant. Used in imaging systems, fiber coupling, and laser beam shaping.

Freeform lenses: lenses with non-rotationally-symmetric surface profiles defined by Zernike polynomials or numerical optimization. Used for aberration correction, light field cameras, and augmented reality applications.

Microlens arrays: regular or irregular arrays of lenses on a common substrate. Used for light homogenization, wavefront sensing (Shack-Hartmann sensors), integral imaging, and display applications.

Diffraction gratings: periodic surface structures with periods from approximately 500 nm (63x objective) to several microns. Used for spectroscopy, wavelength division multiplexing, and structural color.

Axicons: conical lenses that produce Bessel beams. The cone angle controls the Bessel beam ring radius.

Beam shapers: freeform optical elements that convert Gaussian beams to flat-top, donut, or other profiles.

Fiber tip optics: lenses printed directly onto the cleaved end face of an optical fiber. The fiber tip is placed in the GT2, aligned to the fiber core, and the lens is printed in-situ on the fiber end.

Gradient index (GRIN) optics: by modulating laser power across the voxel field, the local degree of polymerization and therefore the local refractive index of the printed volume can be varied, producing a gradient index element without any physical surface curvature.

---

## Recommended Objective and Resist

Primary combination: 63x objective with IPX-Clear or IP-Dip2.

IPX-Clear is preferred for most optical applications because:
- Very high transparency across the visible spectrum (above 90 percent transmission)
- Low autofluorescence suitable for fluorescence microscopy integration
- Compatible with the 63x, 25x, and 10x objectives depending on lens size

IP-Dip2 is used when the highest possible surface resolution is required (sub-200 nm features) or when the lens diameter is small enough that the 63x print volume is adequate.

For larger lenses (diameter above 500 um), the 25x objective with IP-S or IPX-Clear provides better throughput at acceptable surface quality.

---

## Design Considerations

Surface profile accuracy: the GT2 prints discrete voxels, so curved surfaces are approximated by a staircase of voxels. The step height is the axial voxel size (approximately 500 nm for the 63x). For smooth optical surfaces, use the finest slice distance (0.3 um) and the smallest hatch distance (0.2 um) available for the 63x. Post-processing with a reflow step (brief thermal treatment that softens and smooths the surface) can further reduce roughness for some applications.

Orientation: for a plano-convex lens, orient the flat base toward the substrate (Z = 0) and the convex surface facing up. The upward-facing surface is printed layer by layer from the edge up to the apex, and its roughness is determined by the lateral voxel size, which is smaller than the axial voxel size.

Shrinkage compensation: lens profiles are extremely sensitive to dimensional error. A lens designed with a 500 um radius of curvature that shrinks 10 percent in Z will have a 550 um radius — a 10 percent change in focal length. Always apply shrinkage compensation (scale Z by 1.10 to 1.15) and calibrate with test lenses before committing to a final design.

Substrate matching: for transmission optics, print on quartz (fused silica) substrates. The refractive index of IP-Dip2 (1.511) and IPX-Clear (approximately 1.50) are well-matched to borosilicate glass but differ from fused silica (1.457), introducing a small reflection at the lens-substrate interface. For the most demanding applications, design the lens profile to account for this interface.

---

## Representative Results

Fiber tip microlenses with numerical aperture up to 0.5 and coupling efficiency above 90 percent have been demonstrated by printing IP-Dip2 lenses directly onto single-mode fiber end faces using the 63x objective.

Microlens arrays with 100 um pitch and form error below 50 nm have been fabricated on silicon substrates for wavefront sensing applications.

Freeform beam shapers converting Gaussian to flat-top profiles with uniformity better than 5 percent have been demonstrated in IPX-Clear using the 25x objective.

Gradient index elements with refractive index variation of up to 0.01 have been produced by modulating laser power during printing of IP-Dip2.

---

## Limitations

The GT2 is not suited for:
- High-volume production — print times limit throughput to a few elements per hour
- Large aperture optics above approximately 5 mm diameter — use injection molding or diamond turning for these
- Flat-field lithographic elements (use photolithography or e-beam instead)
- Infrared optics — IP-series resins absorb at wavelengths above approximately 2 um

---

Proceed to: microfluidics.md
