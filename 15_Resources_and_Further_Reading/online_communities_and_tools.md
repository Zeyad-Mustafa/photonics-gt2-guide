# Online Communities and Tools

## Overview

This file lists practical online resources — forums, repositories, software tools, and communities — that are useful during day-to-day GT2 work. Academic literature tells you what is possible; these resources help you make it work.

---

## Nanoscribe User Community

Nanoscribe Customer Portal Forum
URL: accessible through https://www.nanoscribe.com (requires account)

The customer portal includes a user forum where GT2 operators from institutions worldwide share parameter sets, troubleshooting solutions, and workflow tips. This is the most targeted community for GT2-specific questions. Before spending several sessions debugging a parameter or compatibility problem, search the forum — someone has likely encountered the same issue.

Topics regularly discussed in the forum:
- Parameter optimization for specific resins and objectives
- Interface detection problems and solutions
- GWL scripting tips and shared scripts
- Substrate preparation methods
- Secondary fabrication integration (ALD, electrodeposition, etc.)

---

## ResearchGate

URL: https://www.researchgate.net

Search for "Nanoscribe" or "two-photon polymerization" to find papers, ask questions of authors directly, and follow researchers active in the field. ResearchGate allows direct messaging to paper authors, which is useful when a paper's methods section is ambiguous about a specific parameter or procedure.

---

## CAD and Design Tools

OpenSCAD
URL: https://openscad.org
License: free, open source

Script-based parametric CAD. Ideal for periodic structures (photonic crystals, arrays, lattices) defined by mathematical functions. The OpenSCAD forum and documentation wiki are active and comprehensive. Search the Thingiverse library (https://www.thingiverse.com) for community-shared OpenSCAD scripts that may serve as starting points for your geometry.

---

Autodesk Fusion 360
URL: https://www.autodesk.com/products/fusion-360
License: free for students and educators, paid for commercial

Full-featured parametric CAD with a large online community. The Fusion 360 forum (forum.autodesk.com) is very active. For GT2-specific workflows, search the forum for STL export settings and mesh quality discussions.

---

FreeCAD
URL: https://www.freecad.org
License: free, open source

Open-source parametric CAD with a growing community. The FreeCAD forum (forum.freecad.org) is active for support questions.

---

## STL Repair and Mesh Tools

Meshmixer (Autodesk)
URL: https://www.meshmixer.com
License: free

The most capable free mesh repair and editing tool. Use the Inspector tool to identify and repair non-manifold geometry, open boundaries, and inverted normals before importing STL files into DeScribe. The Meshmixer tutorial page (meshmixer.com/learn.html) covers the most relevant operations for GT2 users.

---

Microsoft 3D Builder
URL: built into Windows 10 and 11
License: free (Windows only)

The fastest way to check and repair STL files on Windows. Drag and drop an STL file onto 3D Builder and it automatically identifies and offers to repair geometry errors. Sufficient for most common STL problems.

---

Netfabb (Autodesk)
URL: https://www.autodesk.com/products/netfabb/overview
License: free cloud version available at netfabb.autodesk.com

Upload an STL and receive a repaired file. The online version handles most repair tasks without requiring software installation.

---

## Python Tools for GWL and STL Generation

numpy-stl
URL: https://pypi.org/project/numpy-stl
Installation: pip install numpy-stl

Python library for reading, writing, and manipulating STL files using numpy arrays. Useful for generating STL files programmatically from mathematical functions or data arrays without using CAD software.

---

trimesh
URL: https://trimesh.org
Installation: pip install trimesh

Powerful Python library for 3D mesh processing. Supports STL, OBJ, PLY, and other formats. Includes mesh repair, boolean operations, cross-sectioning, and watertightness checking. More capable than numpy-stl for complex geometry operations.

---

SciPy and NumPy
URL: https://scipy.org and https://numpy.org

The standard Python scientific computing stack. Used for generating coordinate arrays, defining surface geometries mathematically, and computing optimal helix parameters, lens profiles, and scaffold geometries before passing them to STL generation libraries.

---

## Visualization and Characterization Tools

Fiji (ImageJ distribution)
URL: https://fiji.sc
License: free, open source

The standard tool for microscopy image analysis. Used for analyzing optical microscope images of printed structures — measuring dimensions, characterizing surface uniformity, and processing fluorescence images of cell-seeded scaffolds. The Fiji plugin ecosystem covers 3D reconstruction from Z-stack images, which is useful for characterizing internal structure of scaffolds.

---

Gwyddion
URL: https://gwyddion.net
License: free, open source

The standard tool for analyzing SPM (scanning probe microscopy) and AFM data. Used for characterizing surface roughness of printed optical elements. Calculates Ra, Rq, and other roughness parameters from AFM images.

---

## Simulation Tools

COMSOL Multiphysics
URL: https://www.comsol.com
License: paid, typically available through institutional site license

The most commonly used simulation platform for GT2 application design. Relevant modules: Ray Optics (for micro-optical design), Wave Optics (for waveguides and photonic devices), Structural Mechanics (for MEMS and mechanical structures), and Microfluidics (for channel flow design). Learning COMSOL simulation alongside GT2 fabrication dramatically reduces the number of trial prints needed to arrive at a working design.

---

Lumerical FDTD
URL: https://www.lumerical.com
License: paid

The standard finite-difference time-domain simulation tool for photonic device design. Used for modeling photonic crystals, waveguides, resonators, and plasmonic structures before fabrication. Lumerical's online knowledge base and community forum are extensive.

---

MATLAB
URL: https://www.mathworks.com
License: paid, widely available through institutional license

Widely used for optical simulation (using the Beam Propagation Method or ray tracing), mechanical structure analysis, and data processing of characterization results. The MATLAB File Exchange (mathworks.com/matlabcentral/fileexchange) includes many community-contributed scripts for optical simulation, STL generation, and GWL file writing.

---

## Version Control for GWL Scripts and CAD Files

Git and GitHub
URL: https://git-scm.com and https://github.com

GWL scripts are text files and are fully compatible with version control using Git. Using Git for your GWL scripts and OpenSCAD design files allows you to track changes, revert to previous parameter sets, and collaborate with colleagues on shared designs. This is strongly recommended for any project involving iterative parameter optimization over many sessions.

Basic workflow:
- Initialize a Git repository in your project folder
- Commit after each session with a message describing what you changed and why
- Tag commits that correspond to successful prints for easy reference
