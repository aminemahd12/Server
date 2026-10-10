# Home server deal research — Villach → Morocco

*Listings were checked on 9–10 Oct 2026 in two independent passes. Every listing used in the three builds and in the §1b comparison was re-opened on 10 Oct and was still active (`date_checked` = 2026-10-10). Prices are as listed and shipping is to Villach. "Net" = price + shipping − realistic resale of the parts you don't need. Pickup trips are not counted in net.*

**Every listing is in [`deals.csv`](deals.csv)**: 378 rows, each opened, none reserved or sold.
- Marketplace ads were posted within 30 days of the check. avito.ma only shows the last bump time, so the Moroccan rows are flagged in `notes`.
- Shop listings have no posting date.
- Rows used in a build are at the top (`used_in_build`). `platform_ships_to_at` says whether the marketplace itself ships to Austria.
- The ads behind every resale value are in [`resale_comps.csv`](resale_comps.csv), and the medians used are in [`resale_comps_summary.csv`](resale_comps_summary.csv).

**Not searchable from the research machine:** eBay (all domains, so no sold-price data) and leboncoin. Resale values are therefore asking-price medians × 0.85, not sold prices (§10).

**What I optimised for:**
- CPU/RAM performance for the solvers and Windows VMs.
- A reliable, large NAS.
- Upgradability.
- Low 24/7 power draw and ease of use. You said this matters, so single-CPU builds are preferred and dual-CPU machines only appear where they are unusually cheap (§1b, §4).

---

## 1. Recommendation in one table

