# 170 um Borosilicate Glass — Oil Immersion Mode Substrate

---

## What This Substrate Is Used For

The 170 um borosilicate glass coverslip is used exclusively with the 63x objective in oil immersion mode (3D SF Oil configuration). It is not used in standard DiLL printing.

In oil immersion mode, the sample sits on top of the glass coverslip, and the 63x objective focuses up through immersion oil and through the glass into the sample above. The glass acts as a transparent, flat spacer between the objective and the sample.

This substrate is not used with the 10x, 25x, or 20x objectives.

---

## Why Thickness Matters Precisely

The 63x oil immersion objective is optically corrected for exactly 170 um of borosilicate glass (refractive index approximately 1.515). This is the same specification as standard microscopy cover glasses (No. 1.5 coverslips).

If the glass is thicker or thinner than 170 um:
- Spherical aberration is introduced into the focal volume
- Voxel size increases and voxel shape distorts
- Resolution degrades — features are blurry and merged
- The degree of degradation scales with how far the thickness deviates from 170 um

Tolerance: use glass within 170 um plus or minus 5 um. Standard No. 1.5 coverslips from reputable suppliers meet this specification.

---

## Refractive Index and Interface Detection

In oil immersion mode, the refractive index stack is:

Objective front element (n = 1.515)
Immersion oil 518F (n = 1.515)
170 um borosilicate glass (n = 1.515)
Sample / resist on top

All three layers — oil, glass, and the matching objective design — have essentially the same refractive index. This means there is no optical reflection at the oil-glass or glass-sample interfaces from below. The interface finder cannot detect the glass surface in the standard way it does in DiLL mode.

In oil immersion mode, interface finding is typically done manually:
1. Bring the objective close to the glass surface manually using the coarse stage
2. Use the live camera feed (AxioVision) to observe reflections from the sample surface above the glass
3. Adjust Z position until the sample surface is in focus
4. Define this as Z = 0 in NanoWrite before starting the print

This manual approach requires practice. Your first oil immersion session should be done with an experienced user present.

---

## Cleaning 170 um Coverslips

These are extremely thin and fragile. Handle with care — they break easily under finger pressure.

Step 1 — Handle by edges only
Never touch the flat surfaces with fingers. Fingerprints contaminate the optical surface and are very difficult to remove without risk of breakage.

Step 2 — Acetone rinse
Hold the coverslip in clean tweezers and rinse with acetone from a wash bottle. Do not submerge — the acetone stream is sufficient and reduces breakage risk.

Step 3 — IPA rinse
Rinse with IPA immediately after acetone.

Step 4 — Nitrogen dry
Blow gently with nitrogen. Do not use high pressure — 170 um glass will crack.

Step 5 (optional) — Plasma treatment
O2 plasma at low power (50 W maximum) for 30 seconds. Higher power or longer times risk thermal stress cracking.

Do not use ultrasonic cleaning — the vibration will crack 170 um glass.

---

## How to Apply Immersion Oil to the 63x

1. Ensure the 63x objective is installed with the fiber ring.
2. Place one small drop of immersion oil 518F on the front element of the 63x objective. One drop is sufficient — excess oil will spread uncontrollably.
3. Lower the sample holder (with the 170 um glass coverslip and sample on top) gently toward the objective until the glass contacts the oil.
4. The oil fills the gap by capillary action.
5. Confirm through the camera that contact is made with no air bubbles in the oil layer.

Air bubbles in the oil layer will scatter the laser and ruin the print. If bubbles are visible, raise the sample slightly, allow the oil to settle, and lower again slowly.

---

## Cleaning the Objective After Oil Immersion

After every oil immersion session, clean the front element of the 63x objective immediately:

1. Use a clean piece of lens tissue — not a regular tissue or cloth.
2. Place the lens tissue gently on the front element and draw it across in one direction. Do not rub back and forth.
3. If oil remains, apply one drop of IPA to the lens tissue and repeat.
4. Inspect visually — the front element should be completely clear with no smears.

Oil left on the objective will dry into a film that degrades resolution in subsequent sessions and is harder to remove than fresh oil.

---

## Comparison: 170 um Borosilicate vs Standard Borosilicate

| Property | 170 um No. 1.5 Coverslip | Standard 1 mm Borosilicate Slide |
|---|---|---|
| Thickness | 170 um | 1000 um |
| For oil immersion (63x) | Yes — required | No — too thick, causes severe aberration |
| For DiLL mode | No | Yes (check delta-n) |
| Fragility | Very fragile | Robust |
| Availability | Standard lab supply | Standard lab supply |

Never substitute a standard 1 mm glass slide for a 170 um coverslip in oil immersion mode. The thickness difference (830 um) introduces uncorrectable spherical aberration.

---

Proceed to: quartz_substrates.md
