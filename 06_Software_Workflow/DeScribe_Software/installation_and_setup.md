# DeScribe — Installation and Setup

---

## System Requirements

DeScribe requires a computer with a dedicated GPU (graphics processing unit). It does not run acceptably on computers with integrated graphics only.

Minimum specifications:
- Operating system: Windows 10 or Windows 11 (64-bit)
- RAM: 16 GB minimum, 32 GB recommended for large models
- GPU: NVIDIA or AMD dedicated graphics card with at least 4 GB VRAM
- Storage: 10 GB free disk space for installation and working files
- Display: 1920 x 1080 resolution or higher

The GPU workstation in your lab has been configured by your facility manager with the correct DeScribe version for your GT2 system. Do not update DeScribe without checking with your facility — version mismatches between DeScribe and NanoWrite can cause job file incompatibilities.

---

## Finding and Launching DeScribe

DeScribe is installed on the GPU workstation. The icon is typically on the desktop or in the Start menu under Nanoscribe. The version number is shown in the title bar when the application opens.

If DeScribe is not on the GPU workstation or is not launching, contact your facility manager. Do not attempt to install it yourself from a downloaded copy — the installation requires a license file specific to your institution.

---

## Initial Setup: Confirming Machine Configuration

When you open DeScribe for the first time or after a software update, confirm that it is configured for your specific GT2 system:

Go to: Settings > Machine Configuration
Verify: the machine type, available objectives, and default parameter ranges match your GT2 setup.

If the machine configuration is wrong, all parameter defaults will be incorrect. Ask your facility manager for the correct configuration file.

---

## File Management

DeScribe creates a working folder each time you generate GWL output. This folder contains the GWL files and a project file (.dsc or equivalent). Keep your project files organized:

Recommended folder structure on the GPU workstation:

    C:\GT2_Projects\
        YourName\
            ProjectName\
                model_v1.stl
                model_v1_job.gwl
                model_v1_data.gwl
                model_v1.dsc

After generating GWL files, transfer them to the GT2 control computer. Methods:
- USB flash drive: copy files to USB on the GPU workstation, plug into GT2 computer, copy to local folder
- Network share: if your facility has a shared network folder accessible from both computers, use this for faster transfer
- Do not transfer files over email or cloud storage that might alter filenames or add compression

---

Proceed to: importing_stl.md
