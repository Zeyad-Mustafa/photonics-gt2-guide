# Photonic Devices

## Why the GT2 Is Used for Photonic Devices

Photonic devices control light at length scales comparable to or smaller than the wavelength of light. Fabricating these devices requires sub-wavelength feature sizes, smooth surfaces, and precise 3D geometry — requirements that match the GT2's capabilities closely.

The GT2 is particularly powerful for 3D photonic structures, which are extremely difficult or impossible to fabricate by conventional planar lithography. 3D photonic crystals, coupled waveguide arrays, and multi-layer photonic circuits all benefit from the GT2's true 3D capability.

---

## What Can Be Fabricated

Optical waveguides: ridge waveguides, strip waveguides, and buried waveguides that guide light by total internal reflection. The refractive index of cured IP-series resins (approximately 1.50 to 1.51) is higher than that of most substrates and ambient air, enabling waveguiding by index contrast.

Waveguide couplers and splitters: Y-junctions, directional couplers, and multimode interference (MMI) splitters that divide or combine optical power between waveguides.

Photonic crystal structures: periodic dielectric structures with lattice constants on the order of the optical wavelength. The 63x objective achieves the sub-500 nm feature sizes required for photonic crystals in the visible and near-infrared spectrum.

Optical resonators: ring resonators, disk resonators, and Fabry-Perot cavities that store optical energy at specific resonance frequencies. Used for sensing, filtering, and nonlinear optics.

3D photonic circuits: multi-layer waveguide networks with vertical interconnects, enabling 3D optical routing not possible with planar technology.

Grating couplers: periodic surface structures on waveguide surfaces that couple free-space light into guided modes. Period and duty cycle must be controlled to better than 100 nm — within the 63x capability.

Optical fiber coupling elements: mode converters, spot size converters, and tapers printed at fiber end faces or on chip surfaces adjacent to fiber attachment points.

Plasmonic templates: periodic metal nanostructure arrays for surface-enhanced Raman scattering (SERS), extraordinary optical transmission, and biosensing. The polymer template is printed and then coated with gold by PVD or used as a lift-off mask.

---

## Recommended Objective and Resist

For sub-wavelength photonic structures (photonic crystals, gratings, resonators with features below 500 nm): 63x objective with IPX-Clear or IP-Dip2.

IPX-Clear is generally preferred for photonic devices because its very high optical transparency (above 90 percent through the visible and near-IR) minimizes propagation loss in waveguides. IP-Dip2 has slightly higher transparency variation across the visible spectrum.

For larger photonic structures (waveguides above 2 um wide, large-scale photonic circuits): 25x objective with IPX-Clear or IP-S.

---

## Design Considerations

Refractive index: the refractive index of cured IPX-Clear and IP-Dip2 is approximately 1.50 to 1.52 at 780 nm, decreasing slightly at longer visible wavelengths. For accurate mode simulation and dispersion calculation, measure the refractive index of your specific resin using an ellipsometer or prism coupler on a test sample under your exact printing conditions.

Waveguide single-mode condition: for single-mode operation at a given wavelength, the waveguide cross-section must be below the cutoff dimension for higher-order modes. For a strip waveguide with n approximately 1.51 on a silica substrate (n = 1.46), the single-mode condition at 1550 nm wavelength requires width below approximately 3 um. Design accordingly.

Surface roughness and propagation loss: sidewall roughness of GT2-printed waveguides is the primary source of scattering loss. With optimal printing parameters (fine slice and hatch distance, low laser power), sidewall roughness of 5 to 15 nm Ra is achievable, corresponding to propagation losses of approximately 1 to 5 dB/cm at 1550 nm. This is acceptable for short devices (a few mm) but limits use in long waveguide applications.

Photonic crystal lattice design: the bandgap wavelength of a photonic crystal scales with the lattice constant. For a bandgap in the visible spectrum (500 to 700 nm wavelength), the lattice constant must be 200 to 400 nm — accessible with the 63x objective. For near-infrared bandgaps (1300 to 1550 nm), lattice constants of 400 to 700 nm are needed, also within 63x capability.

---

## Representative Results

Polymer optical waveguides with propagation loss of 1.5 dB/cm at 1550 nm have been printed in IPX-Clear using the 25x objective and directly coupled to standard single-mode fiber.

3D woodpile photonic crystal structures with complete photonic bandgap at near-infrared wavelengths have been fabricated in IP-Dip2 using the 63x objective, with rod diameter 300 nm and period 800 nm.

Optical ring resonators with quality factors above 5000 at 1550 nm have been demonstrated in IPX-Clear, fabricated with the 25x objective.

Freeform waveguide arrays for spatial multiplexing of optical signals, with 3D routing between layers, have been printed in IP-S and characterized by near-field imaging.

Gold nanostructure arrays for SERS, fabricated by printing IP-Dip2 templates on ITO glass and coating with 50 nm gold by PVD, have demonstrated enhancement factors above 10 to the 6th power for Raman spectroscopy.

---

## Limitations

- Propagation loss: polymer waveguides have higher loss than silicon or silica waveguides. For applications requiring loss below 0.5 dB/cm, consider using the GT2 to define the geometry and then converting to a lower-loss material by ALD coating.
- Thermal sensitivity: the refractive index of polymer changes with temperature (dn/dT approximately minus 10 to the minus 4 per degree C, larger in magnitude than glass). Temperature variations of a few degrees will shift resonator wavelengths by several nanometers — significant for narrow-linewidth devices.
- Long-term stability: polymer photonic devices may drift in performance over months due to slow continued polymerization, absorption of atmospheric moisture, or oxidation. Characterize temporal stability for your specific application.

---

Proceed to: micro_robotics.md