| | **Build 1 — i9-12900K desktop** (recommended) | **Build 2 — HP Z440 workstation** | **Build 3 — Supermicro X10SRi-F server board** |
|---|---|---|---|
| What it is | Gaming PC bought whole; you keep CPU, board, RAM, PSU, cooler and SSD, move them into **your case**, and resell the GPU, QLC SSD, case and WiFi card | A ready-made HP workstation with an E5-2690 v4, plus 32 GB more RAM; resell its GTX 1660 Super and WiFi card | Server board + CPU + RAM from one seller, with a new cooler, a used PSU and an SSD, built into **your case** |
| CPU | i9-12900K, 16 cores / 24 threads (8 P + 8 E) | Xeon E5-2690 v4, 14 / 28 | Xeon E5-2697 v4, 18 / 36 |
| RAM | 64 GB DDR4-3200 (2×32), non-ECC, 4 slots (max 128 GB) | 64 GB DDR4 **ECC** RDIMM, 8 slots (max 256 GB) | 32 GB DDR4-2400 **ECC** RDIMM (4×8), 8 slots (256 GB RDIMM / 512 GB LRDIMM) |
| NAS | 2× Toshiba MG08 16 TB, ZFS mirror (16 TB usable) | same | same |
| VM / boot SSD | Samsung 980 500 GB NVMe | 240 + 256 GB SATA SSDs (included) | Intel D3-S4510 480 GB (enterprise, power-loss protection) |
| PassMark multi / single | **41,099 / 4,128** | 19,166 / 2,067 | 21,371 / 2,038 |
| Memory bandwidth (theoretical) | 51 GB/s (2 channels) | 68 GB/s (4 ch, DDR4-2133 modules) | 77 GB/s (4 ch) |
| **Idle power** (whole box, 2 HDDs; estimate) | **~30–42 W** | ~55–65 W | ~48–68 W |
| **Electricity per year in Morocco** | **€28–53** | €51–82 | €44–85 |
| Upfront cash | €1,237.80 | €846.39 | €790.49 |
| Resale of unused parts | −€456 | −€99 | — |
| **Net cost** | **€781.80** | **€747.39** | **€790.49** |
| Headroom under €800 | €18.20 | €52.61 | €9.51 |
| Net if resale only fetches 70% of asking | €861.90 ❌ | €764.49 | €790.49 |
| Net if the MG08 pair is gone (2× MG07 14 TB instead, +€75.69) | €857.49 ❌ | €823.08 ❌ | €866.18 ❌ |
| **4-year cost** (net + electricity) | **€892–993** | €950–1,074 | €967–1,132 |
| Remote management | None built in (add a €135 KVM later) | None (no BMC; Intel AMT can't do KVM without an iGPU) | **Full IPMI web console** (remote BIOS, power, ISO mount) |
| Ease of use | Normal desktop, iGPU, quiet; Proxmox runs fine | Finished, quiet, 11–13.5 kg machine; nothing to assemble | Needs assembly; server BIOS; fans need setting up |

**Ranking against your priorities** (CPU/RAM > storage reliability > upgradability > idle power, with power and ease of use weighted up as you asked). Storage is the same MG08 mirror in all three, so it doesn't separate them.
1. **Build 1, my pick.** It has about 2× the Xeons' throughput and single-core speed, the lowest idle power and 4-year cost, and standard parts in your case. Its weak spots: no ECC, no remote console until you add a KVM, a 128 GB ceiling, and it is under €800 only if you sell four parts.
2. **Build 2.** ECC, a finished workstation, the easiest to own and the cheapest net. It is about half as fast as Build 1 and costs about €25–30 a year more in power.
3. **Build 3.** ECC, the only built-in remote console (IPMI) and the most RAM headroom. But it is about half as fast as Build 1, has the highest idle draw of the three, needs assembly, and starts with only 32 GB.

**When to choose Build 2 or 3 instead:**
- **Build 2** if you want ECC and a no-assembly machine with little to resell (a GPU and a WiFi card).
- **Build 3** if being able to fix the box from Singapore (BIOS, reinstall, power-cycle) matters more than speed.

**How firm the net figures are.**
- **Cash up front:** €1,237.80 / €846.39 / €790.49. Resale has to happen in Austria before you fly. List the items on willhaben as soon as the box is tested, and allow 1–3 weeks.
- **Build 1 stays under €800 only if all four items sell at about 85% of asking.** At 70% it is €861.90. Keeping the 870 QVO as a scratch disk makes it €930.80.
- **All three builds depend on one Slovenian MG08 pair** (§6). If it sells, the next sound pair (2× MG07 14 TB, Mülheim DE, €198 each + DHL €17.49) puts every build over budget.
- **Pickup trips are not in the net:** Waldkraiburg for Build 1 (~3 h 15 min each way, plus fuel and the A10 tunnel tolls); none for Builds 2 and 3 if the sellers post.

> Nothing has been bought and no seller has been contacted. §9 lists what to ask each seller. The buy-now list is in §6.

**Should you consider a dual-CPU box?** The best-value one found is a Lenovo P720 upgraded to 2× Gold 6140: 36 cores, AVX-512 and 12 memory channels for **€734.69 net** (§1b, §4). The cheapest dual-CPU box as listed is the Intel S2600CW at €642.60 net, but it has only 20 Broadwell cores.
- The P720 is absurdly cheap for the hardware.
- But it idles at ~65–90 W, which costs €32–60 a year more than Build 1. It weighs ~28–31 kg boxed, has no remote console, and needs NUMA pinning to be used well.
- It is only worth it if you run CST Studio or very large FDTD meshes every day.

---

## 1b. Head-to-head: Lenovo P720 vs Build 1 vs the Ryzen 9 options

All columns include the same 2× MG08 16 TB mirror (€337.80), a boot/VM SSD, and a display card where the CPU has no iGPU. Resale = median asking price × 0.85. Every listing here was re-opened on 10 Oct and was still active.

Listings: [P720](https://www.kleinanzeigen.de/s-anzeige/lenovo-thinkstation-p720-workstation-rtx-3060-64-gb-ram-/3531669065-228-3721) · [Gold 6140 #1](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/intel-xeon-gold-6140-18-kerne-36-threads-lga-3647-server-workstation-1-1309917360/) · [#2](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/intel-xeon-gold-6140-18-kerne-36-threads-lga-3647-server-workstation-2-841391018/) · [12900K PC](https://www.kleinanzeigen.de/s-anzeige/gaming-pc-i9-12900k-rtx-3060-12gb-64gb-ddr4-2-5tb-ssd/3522007884-228-5681) · [5950X](https://www.kleinanzeigen.de/s-anzeige/amd-ryzen-9-5950x-16-kerne-32-threads-am4/3528545945-225-136) · [ASRock B550 Pro4](https://geizhals.at/asrock-b550-pro4-a2295762.html) · [4×16 GB ECC](https://www.kleinanzeigen.de/s-anzeige/4x-kingston-kvr24e17d8-16-ddr4-2400-cl17-sdram-ecc-64-gb-/3526472062-225-4445) · [Freezer 36 CO](https://www.alternate.at/ARCTIC/Freezer-36-CO-CPU-K%C3%BChler/html/product/100060190) · [RM550x](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/corsair-rm550x-550w-1384681058/) · [GT 710](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/asus-gt710-sl-2gd5-1784456640/) · [S4510](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/intel-ssd-d3-s4510-series-480gb-1486697881/) · [5900X workstation, Röschitz](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/workstation-amd-ryzen-9-5900x-64gb-ddr4-rtx-2080-super-1905851247/) · [3900X, Villach](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/ryzen-3900x-12core-4100mhz-vhb-2034208352/) · MG08 [#1](https://www.bolha.com/sata3-trdi-diski/prodam-trdi-disk-toshiba-16tb-mg08aca16te-zdrav-oglas-16514405) [#2](https://www.bolha.com/sata3-trdi-diski/trdi-disk-toshiba-16tb-mg08aca16te-zdrav-oglas-16514386)

| | **Lenovo P720, 2× Gold 6140** | **Build 1: i9-12900K harvest** | **Ryzen 9 5950X, parts** | **Ryzen 9 5900X harvest (Röschitz)** | **Ryzen 9 3900X, parts (local CPU)** |
|---|---|---|---|---|---|
| How you get it | Ship P720 from Waltershausen DE (seller must agree; DHL €45.49 if it stays under 31.5 kg boxed); 2× Gold 6140 from Linz (PayLivery) | Pickup in Waldkraiburg (~3 h 15 min each way) | 5950X from Stralsund DE (ad says pickup; text says insured shipping by agreement); new ASRock B550 Pro4 (alza.at); ECC RAM from Hochheim DE; cooler, PSU, GPU and SSD from AT | Pickup in Röschitz, Lower Austria (~4.5 h, weekends only) | 3900X pickup in **Villach**; board, RAM, cooler, PSU, GPU and SSD as in the 5950X column |
| Upfront cash | €1,044.69 | €1,237.80 | €1,047.36 | €1,263.50 | €932.87 |
| You resell | RTX 3060 (€242), 2 TB HDD (€68) | RTX 3060 (€242), 870 QVO 2 TB (€149), case (€51), WiFi card (€14) | nothing | RTX 2080 Super (€200), NZXT H510 (€47) | nothing |
| **Net cost** | **€734.69** | **€781.80** | **€1,047.36** | **€1,016.50** | **€932.87** |
| vs €800 budget | ✅ −€65 | ✅ −€18 | ❌ +€247 | ❌ +€217 | ❌ +€133 |
| Net if resale fetches only 70% | €789.19 | €861.90 ❌ | €1,047.36 | €1,060.50 | €932.87 |
| CPU | 2× 18C/36T Skylake-SP (36C/72T) | 8P+8E, 16C/24T Alder Lake | 16C/32T Zen 3 | 12C/24T Zen 3 | 12C/24T Zen 2 |
| PassMark multi / single | 41,109 / 2,089 (one CPU: 24,187 / 2,141) | 41,099 / **4,128** | **45,247** / 3,477 | 38,887 / 3,465 | 32,465 / 2,702 |
| Cinebench R23 multi | no source | 27,472 | **28,577** | 21,878 | 18,165 |
| AVX-512 | **Yes (2 FMA units)** | No | No | No | No |
| Cores CST can use[^cst] | 36 (base licence covers 2 sockets) | 8 (P-cores only) | 16 | 12 | 12 |
| RAM as bought | 64 GB DDR4 **ECC** RDIMM (layout unknown) | 64 GB DDR4-3200 (2×32), non-ECC | 64 GB DDR4-2400 **ECC** UDIMM (4×16) | 64 GB DDR4-3600 CL16 (4×16), non-ECC | 64 GB DDR4-2400 **ECC** UDIMM (4×16) |
| RAM slots / max | 12 / **768 GB** | 4 / 128 GB (2 slots free) | 4 / 128 GB (all full) | 4 / 128 GB (all full) | 4 / 128 GB (all full) |
| Memory channels / theoretical bandwidth | **12 ch / up to 256 GB/s, only with all 12 slots filled.** The listed 64 GB fills at most 8, so expect ~85–170 GB/s as delivered. | 2 ch / 51 GB/s | 2 ch / 38 GB/s (ECC kit is DDR4-2400) | 2 ch / 58 GB/s | 2 ch / 38 GB/s |
| Boot / VM drive | 250 GB SSD (incl.); 2× M.2 onboard | Samsung 980 500 GB NVMe (incl.) | Intel S4510 480 GB with power-loss protection | Samsung 960 EVO 250 GB (incl.) | Intel S4510 480 GB with power-loss protection |
| Display | No iGPU (Xeon). Install Proxmox before selling the RTX 3060 and check it boots headless; otherwise add a GT 710 (+€25.70) | iGPU | GT 710 | GT 710 | GT 710 |
| **Idle power** (whole box, 2 HDDs; estimate) | 65–90 W (one CPU: 45–75 W) | **30–42 W** | 35–50 W | 45–58 W (X570 chipset +10–14 W) | 35–50 W |
| Electricity / year in Morocco | €60–113 (one CPU: €41–94) | **€28–53** | €32–63 | €41–73 | €32–63 |
| **4-year cost** (net + power) | €974–1,187 (one CPU, net €703.99: €870–1,081) | **€892–993** | €1,176–1,299 | €1,182–1,308 | €1,062–1,184 |
| Remote management | None (AMT without KVM) | None | None | None | None |
| Uses your case / weight to fly | No: Lenovo tower, up to 25.7 kg unpacked, ~28–31 kg boxed (overweight fee) | Yes | Yes | Yes | Yes |
| Noise | Workstation fans, moderate | Quiet (240 mm AIO) | Quiet | Quiet (NH-D15) | Quiet |
| Effort | Least assembly; NUMA tuning for solvers and VMs | Move parts into your case + sell 4 items | Most coordination (7 sellers/shops, 2 cross-border) | Move parts + sell 2 items | Like the 5950X, but the CPU is local |
| Upgrade path | Gen-2 Xeon Gold (e.g. 2× 6230, €160 the pair), 768 GB, 2× M.2 | 13900K/14900K, 128 GB | End of AM4 line; 128 GB needs 4× 32 GB ECC (expensive) | Same as 5950X; drop in a 5950X (~€200–250) | Drop in a 5950X later (~€200–250) |
| Main risks | RAM layout unknown; ex-corporate BIOS lock possible; 6140s come without carrier clips; heavy; proprietary; seller must agree to ship ~30 kg | No ECC; Bronze PSU; resale effort; pickup | Over budget; payment/shipping by agreement with 2 DE sellers | Over budget; non-ECC; weekend-only pickup far away | Over budget; Zen 2 single-thread ≈ Xeon level |
| Best for | CST, big FDTD/MPI (Elmer, Palace, MEEP), huge FEM RAM | HFSS/FEKO on 4-core base licences, openEMS, Windows VMs, lowest bill | Best all-round single CPU with ECC (CST uses all 16 cores) | Fast cores, but loses to Build 1 on price and power | Cheapest Ryzen 9 route; upgrade CPU later |

**Bottom line.**
- **Build 1 is the cheapest to run and has the fastest single cores.** On multi-core it matches the P720 and is about 9% behind the 5950X. Over 4 years it is the cheapest of the full-power options. It loses on ECC, AVX-512, memory bandwidth and RAM ceiling.
- **The P720 is the cheapest to buy** (€734.69 net) and the only one with AVX-512, 12 memory channels and room for 768 GB.
  - It is worth it only if your solvers are bandwidth- or RAM-bound (CST, large FDTD/FEM).
  - Even then, budget €32–60 a year more power than Build 1.
  - Running it on one CPU (€703.99 net, 45–75 W) brings its 4-year cost level with Build 1. But then it has 18 Skylake cores (PassMark 24,187), about 60% of Build 1's throughput, and only 6 RAM slots.
- **None of the Ryzen 9 builds fits €800 in the October 2026 market.** The 5950X with ECC is the best single-CPU machine overall if you can spend €1,047. The 3900X-in-Villach route (€933) gets you onto the same platform and lets you drop in a 5950X later.
- Other Ryzen 9 routes checked cost more:

  | Route | Total |
  |---|---|
  | [3900X + 64 GB + MSI B550 bundle, Vienna](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/amd-ryzen-9-3900x-64gb-ddr4-3600-ram-msi-b550-1796397500/) + cooler, PSU, GPU, SSD, mirror | €1,132.59 |
  | [5900X PC without GPU, Vienna](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/gaming-pc-ohne-gpu-1798028937/) + GPU, mirror | about €1,171 |

---

## 2. What the October 2026 market looks like (and why the builds look like this)

- **DRAM and NAND shortage.**
  - New 64 GB of RAM: desktop DDR4 (2×32) from €478; ECC RDIMM from €319.60 as 2×32 GB DDR4-2133 (geizhals, €159.80 each), up to €1,443 for a single 64 GB DDR4-3200 module (alternate.at); DDR5 (2×32) from €793.
  - A new 870 QVO 2 TB is €550; new NAS HDDs cost €32–52 per TB.
  - Any build that buys 64 GB of new RAM, or new disks, is out of budget. Even the cheapest new RDIMM route puts Build 3 at about €1,010 plus shipping.
  - So the RAM has to come inside a used machine (Builds 1 and 2) or as cheap used server RDIMMs (Build 3, at about €2.5–3.9/GB).
- **Prebuilt harvesting works.** GPUs and SSDs hold their value: an RTX 3060 12 GB asks €285 used, and a used 870 QVO 2 TB €140–350 (median €175). A €900 gaming PC therefore costs about €444 net for the parts you keep.
- **Storage.**
  - The three cheapest large used drives found (€80–95 for 12–16 TB) were all failing according to the sellers' own SMART screenshots. Another set had doctored screenshots.
  - The Toshiba MG08 16 TB pair in Slovenia is the cheapest sound option: 9.6k and 8.9k hours, 0 bad sectors, €160 each. All three builds use it.
- **Power.**
  - Morocco's household tariff is 0.90–1.60 MAD/kWh by tranche. The yearly costs here assume a household above 200 kWh/month, i.e. 1.1676–1.5958 MAD/kWh (≈ €0.105–0.143).
  - Every 10 W of 24/7 idle costs €9.20–12.57 a year.
  - Modern desktop platforms idle at 15–30 W without a graphics card; Xeon E5 v4 workstations at 50–60 W; dual-socket servers at 80–140 W.
- **Rejected on budget:**
  - A Ryzen 9 5950X build with 64 GB ECC (AM4) costs €1,047.36 including a boot SSD. It's the best all-round desktop if you can stretch (§1b, §4).
  - AM5/DDR5 is out of reach at current RAM prices.
  - Dual-socket options are in §4.

**Solver fit** (single-CPU view):

| Solver type | What it needs | Best here |
|---|---|---|
| openEMS (single process), HFSS / FEKO on a base licence (4 cores), Sonnet | Per-core speed and RAM capacity; openEMS scales poorly across many cores (PTS openEMS: i9-13900K 70 MCells/s vs 11–20 on 32–64-core Threadrippers and 21 on an 8-core EPYC 7F32)[^oems] | **Build 1** |
| CST Studio | Uses P-cores only; the base licence covers 2 full sockets; wants all memory channels filled[^cst] | Build 1 (8 fast P-cores), or the dual P720 in §4 for big jobs |
| Large FDTD meshes (MEEP, openEMS MPI), Elmer / Palace (MPI) | Memory bandwidth first[^fdtd] | Builds 2/3 have 4 channels (68–77 GB/s) vs 2 channels on Build 1 (51 GB/s). That is a ~35–50% edge, but Build 1 has 2× the compute. |
| Large FEM direct solves (HFSS, Palace, FEKO MoM) | RAM capacity: 8 GB per core recommended[^hfss] | Build 3 upgrades cheapest (8 slots: 256 GB RDIMM / 512 GB LRDIMM); Build 1 is capped at 128 GB. As delivered, every build has 32–64 GB (2–4 GB per core), so big FEM jobs need a RAM upgrade first. |

**Why the GPUs are sold.** Keeping Build 1's RTX 3060 adds €242 and breaks the budget. openEMS, MEEP and Elmer are CPU-only. Check whether your CST or HFSS licence includes GPU acceleration before you sell it.

---

## 3. The three builds

### Build 1 — i9-12900K desktop in your own case (gaming-PC harvest) — **net €781.80**

| Part | Source listing | Price | Shipping | Notes |
|---|---|---|---|---|
| Gaming PC: i9-12900K, ASUS Prime Z690M-PLUS D4 (mATX), 64 GB DDR4-3200 (2×32), Samsung 980 500 GB NVMe, Samsung 870 QVO 2 TB, RTX 3060 12 GB, Thermaltake TH240 V2 AIO, be quiet! System Power 9 600 W, WLAN card, ATX case | [kleinanzeigen 3522007884](https://www.kleinanzeigen.de/s-anzeige/gaming-pc-i9-12900k-rtx-3060-12gb-64gb-ddr4-2-5tb-ssd/3522007884-228-5681), Waldkraiburg (Bavaria), private, posted 24.09, re-checked active 10.10 | €900 | €0 | **Pickup only**, ~3 h 15 min each way via Salzburg; the seller offers a test on site |
| Toshiba MG08ACA16TE 16 TB #1 (9,639 h, 0 realloc/pending) | [bolha 16514405](https://www.bolha.com/sata3-trdi-diski/prodam-trdi-disk-toshiba-16tb-mg08aca16te-zdrav-oglas-16514405), Cankova SI, private, posted 08.10 | €160 | €17.80 | One Pošta Slovenije 2–5 kg parcel for both drives. bolha's escrow only ships inside Slovenia, so agree the shipment or pick up (~3 h). |
| Toshiba MG08ACA16TE 16 TB #2 (8,938 h, 0 realloc) | [bolha 16514386](https://www.bolha.com/sata3-trdi-diski/trdi-disk-toshiba-16tb-mg08aca16te-zdrav-oglas-16514386), same seller | €160 | — | |
| **Upfront** | | **€1,220** | **€17.80** | **€1,237.80** |
| Resell: RTX 3060 12 GB | asking median €285 (12 ads) × 0.85 | | | −€242 |
| Resell: Samsung 870 QVO 2 TB | asking median €175 (15 used ads, €140–350) × 0.85; new price is €549.99 | | | −€149 |
| Resell: ATX case | asking median €60 (18 ads) × 0.85 | | | −€51 |
| Resell: PCIe WiFi card | asking median €17 (33 ads) × 0.85 | | | −€14 |
| **Net** | | | | **€781.80** |
| Pickup travel (not in net) | Villach–Waldkraiburg–Villach, ~3 h 15 min each way via Salzburg; fuel and the A10 tunnel tolls | | | |

**Why.**
- The best per-core speed in the budget (PassMark single 4,128, about 2× the Xeons) and the highest multi-core throughput (41,099).
- An iGPU, so it runs headless with no extra graphics card. Windows VMs can share the iGPU via SR-IOV using the out-of-tree i915-sriov-dkms driver.
- The lowest idle power.
- Bought separately, the parts you keep would cost about €830–1,100 at current asking prices. That is the 12900K €180–299, a Z690 DDR4 board €160 (median of 2 asks), 64 GB DDR4 €300–445, a 500 GB NVMe €79 (median, n=11), a 240 mm AIO €48 (median, n=12) and a PSU €65 (median, n=11). The harvest saves about €390–650 (comparables in `resale_comps.csv`).

**Performance class.**
- High-end 2021–22 desktop: about 9% below a Ryzen 9 5950X (45,247) in multi-core, with faster single cores ([PassMark](https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core+i9-12900K&id=4597)).
- Limits: dual-channel DDR4 (51 GB/s theoretical, 24–29 GB/s measured STREAM on this class), no AVX-512 (fused off on Alder Lake), no ECC, 128 GB maximum.
- CST uses only the 8 P-cores.
- For MPI solvers and VMs, pin to the P-cores (`lscpu -e` shows which cores are which).

**Idle power: ~30–42 W** at the wall, about **€28–53 a year**.
- Basis: an i5-12500 on Z690 measured 13–18 W at the wall on two boards ([Hardwareluxx](https://www.hardwareluxx.de/community/threads/die-sparsamsten-systeme-30w-idle.1007101/); see also [ComputerBase](https://www.computerbase.de/artikel/prozessoren/intel-core-i3-12100f-b660-test.79265/seite-3)). I estimate 20–30 W for a 12900K without a dGPU, plus 8 W for two MG08 drives ([Toshiba MG08 overview](https://toshiba.semicon-storage.com/content/dam/toshiba-ss-v3/master/en/storage/product-archive/eHDD_MG08_Product-Overview_EOL.pdf): 4 W idle each) and a few watts for the AIO pump and fans.
- Not measured on this exact PC.

**Upgrade path.**
- Add 2× 32 GB for 128 GB.
- Drop-in i9-13900K/14900K. Raptor Lake has a degradation risk, so insist on microcode 0x12B+.
- PCIe 5.0 x16 for a GPU or 10/25 GbE NIC; 3× M.2; 4 SATA ports (enough for 2–3 HDDs plus an SSD).

**Risks.**
- **No ECC** on a 24/7 ZFS host. Acceptable for many homelabs, but a real trade-off.
- **No remote console.** Add a [GL.iNet Comet KVM](https://geizhals.at/gl-inet-comet-gl-rm1-a3636909.html) (€128.99 + €5.90) or [JetKVM](https://geizhals.at/buildjet-jetkvm-a3801988.html) (€129) when the budget allows, plus BIOS "power on after AC loss".
- **The PSU is 80 Plus Bronze** (be quiet! System Power 9). It works, but a used Gold [Corsair RM550x](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/corsair-rm550x-550w-1384681058/) (€65.70 delivered) would save a few watts.
- **AIO pump is a 24/7 wear part.** An Arctic Freezer 36 (€27.29 + €8.90 at alternate.at) is a cheap swap.
- **You must sell four items** to reach €781.80. At 70% of asking the net is €861.90, over budget.
- **Pickup only** in Bavaria.

---

### Build 2 — HP Z440 workstation with 64 GB ECC — **net €747.39**

| Part | Source listing | Price | Shipping | Notes |
|---|---|---|---|---|
| HP Z440: Xeon E5-2690 v4 (14C), 32 GB DDR4, GTX 1660 Super, 240 GB + 256 GB SATA SSDs, Intel AX210 WiFi, Win11 Pro | [willhaben 1544762681](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/hp-z440-e5-2690v4-gtx-1660-super-1544762681/), Feldkirch, private, posted 04.10, re-checked active 10.10 | €350 | €9.90 | **Ships within Austria with willhaben buyer protection** (PayLivery Post ≤31.5 kg) |
| 2× 16 GB DDR4-2133 ECC RDIMM (Samsung M393A2G40DB0-CPB) | [willhaben 1344604666](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/ddr4-server-ram-16-gb-2133p-1344604666/), Hermagor (45 min from Villach), private, 16 modules available | €120 (€60 each; bulk price negotiable) | €2.99 | PayLivery letter, or pick up and test |
| ASUS GT 710 2 GB, passive | [willhaben 1784456640](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/asus-gt710-sl-2gd5-1784456640/), Anger (Styria), private | €20 | €5.70 | Xeon E5 has no iGPU. This passive card replaces the GTX 1660 Super to cut idle power. Skip it (−€25.70) if your Z440 boots headless. |
| 2× Toshiba MG08 16 TB | as in Build 1 | €320 | €17.80 | They go in the Z440's two internal 3.5″ bays |
| **Upfront** | | **€810** | **€36.39** | **€846.39** |
| Resell: GTX 1660 Super | asking median €100 (12 ads) × 0.85 | | | −€85 |
| Resell: Intel AX210 WiFi card | asking median €17 (33 ads) × 0.85 | | | −€14 |
| **Net** | | | | **€747.39** |

**Why.**
- The easiest box to own: a finished, quiet, 11–13.5 kg HP workstation that flies as a normal checked bag.
- ECC RDIMMs (the Z440 takes registered ECC memory only), 64 GB across all 4 channels, and one seller with buyer protection.
- The cheapest build here, with HP's own measured idle figures.

**Performance class.**
- 2016 single-socket workstation: about half of Build 1's throughput (PassMark 19,166 / 2,067), AVX2 only.
- 4-channel memory (68 GB/s with these DDR4-2133 modules) is about 1/3 more bandwidth than Build 1, which helps memory-bound FDTD.

**Idle power: ~55–65 W**, about **€51–82 a year**.
- Basis: HP's [QuickSpecs](https://pcserverandparts.com/content/Spec%20Sheets/Workstations/HP/HP%20Z440/HP%20Z440%20Workstation%20QuickSpecs.pdf) measured 51.2–61.5 W Windows idle for Z440 configurations with Quadro cards and 1–4 HDDs.

**Upgrade path.**
- RAM: 8 slots. HP lists 128 GB maximum; Kingston lists 256 GB with 32 GB RDIMMs. More than 4 DIMMs need HP's memory cooling kit.
- CPU: HP's list stops at 140 W, and the E5-2690 v4 (135 W) is already near the top. 145 W 18–22-core parts are unofficial; one user report says an E5-2697A v4 works after BIOS 02.59.
- NVMe through a PCIe adapter; boot support is mixed per HP forums.

**Risks.**
- **RAM layout unknown.** The ad doesn't say whether the 32 GB is 2×16 or 4×8. If it's 4×8, adding 2×16 means 6 DIMMs (needs the HP cooling kit) and unbalanced channels. Then buy 4×16 instead (4 modules from Hermagor = €240 + €2.99; net becomes €867.39).
- **PSU wattage unknown** (525 W or 700 W). Both are fine without a big GPU. The 525 W unit has only 2 SATA power leads, so you need a splitter for 4 drives.
- **Proprietary HP** board, PSU and chassis: your own case stays unused.
- **No remote console** (no BMC).
- **About half the speed** of Build 1, for more power.

---

### Build 3 — Supermicro X10SRi-F + E5-2697 v4 in your own case (IPMI) — **€790.49**

| Part | Source listing | Price | Shipping | Notes |
|---|---|---|---|---|
| Supermicro X10SRi-F (ATX 12″ × 9.6″, IPMI with HTML5 iKVM, 10× SATA, 8 RDIMM slots) + Xeon E5-2697 v4 (18C) | [kleinanzeigen 3517636108](https://www.kleinanzeigen.de/s-anzeige/server-mb-supermicro-x10sri-f-xeon-e5-2697v4-18-36c-ohne-ram/3517636108-225-29987), Düsseldorf, private, posted 20.09, re-checked active 10.10 | €140 VB | €17.49 | One DHL 5 kg DE→AT parcel together with the RAM, if the seller agrees |
| 4× 8 GB DDR4-2400 ECC RDIMM (Kingston KSM24RS8/8MEI) | [kleinanzeigen 3528701995](https://www.kleinanzeigen.de/s-anzeige/32gb-4x8gb-ddr4-2400-ecc-registered-kingston-ksm24rs8-8mei/3528701995-225-29987), same seller | €99 VB | — | Fills all 4 channels |
| Dynatron R-27 cooler, **narrow ILM** (new) | [alternate.at](https://www.alternate.at/Dynatron/Xeon-CPU-K%C3%BChler-R-27/html/product/1180332), in stock 10.10 | €50.90 | €8.90 | The X10SRi-F uses the **narrow** ILM (manual FAQ heatsink SNK-P0047PS; [STH review](https://www.servethehome.com/?p=12233)), so normal desktop coolers won't fit. The verification note in `deals.csv` says square ILM; Supermicro's documents say narrow, so the narrow cooler is the safe buy. |
| Corsair RM550x 550 W 80 Plus Gold (2018), with box and all cables | [willhaben 1384681058](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/corsair-rm550x-550w-1384681058/), Premstätten (Styria), private | €60 | €5.70 | PayLivery. One EPS cable, which is all a single-socket board needs. |
| Intel D3-S4510 480 GB SATA SSD (20,659 h, 3.1 TB written, health 100%) | [willhaben 1486697881](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/intel-ssd-d3-s4510-series-480gb-1486697881/), Ertl (Lower Austria), private | €65 | €5.70 | No PayLivery option, so ask for an Austrian Post parcel or pick up. |
| 2× Toshiba MG08 16 TB | as in Build 1 | €320 | €17.80 | |
| **Total (nothing to resell)** | | **€734.90** | **€55.59** | **€790.49** |

**Why.**
- The only build in budget with **real out-of-band management**: IPMI/iKVM gives you BIOS, console, power and virtual-ISO access from Singapore. That is a big ease-of-use win for an unattended box.
- ECC, standard ATX parts in **your case**, and an enterprise SSD with power-loss protection for the VMs.
- The most RAM headroom: 8 slots, up to 256 GB with 32 GB RDIMMs or 512 GB with 64 GB LRDIMMs ([Supermicro](https://www.supermicro.com/en/products/motherboard/X10SRi-F)).

**Performance class.**
- 2016 single-socket server: PassMark 21,371 / 2,038, about half of Build 1. AVX2 only.
- 4-channel DDR4-2400 gives 77 GB/s theoretical.
- 32 GB is tight for Windows VMs plus big FEM jobs, so treat RAM as the first upgrade.

**Idle power: ~48–68 W**, about **€44–85 a year**.
- Basis: a lean X10SRM-F (same platform) with an E5-2620 v4 measured 30 W ([Proxmox forum](https://forum.proxmox.com/threads/proxmox-xeon-cpu-upgrade-choice.118047/page-2)). I estimate 40–60 W for a bare X10SRi-F + E5 v4 + RDIMMs + SSD, plus 8 W for two HDDs.

**Upgrade path.**
- RAM: the same seller has [4×16 GB DDR4-2666 RDIMM for €200](https://www.kleinanzeigen.de/s-anzeige/speicher-64gb-ecc-ddr4-2666-4x16gb-thomas-krenn-samsung/3532660727-225-29987) (posted 06.10). Taking it instead of the 4×8 GB gives 64 GB for +€101 (€891.49 total, over budget), or add 4 more 8 GB modules later.
- CPU: E5-2696 v4, 22 cores, [€85 in Heinfels](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/xeon-e5-2696v4-cpu-1569970302/), 1 h 20 min from Villach.
- PCIe 3.0 x16/x8 slots for an NVMe adapter or 10 GbE. There is no onboard M.2.

**Risks.**
- **Payment:** the seller accepts only PayPal Friends & Family or bank transfer, so there is no buyer protection. The seller has top ratings since 2013. Ask for an IPMI screenshot and the BIOS version first.
- **Shipping to Austria** must be agreed.
- **Server fans** default to loud. Set the IPMI fan mode to "Optimal" and lower the fan thresholds for quiet Noctua-type fans.
- **Only 32 GB to start.**
- **About half the speed** of Build 1, for more power.
- **Budget is tight:** €9.51 of headroom.

### Storage risks (all builds)

- **One seller, similar drives.** Both MG08s come from one seller with similar hours and past Chia use, so they may fail close together. Run a long SMART test on arrival and replace the first one that degrades. Drive #2 has reached 56 °C once.
- **A mirror is not a backup.** Keep an off-site copy of anything critical (cloud, or a USB disk in Singapore).
- **The Proxmox/VM SSD is a single disk in every build.** A second power-loss-protected SSD (S4510 €65 or PM883 960 GB €129) is the first thing to buy above budget.
- **Everything depends on this pair.** If it sells, the next sound option (2× MG07 14 TB, €413.49 delivered, ~44k hours) adds €75.69 and puts every build over €800 (§1).

---

## 4. Other options considered

All include the same 2× MG08 16 TB mirror (€337.80) unless noted. Idle figures are estimates with 2 HDDs.

| Option | Parts | Net | Idle | Verdict |
|---|---|---|---|---|
| **Dual CPU, best value: Lenovo P720 with 2× Gold 6140** | [P720, 2× Gold 5118, 64 GB, RTX 3060, €600 VB + DHL €45.49](https://www.kleinanzeigen.de/s-anzeige/lenovo-thinkstation-p720-workstation-rtx-3060-64-gb-ram-/3531669065-228-3721) + 2× Gold 6140 from Linz ([#1](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/intel-xeon-gold-6140-18-kerne-36-threads-lga-3647-server-workstation-1-1309917360/), [#2](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/intel-xeon-gold-6140-18-kerne-36-threads-lga-3647-server-workstation-2-841391018/), €25 + €5.70 each); resell RTX 3060 (€242) + 2 TB HDD (€68) | **€734.69** (upfront €1,044.69) | 65–90 W (€60–113/yr) | 36 cores, AVX-512, 12 channels: as much throughput as Build 1, and 4–6× the bandwidth once all 12 DIMM slots are filled (the listed 64 GB fills at most 8; ask for the layout). But heavy (up to 25.7 kg unpacked per [Lenovo PSREF](https://psref.lenovo.com/syspool/Sys/PDF/ThinkStation/ThinkStation_P720/ThinkStation_P720_Spec.pdf), ~28–31 kg boxed), proprietary, no KVM, NUMA. You can run it on **one** Gold 6140 (~45–75 W, net €703.99) and keep the second socket for later. A [second P720 in Freiburg](https://www.kleinanzeigen.de/s-anzeige/lenovo-thinkstation-p720-computer/3532414379-228-9361) (€690 VB) would come to €1,062.69 with the same upgrades, so it is not a fallback. Head-to-head in §1b. |
| Ryzen 9 5950X + 64 GB ECC (AM4), in your case | [5950X €200 + DHL €14.49](https://www.kleinanzeigen.de/s-anzeige/amd-ryzen-9-5950x-16-kerne-32-threads-am4/3528545945-225-136) + [ASRock B550 Pro4, new, €91.90 + €4.49](https://geizhals.at/asrock-b550-pro4-a2295762.html) + [4×16 GB ECC UDIMM €190 + €14.49](https://www.kleinanzeigen.de/s-anzeige/4x-kingston-kvr24e17d8-16-ddr4-2400-cl17-sdram-ecc-64-gb-/3526472062-225-4445) + [Arctic Freezer 36 CO €23.19 + €8.90](https://www.alternate.at/ARCTIC/Freezer-36-CO-CPU-K%C3%BChler/html/product/100060190) + [RM550x €65.70](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/corsair-rm550x-550w-1384681058/) + [GT 710 €25.70](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/asus-gt710-sl-2gd5-1784456640/) + [Intel S4510 480 GB €70.70](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/intel-ssd-d3-s4510-series-480gb-1486697881/) | €1,047.36 | 35–50 W | **The best single-CPU box if you can stretch €247**: ECC, 45,247 / 3,477 PassMark, low idle. Measured 42 W at the wall on a B550 board, though that was with an RTX 3080 fitted (ComputerBase); it should be lower with a GT 710. Compared side by side in §1b. |
| [i7-13700K PC with RX 7800 XT, Klagenfurt](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/13700k-amd7800xt-mis-b760-gaming-plus-wifi-ram-nicht-enthalten-1877323555/), 35 min from Villach | €750 (or PayLivery €7.90); resell RX 7800 XT (€444); **no RAM included** | ~€306 + RAM + mirror | ~30–40 W | **Ask the seller whether the board is the "B760 Gaming Plus WiFi DDR4".** That model name exists in [DDR4 and DDR5 versions](https://www.scan.co.uk/products/msi-b760-gaming-plus-wifi-intel-b760-s-1700-ddr4-sata3-pcie-40-2x-m2-25gbe-usb-32-gen2-atx). If DDR4: add 64 GB DDR4 (e.g. a 4×16 GB set in Arlsdorf, Carinthia, €190 + €2.99, which the verifier identified as non-ECC desktop RAM) for **≈ €836.79** total, with a 13700K (45,590 / 4,325 PassMark). If DDR5: 64 GB costs €550+, out of budget. PSU brand and cooler are not stated. |
| Supermicro X11DPL-i + 2× Gold 6140 (dual, standard parts, IPMI) | [Kit €299](https://www.kleinanzeigen.de/s-anzeige/supermicro-x11dpl-i-mainboard-mit-2x-intel-xeon-gold-6140/3532639406-225-8105) + [8×8 GB €180, same seller](https://www.kleinanzeigen.de/s-anzeige/8x-8gb-64gb-ddr4-2400-ecc-registered-ram-ksm24rs8-8mei-/3531925755-225-8105) + DHL €17.49 + 2× [Dynatron B-14](https://www.alternate.at/Dynatron/B-14-Square-CPU-K%C3%BChler/html/product/1551241) €110.70 + [RM850x €35.70](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/corsair-rm-850x-netzteil-vollmodular-1704334934/) | €980.69 | 80–100 W | Over budget and power-hungry. **Sources conflict on size and cooler mount:** the first-pass record said narrow ILM, E-ATX 12″×13″ and 16 DIMM slots; Supermicro's [spec page](https://www.supermicro.com/en/products/motherboard/X11DPL-i) and [manual](https://www.supermicro.com/manuals/motherboard/C620/MNL-1946.pdf) say square ILM, 12.08″×10.15″ and 8 slots. I follow Supermicro; check 258 mm board depth against your case. |
| Intel S2600CW dual E5 server | [€460 + €14.80](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/video-workstation-nvidia-geforce-gtx-titan-x-16x-intel-r-xeon-r-cpu-e5-2640-v4-2-40gh-2073820500/), resell Titan X €170 (thin comparable, n=5), + [2× E5-2690 v4 €120](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/2x-xeon-e5-2690v4-cpu-1531003216/) | €762.60 (as listed with 2× E5-2640 v4: **€642.60**, the cheapest dual box) | 85–110 W (€78–138/yr) | 28 cores (20 as listed), 8 channels, BMC, hot-swap bays, standard Intel SSI-EEB board. Heavy, loud, highest power draw. Before the 2690 v4 swap, check that the passive heatsinks and P4000G fans are rated for 135 W. If the listed P3600 NVMe isn't actually included, add an SSD (S4510, +€70.70). |
| ASUS Z10PA-D8 dual E5-2683 v3 (standard parts) | [€490 VB + €28.49](https://www.kleinanzeigen.de/s-anzeige/dual-xeon-workstation-28-kerne-64gb-ram-asus-corsair-top/3530968161-228-2045), resell case + GT 630 (€68) | €788.29 | 80–100 W | Fits your case, but slow Haswell and power-hungry. |
| Dell R730XD (iDRAC8 Enterprise, 16× 3.5″) | [€320 + €14.80](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/dell-poweredge-r730xd-16x-lff-bays-2x-e5-2680-v4-2-40-ghz-16gb-ddr4-ram-1x3-5-2tb-sas-hdds-perc-h730-mini-2x750w-psu-1004962242/) + RAM | ~€840 | 100–150 W | 2U rack server, 28–32 kg, loud. Not for a home in Morocco. |
| Remote console add-on (any build) | [GL.iNet Comet €128.99 + €5.90](https://geizhals.at/gl-inet-comet-gl-rm1-a3636909.html) / [JetKVM €129](https://geizhals.at/buildjet-jetkvm-a3801988.html) | +€135–139 | +2–3 W | Strongly recommended for Builds 1 and 2 once the budget allows |

**Rejected after verification:**
- **Failing drives:** the €80–90 Dortmund 12 TB drives and the €95 Viernheim 16 TB, per their own SMART screenshots.
- **Doctored SMART:** the Donaueschingen Toshiba set.
- **Scam signals:** the €192 (70,000 Ft) Hungarian 5950X (stock press photo, zero-history seller, price cut within hours) and the Tönning 4×32 GB RDIMM for €180.
- **Unknown age, dropped from the CSV:** the Postojna Z440 (renewed ad, months old by its ID), two avito Morocco workstations (bumped old IDs) and a TOP-promoted Slovak 5950X workstation whose real posting date isn't shown.
- **Too weak:** 4-core workstations (Dell 7820 with Silver 4112, HP Z4 G4 W-2123).
- **Over budget:** AM5/DDR5.

---

## 5. Best prebuilt-harvest and bundle deals

### Harvests

Net = price + shipping − realistic resale. Realistic resale = median asking price of comparable ads × 0.85. These are **asking prices, not sold prices**: eBay, the only sold-price source, was blocked from the research machine. Every comparable is in [`resale_comps.csv`](resale_comps.csv). As a cross-check, the US used market for the RTX 3060 12 GB was higher on 10 Oct: [resaleprices.com](https://resaleprices.com/gpu/nvidia-rtx-3060) showed a $321 market average (fair asking range $306–334, 170 listings), and [jawa.gg](https://www.jawa.gg/product/116009/asus-phoenix-geforce-rtx-3060-12gb) had listings at $270–295.

| Prebuilt | Price + ship | Resell (realistic) | Net | What you keep | Same parts bought separately |
|---|---|---|---|---|---|
| [i9-12900K PC, Waldkraiburg](https://www.kleinanzeigen.de/s-anzeige/gaming-pc-i9-12900k-rtx-3060-12gb-64gb-ddr4-2-5tb-ssd/3522007884-228-5681) (**Build 1**) | €900 + €0 | RTX 3060 €242, 870 QVO €149, case €51, WiFi €14 = **€456** | **€444** | 12900K, Z690 DDR4 board, 64 GB, 500 GB NVMe, AIO, PSU (all standard) | ≈ €830–1,100 at asking prices (§3); saves ~€390–650 |
| [HP Z440 E5-2690 v4, Feldkirch](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/hp-z440-e5-2690v4-gtx-1660-super-1544762681/) (**Build 2**) | €350 + €9.90 | GTX 1660S €85, WiFi €14 = **€99** | **€260.90** | Whole workstation (HP proprietary board/PSU), 14C, 32 GB ECC, 2 SSDs | No parts equivalent (proprietary). The nearest standard route (X10SRi-F kit + 32 GB + cooler + PSU) costs €382 before an SSD. |
| [i7-13700K + RX 7800 XT, Klagenfurt](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/13700k-amd7800xt-mis-b760-gaming-plus-wifi-ram-nicht-enthalten-1877323555/) | €750 + €0 | RX 7800 XT €444 (case unstated, not counted) = **€444** | **€306** | 13700K, MSI B760 (DDR4 or DDR5?), 500 GB M.2, 750 W PSU, no RAM | 13700K alone €195–330 used |
| [Lenovo P720 2× Gold 5118](https://www.kleinanzeigen.de/s-anzeige/lenovo-thinkstation-p720-workstation-rtx-3060-64-gb-ram-/3531669065-228-3721) | €600 + €45.49 | RTX 3060 €242, 2 TB HDD €68 = **€310** | **€335.49** | Dual LGA3647 workstation, 64 GB ECC (proprietary) | Standard dual route (X11DPL-i kit + RAM + coolers + PSU) costs €642.89 before storage |
| [Intel S2600CW, Amstetten](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/video-workstation-nvidia-geforce-gtx-titan-x-16x-intel-r-xeon-r-cpu-e5-2640-v4-2-40gh-2073820500/) | €460 + €14.80 | Titan X **€170** (n=5) | **€304.80** | Dual E5 v4, 64 GB, BMC, chassis | No comparable dual-E5 board/CPU/RAM bundle was listed |
| [Ryzen 9 5900X workstation, Röschitz](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/workstation-amd-ryzen-9-5900x-64gb-ddr4-rtx-2080-super-1905851247/) (§1b) | €900 + €0 | RTX 2080 Super €200, NZXT H510 €47 = **€247** | **€653** | 5900X, ROG Crosshair VIII Hero (X570), 64 GB DDR4-3600, NH-D15, AX1000 Titanium, 960 EVO 250 GB | 5900X €180–250 + X570 board €133 (median, n=8) + 64 GB DDR4 €300–445 + NH-D15 €72 (median, n=12) ≈ €685–900; saves ~€30–250 |
| [HP Z840 128 GB](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/powerstation-z840-1401254193/) | €550 + €14.80 | 2× P4000 €246, 2 TB HDD €68 = **€314** | **€250.80** | 2× weak E5-2630 v3, 128 GB RDIMM | Mainly a RAM harvest (128 GB RDIMM ≈ €320–450 privately) |
| [Ryzen 3900X + RTX 3080 Ti, Fischamend](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/gaming-pc-rtx-3080ti-ryzen-9-3900x-32gb-ram-750w-silent-build-1857205100/) | €849 + €0 | 3080 Ti €461, Silent Base 801 €84 = **€545** | **€304** | 3900X, B550, 32 GB, RM750, 360 AIO | Only 32 GB, no SSD, no iGPU; no comparison made |

Every prebuilt in `deals.csv` has its keep/resell breakdown in the `keep_resell_breakdown` column (where nothing is worth reselling, it says so).

**Vendor-lock and proprietary check.**
- **Builds 1 and 3:** only standard ATX parts. The Z690M-PLUS D4 is a retail ASUS board, and the System Power 9 and RM550x are standard ATX PSUs.
- **Build 2:** an HP workstation used as a whole. Its CPU and RDIMMs are standard and reusable.
- No Ryzen PRO, Threadripper PRO or Dell/Lenovo/HPE EPYC (Platform Secure Boot lock risk) is in any build.

### CPU/board/RAM bundles worth knowing

| Bundle | Price | Comment |
|---|---|---|
| [X10SRi-F + E5-2697 v4](https://www.kleinanzeigen.de/s-anzeige/server-mb-supermicro-x10sri-f-xeon-e5-2697v4-18-36c-ohne-ram/3517636108-225-29987) + [4×8 GB, same seller](https://www.kleinanzeigen.de/s-anzeige/32gb-4x8gb-ddr4-2400-ecc-registered-kingston-ksm24rs8-8mei/3528701995-225-29987) (**Build 3**) | €140 VB + €99 VB + €17.49 = €256.49 | Cheapest IPMI platform |
| [5950X](https://www.kleinanzeigen.de/s-anzeige/amd-ryzen-9-5950x-16-kerne-32-threads-am4/3528545945-225-136) + [ASUS Prime B550-Plus, same seller](https://www.kleinanzeigen.de/s-anzeige/asus-prime-b550-plus-mainboard-am4-b550/3527733785-225-136) | €200 + €95 VB + €17.49 = €312.49 | Both bought January 2026, invoice claimed. The core of the AM4 option. |
| [Ryzen 9 3900X + 64 GB (2×32) + MSI B550](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/amd-ryzen-9-3900x-64gb-ddr4-3600-ram-msi-b550-1796397500/) | €590 + €10.60 PayLivery | Austrian, buyer-protected, 2 free DIMM slots. Low idle, but needs a GPU, PSU and disks. |
| [5950X + B550 Aorus Pro AC + 32 GB + Mugen 5](https://pc.bazos.sk/inzerat/196316116/amd-ryzen-9-5950x-gigabyte-b550-aorus-pro-ac-32gb-ra.php) | €420 | Slovakia (~7 h); shipping must be agreed |
| [X11DPL-i + 2× Gold 6140](https://www.kleinanzeigen.de/s-anzeige/supermicro-x11dpl-i-mainboard-mit-2x-intel-xeon-gold-6140/3532639406-225-8105) + [8×8 GB](https://www.kleinanzeigen.de/s-anzeige/8x-8gb-64gb-ddr4-2400-ecc-registered-ram-ksm24rs8-8mei-/3531925755-225-8105) | €496.49 | Dual-CPU; see §4 |

---

## 6. Buy-now list

On your go-ahead, in this order. Nothing has been bought and nobody has been contacted.

| Step | Listing | Cost | Why now |
|---|---|---|---|
| 1 (all builds) | [Toshiba MG08 16 TB #1](https://www.bolha.com/sata3-trdi-diski/prodam-trdi-disk-toshiba-16tb-mg08aca16te-zdrav-oglas-16514405) + [#2](https://www.bolha.com/sata3-trdi-diski/trdi-disk-toshiba-16tb-mg08aca16te-zdrav-oglas-16514386), Cankova SI | €320 + €17.80 | The only sound used 16 TB drives at ~€10/TB found anywhere. Every build uses them; without them every build goes over budget. |
| 2a (Build 1) | [i9-12900K PC, Waldkraiburg](https://www.kleinanzeigen.de/s-anzeige/gaming-pc-i9-12900k-rtx-3060-12gb-64gb-ddr4-2-5tb-ssd/3522007884-228-5681), pickup | €900 | 64 GB as 2×32 at this price is rare in 2026. Then list the RTX 3060, 870 QVO, case and WiFi card on willhaben. |
| 2b (Build 2) | [HP Z440, Feldkirch](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/hp-z440-e5-2690v4-gtx-1660-super-1544762681/), then the [Hermagor RDIMMs](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/ddr4-server-ram-16-gb-2133p-1344604666/) and the [GT 710](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/asus-gt710-sl-2gd5-1784456640/) | €350 + €9.90, €120 + €2.99, €20 + €5.70 | The verifier rated the Z440 likely to sell fast. Cheap Austrian shipping with buyer protection. |
| 2c (Build 3) | [X10SRi-F + E5-2697 v4](https://www.kleinanzeigen.de/s-anzeige/server-mb-supermicro-x10sri-f-xeon-e5-2697v4-18-36c-ohne-ram/3517636108-225-29987) + [4×8 GB](https://www.kleinanzeigen.de/s-anzeige/32gb-4x8gb-ddr4-2400-ecc-registered-kingston-ksm24rs8-8mei/3528701995-225-29987), Düsseldorf; then the R-27, RM550x and S4510 (§3) | €239 VB + €17.49 | Not urgent: it has been unsold for 20 days after a €199 → €140 cut. But it is the only IPMI board in budget. |
| 2d (P720 option) | [Lenovo P720](https://www.kleinanzeigen.de/s-anzeige/lenovo-thinkstation-p720-workstation-rtx-3060-64-gb-ram-/3531669065-228-3721), then [Gold 6140 #1](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/intel-xeon-gold-6140-18-kerne-36-threads-lga-3647-server-workstation-1-1309917360/) + [#2](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/intel-xeon-gold-6140-18-kerne-36-threads-lga-3647-server-workstation-2-841391018/) | €600 VB + €45.49, 2× (€25 + €5.70) | The 6140 ads turn 30 days old on 13.10. |
| Optional | [Samsung PM883 960 GB, Vienna](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/samsung-pm883-ssd-2-5-960gb-sata-6-0gbps-1327243837/) | €129 + €2.99 | A second power-loss-protected VM SSD for any build (above budget). |

**Fallback HDDs if the MG08 pair goes:**
- [2× Toshiba MG07 14 TB, Mülheim DE](https://www.kleinanzeigen.de/s-anzeige/toshiba-enterprise-festplatte-14tb-mg07aca14te/3534592806-225-2064): €198 each + DHL €17.49. Clean SMART, ~44k hours, seller must agree to ship. Adds €75.69 to every build.
- [IronWolf Pro 16 TB, Villach-Auen](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/seagate-ironwolf-pro-16-tb-nas-hdd-long-generic-smart-geprueft-923408488/): €299 each, 8.2k h, several units. Test the exact serial on site.
- The [Berlin HC550 18 TB](https://www.kleinanzeigen.de/s-anzeige/western-digital-ultrastar-dc-hc550-18tb-gebraucht-voll-funktio/3509342612-225-3368) (€199 VB) passes 30 days on 11.10.

---

## 7. Market reference prices found (Oct 2026)

"Used" means private asking prices on kleinanzeigen/willhaben/bolha unless stated. New prices are from geizhals.at, billiger.de or the named shop.

| Item | Price found | Source / basis |
|---|---|---|
| Ryzen 9 5950X | used €200–320 (typ. €250–300) · new €315.05 (billiger.de) / €319.68 (geizhals.at) / €326.56 (cyberport.at) | [KA](https://www.kleinanzeigen.de/s-pc-zubehoer-software/ryzen-9-5950x/k0c225), [billiger](https://www.billiger.de/search?searchstring=AMD+Ryzen+9+5950X&sort=price_asc), [geizhals](https://geizhals.at/amd-ryzen-9-5950x-100-100000059wof-a2392527.html). *Sources differ by up to €11.51.* |
| Ryzen 9 5900X / 3950X / 3900X | used €180–250 / €180–200 / €90–160 | KA, willhaben (≈50 ads) |
| i9-12900K / i7-13700K | used €180–299 / €195–330 | [KA](https://www.kleinanzeigen.de/s-pc-zubehoer-software/i7-13700k/k0c225) |
| Ryzen 9 9900X / 9950X | new €299.99 / €443.94 | [billiger.de](https://www.billiger.de/search?searchstring=AMD+Ryzen+9+9950X&sort=price_asc) |
| Xeon E5-2690 v4 / E5-2696 v4 / Gold 6140 / Gold 6230 | €55 (€120 pair) / €85 / €25 / €80 each (€160 pair) private · refurb Gold 6230 €89.99, EPYC 7302 €199.99 | willhaben, bolha, [servershop24](https://www.servershop24.de/komponenten/cpus-prozessoren/amd/socket-sp3/) |
| ASRock B550 Pro4 (new) | €91.90 + €4.49 (alza.at via geizhals) | [geizhals](https://geizhals.at/asrock-b550-pro4-a2295762.html) |
| New server boards: X11SPi-TF / H12SSL-i / ROMED8-2T | €610.79 / €829 / €868.98 | [geizhals](https://geizhals.at/?fs=h12ssl-i&hloc=at&hloc=de) |
| DDR4 RDIMM 16 GB / 32 GB | used €35–75 / €60–150 (≈€2.5–3.9/GB) · refurb 32 GB €259.99–299.99 · new 32 GB from €159.80 (2133) | KA/willhaben, [servershop24](https://www.servershop24.de/komponenten/arbeitsspeicher/ddr4/pc4-2666/32gb/), [geizhals](https://geizhals.at/?cat=ramddr3&xf=7500_DDR4~7761_RDIMM~7569_32GB&sort=p). *Refurb costs more than new here.* |
| DDR4 desktop 64 GB (2×32) | used €300–445 · new €478.47+ | KA, [billiger](https://www.billiger.de/search?searchstring=DDR4+3200+64GB+Kit+2x32GB&sort=price_asc) |
| DDR5 64 GB (2×32) | used €500–650 · new €793+ | KA, billiger.de |
| WD Red Plus 8 TB / 12 TB (new) | €336.32 (billiger.de) vs €378.88 (geizhals.at) / €472.33 vs €536.15 | [billiger](https://www.billiger.de/search?searchstring=WD+Red+Plus+8TB&sort=price_asc), [geizhals](https://geizhals.at/?cat=hde7s&sort=r). *DE vs AT sources conflict by about 13%.* |
| Toshiba MG09 18 TB / Seagate Exos X18 18 TB (new) | €575.73 / €800 | billiger.de |
| Used 12–18 TB enterprise HDD | typ. €300–450 for 16–18 TB · best sound: MG08 16 TB €160, HC550 18 TB €199 VB, MG07 14 TB €198, HGST He12 12 TB €164 (HU) | KA, willhaben, bolha |
| Samsung 990 Pro 2 TB (new) | €299.89 (billiger.de) vs €369 (geizhals.at) | *Sources conflict.* |
| Samsung 870 QVO 2 TB | new €549.99 · used €140–350 (median €175, 15 used asks) | [billiger](https://www.billiger.de/search?searchstring=Samsung+870+QVO+2TB&sort=price_asc), KA |
| Enterprise SATA SSD 480–960 GB with power-loss protection | used €65–149 · new PM893 960 GB €882.93 | KA/willhaben, geizhals |
| ATX PSU 550–650 W Gold | used €30–70 · new Corsair RM650e €79.99 + €6.39 | [geizhals](https://geizhals.at/?cat=gehps&fs=corsair+rm+e&sort=p) |
| Coolers for Xeons | Dynatron R-27 (narrow ILM) €50.90; Dynatron B-14 (LGA3647 square ILM) €50.90; + €8.90 shipping | [alternate.at](https://www.alternate.at/Dynatron/Xeon-CPU-K%C3%BChler-R-27/html/product/1180332) |
| GPU resale (asks): RTX 3060 12 GB / RX 7800 XT / 2080 Super / GTX 1660 Super / Titan X | €285 / €522 / €235 / €100 / €200 (medians, n=5–33); PCIe WiFi card €17 (n=33) | KA + willhaben asks, all in [`resale_comps.csv`](resale_comps.csv). No sold-price data (eBay blocked). US RTX 3060 on 10.10: $321 market average, fair asking range $306–334 ([resaleprices.com](https://resaleprices.com/gpu/nvidia-rtx-3060)). |
| Remote KVM | GL.iNet Comet €128.99 + €5.90; JetKVM €129; PiKVM V4 Mini €309 | [geizhals](https://geizhals.at/gl-inet-comet-gl-rm1-a3636909.html) |
| Shipping DE→AT (DHL, online) | 2 kg €14.49 · 5 kg €17.49 · 10 kg €22.49 · 20 kg €28.49 · 31.5 kg €45.49 | [dhl.de](https://www.dhl.de/de/privatkunden/pakete-versenden/weltweit-versenden/land/oesterreich.html) |
| Shipping SI→AT (Pošta Slovenije Connect) / within AT (willhaben PayLivery) | ≤2 kg €15.50 · 2–5 kg €17.80 / €2.99–14.80 | [posta.si price list](https://www.posta.si/zasebno-site/Documents/Ceniki/Novi-ceniki/Cenik%20Connect%20paket%20-%20velja%20od%201.1.2026.pdf), listings |
| Morocco (on arrival) | Micron 5300 PRO 3.84 TB enterprise SSD 3,190 DH (€286.82); PSUs at EU-new prices; CPUs at par with EU new (9950X €449 vs €444) to well above the EU used market (used 5950X €378 vs €200–320) | [avito](https://www.avito.ma/fr/abattoirs/autres_mat%C3%A9riels_electroniques/Micron_5300_PRO_3_84TB_SSD_Neuf_57252724.htm), [ultrapc.ma](https://www.ultrapc.ma/) |

FX on 9–10 Oct 2026: 1 EUR = 11.1221 MAD (open.er-api.com), 365.08 HUF and 24.369 CZK (ECB).

---

## 8. Running it in Morocco

- **Electricity.**
  - Household tariff: 0.90–1.60 MAD/kWh by tranche. Above 150 kWh/month, several sources say *all* kWh are billed at the tranche reached, so a 24/7 server can push a household into a dearer tranche. The costs in this report assume more than 200 kWh/month, i.e. 1.1676–1.5958 MAD/kWh (≈ €0.105–0.143).
  - Each 10 W of idle is ≈ 88 kWh ≈ €9.20–12.57 a year. Build 1 idles about 20–25 W below Builds 2 and 3 (midpoint to midpoint).
  - To save more:
    - Set the BIOS to a power-saving profile and enable C-states and ASPM.
    - On Build 1, run `powertop --auto-tune` and remove the dGPU.
    - Let the HDDs spin down only if the NAS is idle for long periods; constant spin-up/down wears drives.
- **Flying it** (Royal Air Maroc, Europe zone): an extra 23 kg piece costs €100; a 23–32 kg piece €77 overweight; 158–203 cm €70 oversize ([RAM](https://www.royalairmaroc.com/int-en/excess-baggage)). Austrian Airlines refuses bags over 32 kg ([Austrian](https://www.austrian.com/at/en/excess-baggage)).
  - Builds 1 and 3 weigh your case plus parts.
  - The P720 is up to 25.7 kg unpacked (Lenovo PSREF), so ~28–31 kg boxed. That is over 23 kg, so the €77 overweight fee applies, and it is close to Austrian's 32 kg refusal limit.
  - Build 2 (HP Z440, 431.8 × 168.9 × 444.7 mm, 11–13.5 kg) fits normal checked baggage when boxed.
  - Carry the HDDs separately in anti-static bags and foam, ideally in the cabin.
  - Remove the AIO radiator or tower cooler before checking it in.
- **Customs.** The ADII Marhaba circular gives Moroccans resident abroad (MRE) a duty-free allowance of 25,000 DH once a year for non-commercial personal effects ([circular 6465/311](https://www.bladi.net/img/pdf/circulaire-marhaba-2023-mre.pdf)). I found no clear rule for non-MRE travellers or for desktop computers specifically. The source is dated 2023, so confirm the 2026 rules with ADII before flying, and keep invoices or screenshots of purchase prices.
- **Remote access from Singapore.**
  - Use a VPN (WireGuard or Tailscale) into Proxmox. Never expose IPMI to the internet.
  - Set the BIOS to "power on after AC loss".
  - Build 3 has IPMI/iKVM built in. For Builds 1 and 2, a €135 KVM (§4) plus a smart plug covers BIOS-level recovery.
  - Inside the budget, the minimum is "power on after AC loss" plus a Wi-Fi smart plug, which lets you hard power-cycle the box. I have not priced a smart plug listing. Full BIOS-level access needs the €135 KVM, which doesn't fit any build under €800.
- **Heat, dust, power.**
  - Put the box in a ventilated room, not a closet.
  - Set drive-temperature alerts at 50 °C in Proxmox, and clean the dust filters every few months.
  - Add a UPS with USB shutdown (NUT). It is not in the budget and I have not priced one.
  - Set the BIOS to power on after AC loss.

---

## 9. Questions to ask each seller before buying (nobody has been contacted)

- **For you:** which case do you own (model), and is it in Villach or already in Morocco? If it is in Morocco, Builds 1 and 3 fly as a bag of parts of a few kg, and I can check board fit (EEB/E-ATX) against the model.

- **Waldkraiburg 12900K PC (Build 1):**
  - Book a pickup with an on-site test: memtest plus a short stress test.
  - Is the BIOS current?
  - Any WHEA errors?
  - Exact case model (for resale)?
- **Feldkirch Z440 (Build 2):**
  - Is the 32 GB 2×16 or 4×8?
  - PSU wattage (525 or 700 W)?
  - BIOS version?
  - Does it boot without a graphics card?
- **Hermagor RDIMMs (Build 2):** bulk price for 2 (or 4) modules; test on pickup (45 min away).
- **Düsseldorf X10SRi-F seller (Build 3):**
  - Will you ship board + CPU + 4×8 GB to Austria in one DHL parcel?
  - Can I pay with PayPal Goods & Services (I'll cover the fee)?
  - IPMI screenshot and BIOS version?
- **Ertl S4510 seller (Build 3):** will you post via Austrian Post?
- **MG08 ×2 (Cankova, all builds):** will you post both to Austria via Pošta Slovenije (€17.80)? Current SMART readout and the Toshiba warranty-check result for both serials.
- **Waltershausen P720 (dual-CPU option):**
  - Which Xeon Gold model, and how is the 64 GB laid out (module size and slots)?
  - PSU wattage (690 or 900 W)?
  - Is there a BIOS supervisor password or any asset/Computrace lock? Can you show proof of purchase from the company (the inventory sticker)?
  - Will you ship it to Austria by DHL, and what does it weigh packed (DHL's limit is 31.5 kg)?
- **Linz Gold 6140 seller (P720 option):** will you combine both CPUs in one parcel? Are the contact pads clean?
- **Stralsund 5950X seller (Ryzen option):** will you ship insured by DHL to Austria? Can I pay with PayPal Goods & Services? Invoice copy?
- **Hochheim ECC RAM seller (Ryzen option):** will you ship to Austria? Exact module part numbers (ECC UDIMM)?
- **Röschitz 5900X (Ryzen option):** weekend viewing with a stress test; exact NVMe/SSD and PSU model?
- **Villach 3900X (Ryzen option):** test in a board on pickup (the seller account is new, June 2026).
- **Klagenfurt 13700K (alternative):** is the board the DDR4 version? PSU brand? Is a cooler included?

---

## 10. Method, coverage and limitations

**Coverage.**
- **Sources checked:**
  - Marketplaces: kleinanzeigen.de, willhaben.at, bolha.com (SI), hardverapro.hu, bazos.cz/sk, subito.it (Friuli), markt.de, quoka.de, avito.ma.
  - Moroccan shops: ultrapc.ma, setupgame.ma, techspace.ma, myordi.ma.
  - Refurbishers: servershop24, it-market, afbshop, esm, harlander, itsco, lapstore, techbuyer, memorysolution, compuram, ram-koenig.
  - Retail: geizhals.at (intermittent), billiger.de, alternate.at/.de, cyberport.at, MediaMarkt.at.
- **Volume:**
  - About 1,000 listings were screened. Every one of the 378 rows in `deals.csv` was opened. Four rows of unknown age were dropped (§4).
  - Shortlisted listings were re-opened by an independent "skeptic" pass that read the SMART screenshots and the CPU-Z/BIOS photos. That pass caught the failing drives, wrong CPU SKUs, a non-ECC "server" RAM kit and doctored screenshots.

**Blocked from the research machine.** I could not use these, so prices from them are not included:
- **eBay (all domains).** This rules out eBay sold listings.
- **Others:** idealo, leboncoin, galaxus, e-tec, mylemon, proshop, computeruniverse, jumia.ma, mytek.ma, pcgamer.ma, msi.com.
- **hardwareluxx marketplace:** login required.
- **Mindfactory:** captcha.

**Resale values.**
- They are asking-price medians from kleinanzeigen + willhaben ads posted 9 Sep – 10 Oct 2026, minus 15%. They are not sold prices, because eBay's sold filter was unreachable. The US RTX 3060 market (resaleprices.com, $321 average on 10.10) sits above the EU asks used here, so the RTX 3060 figure is not inflated.
- Every comparable is in [`resale_comps.csv`](resale_comps.csv), and the medians used are in [`resale_comps_summary.csv`](resale_comps_summary.csv). Search-card comparables are raw (some bundles and accessories are mixed in; the median absorbs them).
- On 10.10 I re-gathered two comparables. The 870 QVO now uses 15 used asks (median €175, was 3 asks at €200). The PCIe WiFi card uses 33 asks (median €17, was €20 with no saved source). This lowered Build 1's resale by €24 and Build 2's by €3.
- Still thin: Fractal Define (n=3), Titan X (n=5) and Silent Base (n=5). The Titan X is flagged in the S2600CW row.
- Resale assumes you sell inside Austria via willhaben (the buyer pays PayLivery).

**Shipping rules.** Kleinanzeigen "Versand möglich" and "Direkt kaufen" are **Germany-only**. Every German item needs the seller to agree to ship to Austria, at the DHL prices above, or a pickup. This is flagged per row in `ships_to_at`.

**Payment risk.** Several sellers accept only PayPal Friends & Family or bank transfer, which gives no buyer protection. These include the X10SRi-F/RAM seller in Düsseldorf (Build 3), the X11DPL-i RAM seller in Hockenheim and the Stralsund 5950X seller. This is flagged in `notes`.

**Idle power** figures are estimates from the measurements cited. They are not measured on these exact machines. Sources:
- [HP Z440 QuickSpecs](https://pcserverandparts.com/content/Spec%20Sheets/Workstations/HP/HP%20Z440/HP%20Z440%20Workstation%20QuickSpecs.pdf)
- [ComputerBase Ryzen 5000](https://www.computerbase.de/artikel/prozessoren/amd-ryzen-5000-test.74008/seite-6) and [ComputerBase Alder Lake](https://www.computerbase.de/artikel/prozessoren/intel-core-i3-12100f-b660-test.79265/seite-3)
- [Hardwareluxx low-idle thread](https://www.hardwareluxx.de/community/threads/die-sparsamsten-systeme-30w-idle.1007101/)
- [Proxmox forum, X10SRM-F](https://forum.proxmox.com/threads/proxmox-xeon-cpu-upgrade-choice.118047/page-2)
- [r/homelab P720 thread](https://www.reddit.com/r/homelab/comments/1jcv0c7/what_kind_of_idle_power_impact_should_i_expect/)
- [Toshiba MG08](https://toshiba.semicon-storage.com/content/dam/toshiba-ss-v3/master/en/storage/product-archive/eHDD_MG08_Product-Overview_EOL.pdf)
- [ServeTheHome DIMM power](https://www.servethehome.com/ddr4-dimms-system-power-consumption-tested/)

PassMark figures are from the [cpubenchmark.net](https://www.cpubenchmark.net/) CPU pages (e.g. [2× Gold 6140](https://www.cpubenchmark.net/cpu.php?cpu=Intel+Xeon+Gold+6140+%40+2.30GHz&id=3132&cpuCount=2), [5950X](https://www.cpubenchmark.net/cpu.php?cpu=AMD+Ryzen+9+5950X&id=3862)). Cinebench R23 figures are from [CGDirector](https://www.cgdirector.com/cinebench-r23-scores-updated-results/).

**Few options in some areas.**
- Single-socket boards newer than Broadwell were scarce, and they were either expensive or paired with few cores. Examples: a W680-ACE board at €292, an X11SRA-F + W-2135 (6C) at €350, an X11SRA + W-2133 + 64 GB at €495, and SP3 boards at €279–399.
- Sound large HDDs under €200 were scarce. Found: the MG08 16 TB pair (€160 each), the HC550 18 TB (€199 VB), an MG07 14 TB in Mülheim (€198) and an HGST He12 12 TB in Hungary (€164).
- Nothing with a Ryzen 9 fits €800 at current prices (§1b).

[^fdtd]: Ruiz-Cabello et al., *PLoS ONE* 15(9) e0238115 (2020), [doi:10.1371/journal.pone.0238115](https://doi.org/10.1371/journal.pone.0238115): "the main factor limiting FDTD performance … is the memory bandwidth".
[^oems]: [OpenBenchmarking pts/openems](https://openbenchmarking.org/test/pts/openems).
[^cst]: 3DS hardware recommendations; [GoEngineer on CST licensing](https://www.goengineer.com/blog/introducing-unified-license-model-for-cst-studio-suite) (2023): the base licence gives full solver access to two CPU sockets.
[^hfss]: [Ansys blog, W. Slagter (2020)](https://ansys.synopsys.com/blog/hardware-tips-to-accelerate-simulation): 8 GB RAM per core, fill all channels; four cores without HPC licences.
