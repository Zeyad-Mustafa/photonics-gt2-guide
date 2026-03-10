# IP-Visio — Biological Applications

> This file describes the main application areas for IP-Visio-printed structures in biomedical research and life sciences.

---

## 3D Cell Scaffolds

The most common application of IP-Visio is printing **3D scaffolds for cell culture**. These are open lattice structures with controlled pore sizes and geometries that:

- Allow cells to attach and grow in three dimensions (rather than flat on a Petri dish)
- Mimic the extracellular matrix (ECM) geometry found in real tissue
- Enable researchers to study cell migration, differentiation, and behavior in a 3D microenvironment

Design considerations for cell scaffolds:
- Pore size: typically 20-200 um for most mammalian cell types
- Strut diameter: minimum ~2-5 um (limited by 25x voxel size)
- Surface topology: IP-Visio's smooth surfaces are favorable for cell attachment
- Height: limited by 25x build volume (~800 um max in Z with stitching)

After printing and development, scaffolds are typically:
1. UV cured
2. Sterilized (UV irradiation, ethanol wash, or autoclave — confirm compatibility)
3. Surface functionalized if required (plasma treatment, protein coating)
4. Seeded with cells and placed in culture medium

---

## Microfluidic Devices for Biology

IP-Visio can be used to print **microfluidic channels and chambers** that carry biological fluids, cells, or reagents. Advantages over PDMS soft lithography:

- Complex 3D channel geometries not achievable by standard molding
- No manual alignment of layers
- Single-step fabrication of integrated valves, mixers, and chambers
- Sub-10 um channel widths achievable with the 25x objective

Channel cross-sections as small as 5 x 5 um are achievable. For larger channels (> 200 um), IP-Q with the 10x objective is faster.

Note: Microfluidic devices require bonding to a flat substrate (e.g., PDMS slab, glass coverslip) after printing to seal the channels. IP-Visio structures can be bonded with oxygen plasma treatment.

---

## Drug Delivery Structures

IP-Visio can be used to fabricate **micro-carriers and release structures** for controlled drug delivery research, including:

- Hollow capsules with defined wall thickness and pore size
- Degradation-rate-controlled shells (IP-Visio does not degrade in physiological conditions without modification — typically used as a non-degradable control material)
- Scaffolds loaded with drug-containing hydrogels after printing

---

## Tissue Engineering Scaffolds

For tissue engineering applications requiring a 3D printed template:

- IP-Visio structures can serve as a template onto which biological materials (hydrogels, ECM proteins, cells) are added
- The optical clarity of IP-Visio allows transmitted and fluorescence imaging through the structure without significant background

---

## Fluorescence Microscopy Compatibility

IP-Visio's very low autofluorescence makes it compatible with:

- GFP (excitation ~488 nm, emission ~510 nm)
- mCherry (excitation ~587 nm, emission ~610 nm)
- DAPI (excitation ~360 nm, emission ~460 nm)
- Most standard fluorescent dyes and proteins

IP-S and IP-Q have enough autofluorescence background that they can obscure weak fluorescent signals. If your experiment involves fluorescence imaging of structures or cells on/in IP-based scaffolds, IP-Visio is the only standard resist suitable for this use.

---

## Related Files

- [overview.md](./overview.md)
- [handling_and_storage.md](./handling_and_storage.md)
- [10_Applications/biomedical.md](../../10_Applications/biomedical.md)