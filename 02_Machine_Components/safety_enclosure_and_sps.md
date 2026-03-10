# 🛡️ Safety Enclosure and the SPS Panel

> The GT2 uses a Class IV laser — invisible, potentially blinding, and capable of igniting materials. The safety enclosure and SPS (Safety Precedence Sequence) system exist to make it impossible to be harmed during normal operation. This file explains how the safety system works and what to do when it doesn't.

---

## 🧠 Why a Safety Enclosure?

A Class IV laser at 780 nm (NIR) is **invisible to the human eye** and will not trigger the blink reflex. Even a brief, accidental reflection off a shiny surface can cause permanent retinal damage before you realize anything happened.

The GT2 solves this with a **completely sealed, interlocked safety enclosure** around the entire optical path and sample area. The laser cannot fire unless:

1. The top hatch is fully closed and latched
2. The SPS sequence has been properly initialized
3. NanoWrite has enabled the laser through the software interlock

All three conditions must be true simultaneously. If any one of them fails during operation, the system **immediately cuts power to the laser**.

---

## 🏗️ Physical Components of the Safety Enclosure

### The Outer Cabinet

The GT2 sits inside a rigid, opaque cabinet that contains all optical components. The cabinet is designed to:
- Block all 780 nm NIR radiation from escaping
- Prevent accidental contact with the sample stage during printing
- Provide a controlled environment (reduces dust and vibration)

### The Top Hatch

The **top hatch** is the primary access point for loading and unloading samples. It is located on the top surface of the GT2 enclosure.

```
         ┌─────────────────────────────────────┐
         │           TOP HATCH                 │
         │   ┌───────────────────────────┐     │
         │   │  Open to load/unload      │     │
         │   │  substrate and holder     │     │
         │   └───────────────────────────┘     │
         │         ↓ (closes to print)         │
         └─────────────────────────────────────┘
```

> ⚠️ **The hatch has a magnetic/mechanical interlock.** If it is not fully closed, the SPS will not allow the laser to fire. If you hear a click when closing — that's the interlock engaging. If you don't hear a click, check that the hatch is fully seated.

---

## 🔴 The SPS Panel

**SPS = Safety Precedence Sequence**

The SPS panel is a physical control panel on the GT2 (typically on the front or side of the machine). It contains:

| Element | Description |
|---|---|
| **Key switch** | The master laser enable key — must be turned to "ON" position |
| **Green "Process" light** | Glows green when the system is in a safe, ready state |
| **Red emergency stop (E-stop)** | Immediately kills laser power and disables the system |
| **Status LEDs** | Indicate which interlocks are engaged |
| **Reset button** | Re-initializes the SPS after a fault condition |

### The SPS Sequence (Normal Startup)

The SPS requires a specific startup order. Attempting to skip steps will result in a locked-out system:

```
Step 1: Turn key switch to ON
        │
        ▼
Step 2: Close top hatch completely
        │
        ▼
Step 3: NanoWrite sends "enable laser" command
        │
        ▼
Step 4: SPS checks all interlocks
        │
        ▼
Step 5: Green Process light illuminates ✅
        │
        ▼
Step 6: Laser is now enabled — printing can proceed
```

If any interlock check fails at Step 4, the SPS will **not** enable the laser and will display a fault code.

---

## 🟢 The Green "Process" Light

The **green Process light** is your visual confirmation that the system is in a laser-enabled, print-ready state.

| Light State | Meaning |
|---|---|
| **Green (steady)** | System is ready; laser is enabled |
| **Green (flashing)** | System is initializing or transitioning |
| **Off** | System is in safe state; laser is NOT enabled |
| **Red** | Fault condition — check SPS panel for error code |

> 🧠 **Rule of thumb:** If the green light is not on, the laser is off. You are safe to open the hatch. If the green light is on, the laser may be active — do not open the hatch.

---

## 🚨 SPS Safe-State Error: What It Means and How to Fix It

One of the most common issues beginners encounter is the **"SPS Safe State" error** in NanoWrite. This happens when the SPS system detects an interlock violation and puts the machine into a protective shutdown.

### Common Causes

| Cause | What Happened | Fix |
|---|---|---|
| Top hatch not fully closed | Hatch interlock not engaged | Close hatch completely until you hear the click |
| E-stop was pressed | Emergency stop is latched | Twist/release the E-stop button, then re-initialize SPS |
| Power interruption | SPS lost its initialized state | Follow the full SPS startup sequence from Step 1 |
| Software crash during print | NanoWrite lost control of the laser enable signal | Restart NanoWrite; re-initialize SPS |
| Key switch in wrong position | Key is in OFF or intermediate position | Turn key fully to ON |

### Recovery Procedure

1. Check that the **top hatch is fully closed**
2. Check that the **E-stop is not engaged** (not pressed in)
3. In NanoWrite, go to the machine control panel and click **"Reset SPS"** or **"Initialize Safety System"**
4. Wait for the green Process light to illuminate
5. If it doesn't illuminate, check the SPS panel LED codes and compare to the fault table in your machine's manual

For detailed troubleshooting: **[11_Troubleshooting/sps_safe_state_error.md](../11_Troubleshooting/sps_safe_state_error.md)**

---

## 🛑 The Emergency Stop (E-Stop)

The red E-stop button immediately:
- Cuts power to the laser
- Stops all stage movement
- Puts the SPS into safe state

### When to Use the E-Stop

- Smoke, burning smell, or unexpected sounds during a print
- Someone accidentally opens the enclosure during operation
- NanoWrite becomes unresponsive while the laser is active
- Any situation where you are unsure if the laser is firing and you cannot stop it through software

### When NOT to Use the E-Stop

- Simply pausing or stopping a print normally (use NanoWrite's stop button instead)
- A minor software error that doesn't involve a safety risk
- The print is taking too long (just wait — pressing E-stop mid-print ruins the job)

> ⚠️ **After pressing E-stop, you must follow the full SPS re-initialization procedure before the machine can print again.** This takes a few minutes. It is designed this way intentionally — the system wants you to consciously confirm everything is safe before re-enabling the laser.

---

## 🧤 Physical Safety Practices at the Machine

Even though the enclosure protects you during normal operation, maintain these habits:

1. **Never reach into the enclosure while NanoWrite has the laser enabled.** Always disable the laser through software first.
2. **Do not place reflective objects** (watches, rings, phone screens) near any open optical ports during service.
3. **Laser safety eyewear** must be worn during any open-beam alignment — this is performed only by trained service personnel.
4. **Do not attempt to defeat any interlock** for any reason. If an interlock is preventing your print, investigate the cause; don't bypass the safety.

Full laser and chemical safety information: **[12_Safety/README.md](../12_Safety/README.md)**

---

## 🔗 Related Files

- [12_Safety/laser_safety_overview.md](../12_Safety/laser_safety_overview.md)
- [12_Safety/sps_safety_system.md](../12_Safety/sps_safety_system.md)
- [11_Troubleshooting/sps_safe_state_error.md](../11_Troubleshooting/sps_safe_state_error.md)
- [06_Software_Workflow/NanoWrite_Software/startup_procedure.md](../06_Software_Workflow/NanoWrite_Software/startup_procedure.md)
- [06_Software_Workflow/NanoWrite_Software/shutdown_procedure.md](../06_Software_Workflow/NanoWrite_Software/shutdown_procedure.md)