# 🧪 63× Objective — Compatible Resists

---

## Compatible Resists

| Resist | Status | Best For |
|---|---|---|
| **IP-Dip2** | ✅ Primary | Highest resolution, standard 63× workflow |
| **IP-Dip** | ✅ Compatible | Previous generation — use IP-Dip2 when available |
| **IPX-Clear** | ✅ Compatible | Transparent optical structures at high resolution |
| **GP-Silica** | ✅ Compatible | Fused silica / glass structures (special workflow) |
| IP-S | ❌ Not compatible | 25× only |
| IP-Q | ❌ Not compatible | 10×/25× only |
| IP-Visio | ❌ Not compatible | 25× only |
| IP-PDMS | ❌ Not compatible | 25× only |

---

## IP-Dip2 — The Primary 63× Resist

**IP-Dip2** is Nanoscribe's latest and highest-performance resin, specifically engineered for the 63× objective.

| Property | Value |
|---|---|
| Refractive index | n = 1.511 @ 780 nm |
| Viscosity | Low (water-like) |
| Shrinkage | ~8–12% |
| Transparency | High (visible spectrum) |
| Shelf life | 12–18 months (refrigerated) |

**Why IP-Dip2 specifically for 63×:**
- Refractive index (1.511) closely matches immersion oil (1.515) → minimal aberration in DiLL mode
- Formulated for maximum two-photon sensitivity at NA 1.4 focal volumes
- Optimized photoinitiator for sub-200 nm voxel performance

**Application method:**
1. Remove from fridge → warm to room temperature (~15 min)
2. Deposit **1 small drop** on substrate (quartz or silicon)
3. Drop must be **semi-spherical** — this is critical for interface detection
4. Do not wait more than 15–20 min before printing
5. Keep bottle capped and away from light when not in use

---

## IP-Dip (Legacy) vs IP-Dip2

| Property | IP-Dip | IP-Dip2 |
|---|---|---|
| Resolution | Good | Better |
| Shrinkage | ~10–15% | ~8–12% |
| Shelf life | 12 months | 12–18 months |
| Availability | Being phased out | Current standard |

If your lab still has IP-Dip stock, it works — but IP-Dip2 gives better results. Don't mix them.

---

## GP-Silica — For Glass Structures

GP-Silica is a special hybrid resin that contains silica nanoparticles suspended in a photopolymer matrix. After printing and development, the polymer is burned away in a furnace, leaving a **pure fused silica (glass) structure**.

⚠️ **Special requirements for GP-Silica with 63×:**
- Print must be completed within **8 hours** of resin deposition
- After printing: debinding step (400°C furnace, 4 hours)
- After debinding: sintering step (~1500°C furnace, controlled atmosphere)
- Final structure shrinks ~25% in all dimensions during sintering — design 25% oversized
- Requires access to a high-temperature furnace (not included with GT2)

---

> 🔗 Next: [compatible_substrates.md](compatible_substrates.md)