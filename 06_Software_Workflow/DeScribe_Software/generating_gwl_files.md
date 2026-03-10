# DeScribe — Generating GWL Files

---

## What Gets Generated

After reviewing the 3D preview and confirming the print time, click Generate (or Export, depending on the DeScribe version) to produce the GWL output files.

DeScribe generates two files:

filename_job.gwl: the master control file. This is the file you open in NanoWrite to start the print. It contains the startup commands, interface finding instructions, scanning mode selection, and an include statement that calls the data file.

filename_data.gwl: the toolpath data file. It contains every single laser coordinate and every parameter change for the entire print. This file can be very large (tens to hundreds of megabytes for complex structures). Do not open or edit this file manually — it is not human-readable in a useful sense.

Both files must always stay in the same folder. If you move them, move them together. If only the job file is transferred to the GT2 computer, NanoWrite will fail because it cannot find the data file when the job file calls it.

---

## Where to Save the Output Files

Save to a dedicated project folder on the GPU workstation. Use the naming convention recommended in installation_and_setup.md. Confirm that both files are present in the output folder before transferring to the GT2 computer.

---

## Transferring to the GT2 Computer

Method 1 — USB flash drive:
Copy both GWL files (and any additional included GWL files, if applicable) to a USB drive. Plug the USB drive into the GT2 control computer. Copy the files to a local folder on the GT2 computer (for example, C:\PrintJobs\YourName\ProjectName\). Eject the USB drive.

Method 2 — Network share:
If a shared network folder is available on both computers, copy the files there from the GPU workstation and access them from the GT2 computer. Confirm the files are fully copied (not still transferring) before opening in NanoWrite.

Do not attempt to run NanoWrite with files still on the USB drive or in a network folder that has intermittent connectivity. File read errors mid-print will corrupt the job.

---

## Verifying the Files Before Loading

On the GT2 computer, open the job file (filename_job.gwl) in a plain text editor (Notepad) and scroll through the first few lines. Confirm:

- The include statement points to the correct data file name
- The data file name matches the actual data file in the same folder
- No path separators or special characters in the file name will cause problems

If the include statement points to a path that does not exist on the GT2 computer (for example, a path on the GPU workstation's C drive), edit the include statement to use just the filename with no path, and confirm both files are in the same folder.

---

Proceed to: multi_print_jobs.md
