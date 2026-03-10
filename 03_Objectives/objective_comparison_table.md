# 📊 Objective Comparison Table — Full Specs

> Use this table as your quick reference whenever you need to decide which objective to use.

---

## Full Specifications Table

| Property | 10× DiLL | 20× Air | 25× DiLL | 63× DiLL |
|---|---|---|---|---|
| **Magnification** | 10× | 20× | 25× | 63× |
| **Numerical Aperture (NA)** | 0.3 | — | 0.8 | 1.4 |
| **Working Distance (WD)** | 700 µm | — | 380 µm | 360 µm |
| **Immersion Medium** | IP-series resin (DiLL) | Air | IP-series resin (DiLL) | Oil / IP-Dip2 (DiLL) |
| **Lateral Voxel Size** | ~1.6 µm | N/A | ~400 nm | ~160 nm |
| **Axial Voxel Size** | ~12 µm | N/A | ~1.5 µm | ~500 nm |
| **Print Field (Galvo)** | 400×400 µm | 400×400 µm | 400×400 µm | 400×400 µm |
| **Max Structure Volume** | ~10 mm³ | ~1 mm² (2D) | ~1 mm³ | ~0.1 mm³ |
| **Max Build Height** | ~700 µm | Limited | ~380 µm | ~360 µm |
| **True 3D Printing** | ✅ Yes | ❌ No | ✅ Yes | ✅ Yes |
| **Resin Stop Type** | Silicone ring | — | Silicone ring | Fiber ring |
| **Compatible Resists** | IP-Q, IPX-Q, IPX-Clear | i-line photoresists | IP-S, IP-Visio, IP-PDMS, IP-Q, IPX-Clear | IP-Dip2, IP-Dip, IPX-Clear |
| **Typical Substrates** | Silicon wafer, 25×25 mm Nanoscribe glass | Spin-coated wafer | ITO glass, silicon | Quartz, silicon, 170 µm borosilicate |
| **Typical Laser Power** | 30–70% | N/A | 20–50% | 15–35% |
| **Print Speed** | ⚡⚡⚡ Fast | ⚡⚡ Medium | ⚡⚡ Medium | ⚡ Slow |
| **Resolution** | ⭐ Low | ⭐⭐ Medium | ⭐⭐⭐ High | ⭐⭐⭐⭐ Highest |
| **Best For** | Large fast structures | 2D patterning on wafers | Balanced research printing | Nanoscale precision |

---

## Voxel Size Visual Comparison

```
63× voxel:    ▪  (~160 nm wide)
25× voxel:    ●  (~400 nm wide)
10× voxel:    ⬤  (~1.6 µm wide)

              ▪ = 1 voxel unit
              At this scale: 10× voxel is 10× wider than 63× voxel
```

---

## Compatible Resists Quick Matrix

| Resist | 10× | 20× | 25× | 63× |
|---|---|---|---|---|
| IP-Dip2 | ❌ | ❌ | ❌ | ✅ |
| IP-Dip | ❌ | ❌ | ❌ | ✅ |
| IP-S | ❌ | ❌ | ✅ | ❌ |
| IP-Visio | ❌ | ❌ | ✅ | ❌ |
| IP-PDMS | ❌ | ❌ | ✅ | ❌ |
| IP-Q | ✅ | ❌ | ✅ | ❌ |
| IPX-Q | ✅ | ❌ | ❌ | ❌ |
| IPX-Clear | ✅ | ❌ | ✅ | ✅ |
| GP-Silica | ❌ | ❌ | ✅ | ✅ |
| i-line resists | ❌ | ✅ | ❌ | ❌ |

---

## Decision Flowchart

```
What is the smallest feature in your design?

├── < 500 nm → Use 63× + IP-Dip2
│
├── 500 nm – 5 µm → Use 25× + IP-S (or IP-Visio for bio)
│
├── 5 µm – 50 µm → Use 25× or 10× depending on total volume
│   ├── Structure < 1 mm³ → 25×
│   └── Structure > 1 mm³ → 10×
│
├── > 50 µm features, large volume → Use 10× + IP-Q
│
└── 2D pattern on spin-coated wafer → Use 20× + i-line resist
```

---

> 🔗 See individual objective folders for full installation, parameter, and troubleshooting details.