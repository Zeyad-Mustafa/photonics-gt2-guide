# DeScribe — Multi-Print Jobs

---

## Printing Multiple Structures in One Job

It is often useful to print more than one structure per substrate — either multiple copies of the same structure, an array of structures at different positions, or several different structures on the same substrate.

There are two approaches: using DeScribe's built-in array function, or writing a custom master GWL script that calls multiple individual job files.

---

## Approach 1 — DeScribe Array Function

DeScribe has a built-in function to create rectangular arrays of a single structure. In the Print Setup or Job Setup panel, look for an Array or Repeat section.

Set:
- Number of structures in X direction
- Number of structures in Y direction
- Spacing between structures in X (micrometers)
- Spacing between structures in Y (micrometers)

DeScribe generates a single job file that prints all instances sequentially, moving the stage between each instance using StageGoTo commands.

This approach is the simplest for regular rectangular arrays of identical structures.

Limitation: all instances use the same parameters. If different structures or different parameters are needed, use approach 2.

---

## Approach 2 — Master GWL Script

For maximum flexibility, write a master GWL script that calls multiple data files and positions each one at specific stage coordinates.

Example master job file for three different structures at different positions:

    % Master job file — three structures
    PiezoScanMode
    ScanSpeed 25000
    LaserPower 22
    
    % Structure 1 at position (0, 0)
    StageGoToX 0
    StageGoToY 0
    FindInterfaceAt 5
    include structure_A_data.gwl
    
    % Structure 2 at position (0.5 mm, 0)
    StageGoToX 0.5
    StageGoToY 0
    FindInterfaceAt 5
    include structure_B_data.gwl
    
    % Structure 3 at position (1.0 mm, 0)
    StageGoToX 1.0
    StageGoToY 0
    FindInterfaceAt 5
    include structure_C_data.gwl

In this approach, each structure has its own data file generated separately by DeScribe, and the master script handles positioning and sequencing.

Note: FindInterfaceAt should be called before each structure if the substrate is not perfectly flat across the full print area. For very flat substrates (silicon wafers), you can find the interface once at the beginning and omit it for subsequent structures, but this only works reliably if height variation across the substrate is less than approximately 5 um.

---

## Spacing Between Structures

When printing multiple structures on one substrate, leave adequate spacing between them:

Minimum spacing to prevent resin contamination: at least 50 um between the edges of adjacent structures. The laser occasionally produces stray exposure at the edges of the scan field — this dead zone is larger at higher power settings.

Practical spacing for easy identification and dicing: 200 to 500 um between structure centers is common in research settings.

Maximum number of structures per substrate: limited by the substrate size (25x25 mm), but practically limited by print time. Confirm total print time for the array before starting.

---

Proceed to: stagegoTo_commands.md
