# Critical Warnings Checklist

This file consolidates every machine-specific warning from across this guide. Each warning describes a specific action that will cause a failed print, damaged equipment, or a safety incident if it is carried out. Read this list before every session until every item is automatic.

---

## Machine Operation Warnings

NEVER open the top hatch without going through the Exchange Holder dialog in NanoWrite.
Opening the lid without this dialog bypasses the safety interlock sequence. The laser may still be enabled. This is the single most important procedural rule for the GT2.

NEVER leave the machine unattended during approach.
The objective approaches the substrate during interface finding. If the stage overshoots, the objective can crash into the substrate and be damaged or destroyed. The objective costs several thousand dollars to replace.

ALWAYS allow 45 minutes of laser warm-up before printing.
Printing before warm-up is complete produces inconsistent voxel sizes and unpredictable exposure. The warm-up timer in NanoWrite is the reference. Do not abbreviate it.

NEVER run DeScribe on the GT2 control computer.
DeScribe must run on the dedicated GPU workstation. Running it on the GT2 control computer degrades NanoWrite performance and risks timing errors during prints.

NEVER run NanoWrite with GWL files still on a USB drive or an intermittent network share.
File read errors mid-print will abort the job and may leave the machine in an inconsistent state.

ALWAYS confirm the correct objective is installed before starting NanoWrite approach.
Starting approach with the wrong objective can crash the wrong-length objective into the substrate, or fail to contact the resin at all, both of which waste the session.

---

## Objective-Specific Warnings

25x OBJECTIVE: The adjustment ring MUST be set to Glyc (the position showing the 3 longest bars) before every session.
If the ring is set to any other position, the refractive index correction is wrong, the voxel is distorted, and every print will have degraded resolution. This setting does not retain itself between sessions. Check it every time.

63x OBJECTIVE: Use the fiber ring, never the silicone ring.
The 63x requires a fiber ring for the resin stop. Installing the silicone ring (used with other objectives) on the 63x will cause resin to leak past the ring and contaminate the objective front element and the piezo stage beneath it.

63x OBJECTIVE: Clean the front element and fiber ring after every oil immersion session.
Oil left on the front element dries into a film that degrades resolution in all subsequent sessions. Clean immediately after removal while the oil is still fluid.

10x OBJECTIVE: The 10x uses a silicone ring, not a fiber ring.
The opposite of the 63x warning above. Installing the fiber ring on the 10x will not provide adequate resin containment.

---

## Resin and Substrate Warnings

ITO GLASS: The ITO-coated side must face DOWN toward the objective.
Printing with the uncoated glass side facing the objective requires the laser to focus through 1 mm of glass, causing severe spherical aberration and unreliable interface detection. Verify orientation with a multimeter before loading.

GP-SILICA: The 8-hour time limit from resin deposition to end of development is strict.
After 8 hours, the binder chemistry changes and the green body becomes unsinerable. Exceed the time limit and the entire print is wasted. Plan your session to complete printing and development within this window.

GP-SILICA: Zero agitation during development and IPA rinse.
The green body before sintering is extremely fragile. Any agitation will crack or collapse it. Submerge gently and leave completely undisturbed.

IP-PDMS: Development time is longer than all other resins (25 to 35 minutes minimum).
Underdeveloped IP-PDMS structures feel tacky. If in doubt, return to fresh PGMEA for 10 additional minutes.

RESIN DROP GEOMETRY: The resin drop must be semi-spherical, not flat.
A flat drop prevents reliable interface detection. Apply resin to a clean plasma-treated surface and proceed immediately. Do not leave the resin sitting for more than 15 to 20 minutes before loading.

---

## Software and File Warnings

ALWAYS verify the include path in the job.gwl file after transferring from the GPU workstation.
DeScribe embeds absolute file paths in the job file. These paths do not exist on the GT2 computer. Edit the include line to use only the filename (no directory path) before loading in NanoWrite.

ALWAYS check the estimated print time in DeScribe before generating GWL files.
A print time that is too long can only be fixed in DeScribe. It cannot be changed once the job is loaded in NanoWrite without going back to DeScribe and regenerating.

NEVER edit the data.gwl file manually.
The data file is machine-generated and not human-readable in a useful sense. Edits to this file will corrupt the toolpath and produce an unpredictable or failed print.

---

## Post-Processing Warnings

NEVER UV cure a GP-Silica green body.
The green body must go through debinding and sintering in the furnace. UV curing the binder before furnace processing interferes with debinding uniformity.

NEVER run the UV curing station for more than 40 minutes in a single cycle.
Excess heat from prolonged operation can distort structures and damage the lamp. For extended curing of large structures, run two cycles with a 5-minute cooling interval.

NEVER pour PGMEA, IPA, or acetone down the drain.
All organic solvent waste must go into the designated halogen-free organic waste containers. Drain disposal violates waste regulations in most jurisdictions.

---

## Safety Warnings

NEVER look into the machine enclosure while the green Process light is on.
The 780 nm laser is invisible to the eye. Retinal damage can occur before any pain sensation warns you. Trust the Process light as the indicator of laser state.

NEVER open the electronics cabinet.
Mains voltage is present inside. There are no user-serviceable components. Report any electronics cabinet issue to your facility manager.

ALWAYS wear nitrile gloves when handling uncured resin or development solvents.
Acrylate monomers are skin sensitizers. Sensitization is irreversible. Prevent it by eliminating all skin contact from the first use.

ALWAYS perform development in a fume hood or well-ventilated area.
PGMEA is classified as a reproductive toxicant. Minimize inhalation exposure. IPA is highly flammable — keep away from ignition sources.
