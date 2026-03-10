# 🧪 Polymerization Chemistry — What Happens When the Resin Solidifies

> You don't need to be a chemist to use the GT2. But understanding the basic chemistry of polymerization will help you make better decisions about resin choice, laser parameters, post-processing, and troubleshooting.

---

## What Is a Photopolymer?

A **photopolymer** is a material that changes from liquid to solid when exposed to light. The word comes from:

- **Photo** = light (Greek: φῶς)
- **Polymer** = long chain molecule (Greek: πολύς = many, μέρος = part)

The IP-series resins used in the GT2 are all photopolymers — they are liquid under normal conditions and solidify only when the right amount of laser energy is delivered to the focal point.

---

## The Three Components of IP-Series Resins

Every Nanoscribe IP-series resin contains three main ingredients:

### 1. Monomers / Oligomers
The "building blocks" — small molecules that will link together to form the solid polymer network.

In GT2 resins, these are typically **acrylate-based** or **methacrylate-based** molecules. They contain reactive double bonds (C=C) that participate in the polymerization chain reaction.

```
Monomer structure (simplified):
CH₂=CH–[functional group]
  ↑
  This double bond is where the reaction happens
```

### 2. Photoinitiators
The trigger molecules. They absorb the two photons and generate highly reactive species (free radicals) that start the polymerization chain reaction.

Without photoinitiators, the monomer would never react no matter how much laser power you use.

Nanoscribe's resins use proprietary two-photon-active photoinitiators optimized for 780 nm absorption.

### 3. Additives
Depending on the specific resin, additives may include:
- **Inhibitors** — prevent unwanted polymerization during storage (shelf life)
- **Plasticizers** — control flexibility/stiffness of cured polymer (IP-PDMS)
- **Sensitizers** — enhance two-photon absorption cross-section
- **Biocompatibility agents** — for IP-Visio

---

## The Polymerization Reaction — Step by Step

```
STEP 1: Two-Photon Absorption
━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Photoinitiator (PI) + 2 photons (780 nm) → PI* (excited state)

STEP 2: Radical Generation
━━━━━━━━━━━━━━━━━━━━━━━━━
PI* → R• (free radical — an extremely reactive molecule fragment)

STEP 3: Chain Initiation
━━━━━━━━━━━━━━━━━━━━━━━
R• + Monomer → R–Monomer•  (radical attacks the C=C double bond)

STEP 4: Chain Propagation
━━━━━━━━━━━━━━━━━━━━━━━━━
R–Monomer• + Monomer → R–Monomer–Monomer•
R–Monomer–Monomer• + Monomer → R–Monomer–Monomer–Monomer•
[this continues hundreds to thousands of times in microseconds]

STEP 5: Chain Termination
━━━━━━━━━━━━━━━━━━━━━━━━━
Two radicals combine → dead chain → solid polymer network
```

The key thing to understand: **one two-photon absorption event generates one radical, which then triggers a chain reaction that polymerizes hundreds of monomers**. This amplification is why even the very small number of two-photon events at the focal point is enough to create a solid voxel.

---

## Why Does Polymerization Cause Shrinkage?

When monomers link together into polymer chains, the spacing between molecules decreases — they pack closer together. This results in a volume reduction of the material:

```
Before polymerization:    After polymerization:
  O  O  O  O  O           O-O-O-O-O
  O  O  O  O  O     →     O-O-O-O-O
  O  O  O  O  O           O-O-O-O-O
(spread out monomers)    (packed polymer chains)
```

**Typical shrinkage of IP-series resins: 5–15% by volume**

This shrinkage has practical consequences:
- Printed features are slightly smaller than designed — compensate by scaling up in DeScribe
- Non-uniform shrinkage can cause warping or delamination in large structures
- Thin features may crack if they adhere to a rigid substrate while shrinking
- IP-S is specifically formulated for **low shrinkage** (~5%) compared to other resins

---

## Oxygen Inhibition

Oxygen dissolved in the resin acts as a **polymerization inhibitor** — it reacts with free radicals before they can initiate chain growth, effectively consuming radicals without producing polymer.

```
R• + O₂ → RO₂•  (peroxy radical — inactive, cannot propagate chain)
```

This has two important effects:

1. **Surface inhibition:** The top surface of a structure exposed to air may remain partially uncured due to oxygen from the atmosphere. This is why UV post-curing is important — it provides extra energy to overcome oxygen inhibition at surfaces.

2. **Threshold effect:** Oxygen helps sharpen the polymerization threshold — you need to generate enough radicals to overcome oxygen inhibition before curing begins. This actually helps achieve sub-diffraction features.

**Practical tip:** Do not let resin sit open in air for extended periods before printing — dissolved oxygen concentration increases and you may need higher laser power to overcome inhibition.

---

## UV Post-Curing — Why It's Necessary

During printing, not every monomer in the voxel reacts. The laser provides enough energy to form a **solid network** (enough cross-links to make it rigid) but some unreacted monomers remain trapped inside.

UV post-curing at 405 nm:
- Activates remaining photoinitiator molecules throughout the structure
- Reacts remaining monomers → more complete cross-linking
- Increases mechanical strength (hardness, stiffness) by 20–50%
- Improves chemical resistance of the final structure
- Reduces likelihood of slow continued polymerization over time (which would distort dimensions)

**Without UV post-curing:** Structures are softer, weaker, and may slowly change shape over days/weeks.

---

## How Development Works Chemically

After printing, your structure sits in a pool of uncured liquid resin. The development step removes this liquid using a solvent:

**PGMEA** (propylene glycol monomethyl ether acetate) is the primary developer:
- It is a **polar aprotic solvent** with good solvating power for uncured monomers
- The uncured monomer molecules dissolve into the PGMEA
- The polymerized (cross-linked) network does NOT dissolve — it is insoluble in PGMEA
- Result: liquid washes away, solid structure remains

**IPA rinse (second step):**
- IPA is a weaker solvent that removes residual PGMEA
- PGMEA can slowly swell some polymers if left too long — IPA rinse prevents this
- IPA evaporates faster than PGMEA — important for clean drying

---

## Resin Shelf Life and Storage

IP-series resins contain **inhibitors** to prevent premature polymerization during storage. Despite this:

- Store in **refrigerator (4–8°C)** when not in use
- **Protect from light** — even room light can slowly degrade the photoinitiator
- **Shelf life:** Typically 12–24 months from manufacturing date (check label)
- Allow to reach **room temperature** before use (~15 min out of fridge)
- **Never return used resin to the original bottle** — contamination risk

---

## Summary

| Concept | Key Point |
|---|---|
| Monomer | Small reactive molecule — the building block |
| Photoinitiator | Absorbs 2 photons → generates radicals → triggers reaction |
| Chain reaction | 1 radical → hundreds of monomers polymerized |
| Shrinkage | 5–15% volume reduction — design larger to compensate |
| Oxygen inhibition | O₂ consumes radicals — explains threshold behavior |
| Development | PGMEA dissolves uncured monomer, not cured polymer |
| UV post-curing | Completes reaction, increases strength and stability |

---

> 🔗 **Section complete!** Next → **[02_Machine_Components](../02_Machine_Components/README.md)**