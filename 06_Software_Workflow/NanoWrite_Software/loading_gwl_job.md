# NanoWrite — Loading and Running a GWL Job

---

## Loading the Job File

After a successful interface detection, load your GWL job file:

Step 1 — In NanoWrite, go to File > Open Job (or click the Open Job button in the toolbar).

Step 2 — Navigate to the folder where you copied the GWL files from the GPU workstation. Select the job file (filename_job.gwl). Do not select the data file directly — always open the job file, which calls the data file automatically.

Step 3 — NanoWrite reads the job file and displays a summary of the print parameters: scan mode, laser power, estimated print time, and structure bounding box. Review these values and confirm they match your DeScribe settings.

---

## Confirming Settings Before Starting

Before clicking Start, verify:

Scan mode matches your objective: piezo scan mode for the 63x and 25x (high precision), galvo mode for the 10x (fast large-area). If the mode is wrong, the stage range will be incorrect and the print will fail.

Laser power is within the expected range: if the power shown is wildly different from what you set in DeScribe, the job file may have been corrupted or is from a different session.

Estimated print time is reasonable: cross-check against what DeScribe showed. They should match within a few percent.

Z = 0 reference is set: confirm that interface detection completed successfully before this step. If Z = 0 was not set, the print will start at an incorrect height.

---

## Starting the Print

Click Start (or Run Job). NanoWrite will execute the GWL script sequentially. The stage will begin moving, the laser will fire, and the print will proceed automatically.

Do not interact with NanoWrite or the computer during printing unless monitoring or responding to an error. Mouse clicks or keyboard input can occasionally interrupt the print in some NanoWrite versions.

---

## Pausing and Stopping

To pause: click Pause in NanoWrite. The laser stops and the stage holds its position. Use pause sparingly — pausing for extended periods can cause resin near the focal point to thermally relax, sometimes resulting in a visible discontinuity in the structure at the pause point.

To stop: click Stop or Abort. The laser stops immediately and the stage returns to the home position. The partial structure on the substrate is not automatically discarded — you can choose to develop and inspect the partial print.

Do not stop a print unless necessary. Restarting partway through is complex and usually not reliable.
