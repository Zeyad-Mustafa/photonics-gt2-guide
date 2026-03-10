# DeScribe — StageGoTo Commands

---

## What StageGoTo Commands Do

StageGoTo commands move the coarse XY stage of the GT2 to a specific absolute position before starting a print. They allow you to position your structure at a precise location on the substrate, rather than always printing at the default center position.

These commands appear in the job.gwl file, either generated automatically by DeScribe or written manually.

---

## The Two Commands

StageGoToX value: moves the coarse stage to position X = value, in millimeters.
StageGoToY value: moves the coarse stage to position Y = value, in millimeters.

Both commands move to absolute positions, not relative offsets. If you want to move 0.5 mm to the right of the current position, you must know the current absolute position and add 0.5 to it.

---

## Coordinate System

The GT2 stage coordinate system has its origin (0, 0) at the default print position — typically the center of the substrate holder. Positive X is to the right, positive Y is away from the operator, when facing the machine from the front.

Stage positions are in millimeters. A move of 1.0 in StageGoToX moves the stage 1 mm = 1000 um in X.

---

## How to Edit StageGoTo Commands in the Job File

After generating GWL files in DeScribe, open the job file (filename_job.gwl) in a plain text editor (Notepad or similar). Find the StageGoToX and StageGoToY lines near the top of the file. Edit the values to position the print at your desired location.

Example: to print a structure 2 mm to the right of center and 1 mm above center:

    StageGoToX 2.0
    StageGoToY 1.0

Save the file after editing. The edited file is ready to load in NanoWrite.

---

## Using StageGoTo for Alignment to Existing Features

If your substrate has existing structures (from a previous print or from photolithography) and you need to align the new print to them, use the following procedure:

Step 1: Load the substrate in the GT2 and open NanoWrite.
Step 2: Use the manual stage controls in NanoWrite to navigate to the alignment feature on the substrate (use the AxioVision camera to locate it).
Step 3: Note the XY stage position shown in NanoWrite when the alignment feature is centered in the camera view.
Step 4: Calculate the required StageGoToX and StageGoToY values to position the print at the desired offset from this alignment feature.
Step 5: Edit the job file with the calculated values.
Step 6: Proceed with the print.

Alignment accuracy using this manual method is typically 2 to 5 um. For tighter alignment requirements, consult your facility's advanced alignment procedures.

---

Proceed to: common_errors.md
