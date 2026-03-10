# GWL Scripting Introduction

---

## What Is GWL

GWL (Gwl Writing Language) is the native scripting language of Nanoscribe GT2 systems. It is the low-level language that NanoWrite executes directly — the equivalent of G-code for a conventional CNC machine or 3D printer.

When you use DeScribe to slice an STL file, DeScribe generates GWL files automatically. However, GWL can also be written directly by hand. This allows complete control over every aspect of the printing process and enables workflows that are impossible or impractical through the DeScribe GUI.

---

## When to Write GWL Directly

Direct GWL scripting is useful when:

- You need to print structures that cannot be defined as a single closed solid (for example, two objects that share no volume but must be printed in one job)
- You need to print the same structure at dozens or hundreds of positions with precise spacing (array printing)
- You need to interleave different laser power or speed settings within a single print
- You are automating a workflow and generating print jobs programmatically from a data file
- You need to include custom stage moves between print segments
- You need to print structures defined by mathematical functions that are easier to express as coordinate lists than as STL solids

---

## Basic GWL Syntax

GWL is a simple line-by-line script. Each line contains one command. Comments begin with a percent sign.

    % This is a comment
    PiezoScanMode                % set piezo scanning mode
    ScanSpeed 25000              % set scan speed to 25000 um/s
    LaserPower 25                % set laser power to 25 percent
    
    % Write a horizontal line from (0,0,0) to (10,0,0)
    MoveStageX 0
    MoveStageY 0
    MoveTo 0 0 0
    LineTo 10 0 0

---

## Core GWL Commands

Movement commands:

| Command | Function |
|---|---|
| MoveTo x y z | Move to coordinates x, y, z with laser OFF |
| LineTo x y z | Move to coordinates x, y, z with laser ON (writes a line) |
| MoveStageX value | Move the coarse stage to absolute X position (in mm) |
| MoveStageY value | Move the coarse stage to absolute Y position (in mm) |
| StageGoToX value | Alternative stage move command (same effect) |
| StageGoToY value | Alternative stage move command (same effect) |

Parameter commands:

| Command | Function |
|---|---|
| ScanSpeed value | Set scan speed in um/s |
| LaserPower value | Set laser power as percent (0 to 100) |
| PiezoScanMode | Switch to piezo scanning (high precision, small range) |
| GalvoScanMode | Switch to galvo scanning (fast, larger range) |
| FindInterfaceAt value | Trigger interface detection at specified Z height |
| AddZDrivePosition value | Offset the Z reference by a given amount |

Structural commands:

| Command | Function |
|---|---|
| include filename.gwl | Include another GWL file (modular scripting) |
| for N | Begin a loop that repeats N times |
| end | End a loop |

---

## Example: Printing a 5x5 Array of Pillars

The following GWL script prints a 5 by 5 array of cylindrical pillars, each 1 um diameter and 5 um tall, spaced 10 um apart.

    % 5x5 pillar array
    % Pillar diameter: 1 um, height: 5 um, spacing: 10 um
    
    PiezoScanMode
    ScanSpeed 20000
    LaserPower 20
    
    for 5
      for 5
        % Write one pillar as a vertical line
        MoveTo 0 0 0
        LineTo 0 0 5
        % Move to next pillar position
        MoveStageX +0.00001  % 10 um in mm
      end
      MoveStageX -0.00005   % reset X, move Y
      MoveStageY +0.00001
    end

Note: This is a simplified example for concept demonstration. Real pillar printing uses a circular hatch pattern for each layer, not a single vertical line. DeScribe-generated GWL contains full hatching for solid fills.

---

## The job.gwl and data.gwl Structure

When DeScribe generates GWL output, it creates two files:

filename_job.gwl: the master control file. It sets scan mode, initial parameters, finds the interface, then calls the data file using an include command. This is the file you open in NanoWrite.

filename_data.gwl: contains all the coordinate data — every single laser move for every layer of your structure. This file is large and should never be edited manually.

When writing custom GWL scripts, you typically write directly in a single job file, or write a master job file that includes multiple data files for different sections of the print.

---

## Modular GWL for Array Printing

The include command allows a single structure to be defined once and repeated at multiple positions:

    % master job file for 3x3 array
    PiezoScanMode
    ScanSpeed 25000
    LaserPower 22
    FindInterfaceAt 5
    
    for 3
      for 3
        include structure.gwl       % print the structure at current position
        StageGoToX +0.1             % move 100 um in X
      end
      StageGoToX -0.3              % reset X
      StageGoToY +0.1              % move 100 um in Y
    end

In this approach, structure.gwl contains the detailed coordinate data for a single instance of the structure. The job file handles positioning and repetition.

---

## Practical Notes for GWL Scripting

Coordinate system: GWL coordinates are in micrometers for piezo mode moves (MoveTo, LineTo) and in millimeters for stage moves (MoveStageX, StageGoToX).

Laser state: the laser fires whenever LineTo is used. The laser is off during MoveTo. Every time you need to reposition without writing, use MoveTo.

Power and speed: you can change LaserPower and ScanSpeed at any point in the script. This allows different regions of a structure to be printed with different parameters — for example, a high-power dense fill for the interior and a low-power fine-detail pass for the shell.

Interface finding: always include a FindInterfaceAt command at the beginning of your script, or call it from the job file. Without it, the Z = 0 reference is undefined and the print will be at an incorrect height.

Testing scripts: test new GWL scripts with LaserPower set to 0 (a dry run). The stage moves but no polymerization occurs. This lets you verify stage positions and timing without wasting resin.

---

Proceed to: design_rules_checklist.md
