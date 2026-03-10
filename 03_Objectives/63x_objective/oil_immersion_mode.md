# 🛢️ 63× Objective — Oil Immersion Mode

---

## Two Modes for the 63×

The 63× can operate in two distinct modes:

| Mode | Immersion Medium | Substrate | Use Case |
|---|---|---|---|
| **DiLL (standard)** | IP-Dip2 resin directly | Quartz, silicon | Direct 3D printing into resin drop |
| **Oil Immersion (3D SF Oil)** | Immersion oil 518F | 170 µm borosilicate glass | Printing on spin-coated resists through glass |

---

## DiLL Mode (Primary)

In standard DiLL mode with the 63×:
- The objective dips directly into IP-Dip2 resin
- No cover glass between objective and resin
- Best resolution — no glass-induced aberrations
- Most common mode for nanoscale printing

---

## Oil Immersion Mode

In oil immersion mode:
- A drop of **immersion oil 518F** (n = 1.515) is placed on the objective
- A **170 µm borosilicate glass coverslip** sits between the oil and the sample
- The sample (with spin-coated resist) sits on top of the glass
- The laser focuses up through: oil → glass → resist

### When to Use Oil Immersion Mode
- When your sample has a spin-coated photoresist (not a drop-cast IP-series resin)
- When substrate must remain flat and clean (no resin contact on bottom)
- When printing on pre-patterned substrates where resin contact is undesirable

### Refractive Index Matching in Oil Mode
```
Objective (n = 1.515 design)
       ↓
Oil 518F (n = 1.515) ✅ matched
       ↓
170 µm borosilicate glass (n ≈ 1.515) ✅ matched
       ↓
Resist / sample
```

All three layers have nearly identical refractive indices — no aberration at any interface.

### How to Apply Immersion Oil
1. Place **one small drop** of oil 518F on the front element of the 63× objective
2. Lower the sample holder so the glass coverslip contacts the oil
3. The oil fills the space by capillary action
4. ⚠️ Clean the objective front element with lens tissue after every oil immersion session — leftover oil dries and degrades optical performance

---

> 🔗 Next: [compatible_resists.md](compatible_resists.md)