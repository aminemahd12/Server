# Home server deal research — Villach → Morocco

*Listings were checked on 9–10 Oct 2026 (two independent passes; the parts in the three builds were re-opened a third time on 10 Oct). Prices are as listed. Shipping is to Villach. "Net" = price + shipping − realistic resale of the parts you don't need.*

**Every listing is in [`deals.csv`](deals.csv)**: 378 rows, each opened, all ≤ 30 days old and none reserved or sold. Rows used in a build are at the top.

---

## 1. Recommendation in one table

| | Build 1 — Dual Xeon Gold workstation | Build 2 — Fast-core desktop | Build 3 — Dual Xeon server, 8-channel |
|---|---|---|---|
| Core platform | Lenovo ThinkStation P720 (harvest the GPU), CPUs swapped to 2× Xeon Gold 6140 | i9-12900K gaming PC (harvest the GPU, QLC SSD, case) | Intel S2600CW2R pedestal server (harvest the Titan X), CPUs swapped to 2× E5-2690 v4 |
| Cores / threads | 36 / 72 (AVX-512, 2 FMA) | 16 / 24 (8 P + 8 E) | 28 / 56 (AVX2) |
| RAM | 64 GB ECC RDIMM, 12 slots | 64 GB DDR4 (2×32, non-ECC), 4 slots | 64 GB ECC RDIMM (8×8, every channel filled), 16 slots |
| NAS | 2× Toshiba MG08 16 TB, ZFS mirror (16 TB usable) | same | same |
| PassMark multi / single | 41,109 / 2,089 | 41,099 / 4,128 | 30,547 / 2,054 |
| Memory bandwidth (theoretical) | up to 256 GB/s (12 ch) | 51 GB/s (2 ch) | 137 GB/s (8 ch DDR4-2133) |
| Idle power (estimate, with 2 HDDs) | ~65–90 W | ~30–42 W | ~85–110 W |
| Upfront cash | **€1,044.69** | **€1,237.80** | **€932.60** |
| Resale of unused parts | −€310 | −€480 | −€170 |
| **Net cost** | **€734.69** | **€757.80** | **€762.60** |
| Uses your case? | No (Lenovo chassis) | Yes (mATX board, standard ATX PSU) | No (server pedestal, SSI-EEB board) |
| Remote console | No KVM (Intel AMT can't do KVM without an iGPU) | None | BMC/IPMI (power, sensors, serial). KVM needs an Intel RMM4 key. |

**My pick:**
- **Build 1** if your solvers are CST, MEEP, Elmer, Palace or large FDTD meshes, i.e. throughput and memory bandwidth.
- **Build 2** if you mostly run HFSS or FEKO on a base licence (4 cores), openEMS, or interactive Windows VMs. It is also the cheapest to run 24/7 and is the only build that goes into your own case.
- **Build 3** is the fallback dual-socket box if the P720 seller won't ship to Austria.

The reasoning is in §3 and the solver-by-solver notes in §2.

> Nothing has been bought and no seller has been contacted. §9 lists what to ask each seller. Several of these will sell fast; see the buy-now list in §6.

---

## 2. What the October 2026 market looks like (and why the builds look like this)

- **DRAM and NAND shortage.**
  - New 2×32 GB DDR4 costs from €478; 2×32 GB DDR5 from €793; 64 GB DDR4 ECC RDIMM €1,443 new at alternate.at.
  - A new 990 Pro 2 TB is €300–369, and a new 870 QVO 2 TB is €550.
  - New NAS HDDs cost €36–52 per TB.
  - Any build that buys 64 GB of new RAM, or new disks, is out of budget.
- **Server RAM from decommissioned machines is the bargain.** Used private DDR4 RDIMM costs about €2.5–3.9/GB, against €5–8/GB for desktop DDR4 and €8–17/GB for DDR5. That favours Xeon platforms that take RDIMMs.
- **CPUs are cheap; boards and RAM are not.**
  - Xeon Gold 6140 (18 cores): €25 each in Linz.
  - E5-2690 v4: €55, or €120 per pair, in East Tyrol.
  - 5950X: €200.
  - Standalone server boards are rare and expensive: new X11SPi-TF €611, H12SSL-i €829.
- **Prebuilt harvesting works because GPUs and SSDs hold value.** An RTX 3060 12 GB asks €285 used, and a 2 TB QLC SSD asks about €200. A €900 PC can therefore cost you about €420 net.
- **Used HDDs are where storage value is**, but check SMART. The three cheapest large drives found (€80–95 for 12–16 TB) were all failing according to the sellers' own SMART screenshots, and another set had doctored screenshots. The Toshiba MG08 16 TB pair in Slovenia is the cheapest sound option: 9.6k and 8.9k hours, 0 bad sectors, €160 each.
- **Platforms tested and rejected on budget, all with the same 16 TB mirror:**

  | Platform | Total | Over budget by |
  |---|---|---|
  | Standard-parts dual Gold 6140 (Supermicro X11DPL-i, IPMI) | €980.69 | €181 |
  | Ryzen 9 5950X + 64 GB ECC | €982.37 | €182 |
  | AM5 with 64 GB DDR5 | > €1,000 | > €200 |

  They are listed in §4 in case you can stretch.

**Solver fit:**

| Solver type | What it needs | Best build here |
|---|---|---|
| FDTD (openEMS, MEEP, CST transient) on big meshes | Memory bandwidth first[^fdtd] | 1 (then 3), with every DIMM channel populated |
| openEMS single process | It scales poorly across many cores. PTS openEMS: i9-13900K 70 MCells/s vs 11–21 on 32–64-core Threadripper/EPYC[^oems] | 2 |
| CST Studio | The base licence covers 2 full sockets; uses P-cores only; wants all channels filled[^cst] | 1 |
| Ansys HFSS | 4 cores without HPC licences; RAM capacity and per-core speed matter most[^hfss] | 2 if base licence; 1 with HPC packs |
| FEKO MoM / Sonnet | RAM capacity, then per-core speed[^feko] | 1 (768 GB max) for big models; 2 for small ones |
| Elmer / Palace / MEEP (MPI) | Scales across sockets; bandwidth-bound iterative solvers | 1 |

---

## 3. The three builds

### Build 1 — Dual Xeon Gold 6140 workstation (Lenovo P720 harvest) — **net €734.69**

| Part | Source listing | Price | Shipping | Notes |
|---|---|---|---|---|
| Lenovo ThinkStation P720: 2× Xeon Gold 5118, 64 GB DDR4 ECC, RTX 3060 12 GB, 250 GB SSD, 2 TB HDD, Lenovo PSU | [kleinanzeigen 3531669065](https://www.kleinanzeigen.de/s-anzeige/lenovo-thinkstation-p720-workstation-rtx-3060-64-gb-ram-/3531669065-228-3721), Waltershausen DE, private, posted 04.10 | €600 VB | €45.49 | CPUs identified from the seller's Device Manager photo. Shipping is DHL 31.5 kg DE→AT online price; the seller prefers pickup, so it must be agreed. |
| Xeon Gold 6140 #1 (18C, 2 AVX-512 FMA) | [willhaben 1309917360](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/intel-xeon-gold-6140-18-kerne-36-threads-lga-3647-server-workstation-1-1309917360/), Linz, private | €25 | €5.70 | PayLivery. Posted 13.09 (27 days old). |
| Xeon Gold 6140 #2 | [willhaben 841391018](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/intel-xeon-gold-6140-18-kerne-36-threads-lga-3647-server-workstation-2-841391018/), Linz, same seller | €25 | €5.70 | PayLivery |
| Toshiba MG08ACA16TE 16 TB #1 (9,639 h, 0 realloc) | [bolha 16514405](https://www.bolha.com/sata3-trdi-diski/prodam-trdi-disk-toshiba-16tb-mg08aca16te-zdrav-oglas-16514405), Cankova SI, private, posted 08.10 | €160 | €17.80 | One Pošta Slovenije 2–5 kg parcel for both drives. The bolha escrow only ships inside Slovenia, so agree the shipment or pick up (~3 h). |
| Toshiba MG08ACA16TE 16 TB #2 (8,938 h, 0 realloc) | [bolha 16514386](https://www.bolha.com/sata3-trdi-diski/trdi-disk-toshiba-16tb-mg08aca16te-zdrav-oglas-16514386), same seller | €160 | — | |
| **Upfront** | | **€970.00** | **€74.69** | **€1,044.69** |
| Resell: RTX 3060 12 GB | Asking median €285 (n=12) × 0.85 | | | −€242 |
| Resell: 2 TB 3.5″ HDD | Asking median €80 (n=45) × 0.85 | | | −€68 |
| **Net** | | | | **€734.69** |

Not counted, but available as upside: the two removed Gold 5118s (one comparable ad at €25).

**Why this one.**
- It is the only dual-socket AVX-512 machine that fits the budget with a proper NAS mirror.
- After the €61 CPU swap it has 36 cores at PassMark 41,109 multi, the same throughput as a Ryzen 9 5950X (45,247).
- It has 12 memory channels against the Ryzen's 2. Measured STREAM on dual Skylake-SP is 194–214 GB/s tuned, against 24–29 GB/s on dual-channel desktops.
- Enterprise chassis, ECC everywhere, 12 DIMM slots, two onboard M.2.
- The Gold 6140 is the same generation as the factory 5118, so no BIOS gamble. The P720 is rated for up to 165 W CPUs and lists Gen-2 (Cascade Lake) support.

**Performance class.**
- Dual-socket HPC workstation: in the class of a Dell R740 or Precision 7820 with 2× Gold 6140.
- Single-thread is about 2.1k PassMark, roughly 60% of a Zen 3 core. Interactive Windows VMs feel like a 2018 workstation, not a gaming PC.
- It shines on parallel FDTD/FEM/MoM jobs. Pin each job to one socket (`numactl --cpunodebind/--membind`, or a NUMA-enabled VM): remote-socket bandwidth is about 42% lower.

**Idle power: ~65–90 W at the wall** with 2 HDDs and an SSD, about **€60–113 a year** in Morocco.
- Basis: a P720 with one CPU measured 31 W idle (user report); +15–20 W for the second socket; ~2 W per RDIMM; 4 W per MG08 drive (Toshiba datasheet).
- This is an estimate; the dual-CPU figure is not measured.

**Upgrade path.**
- **RAM:** fill all 12 DIMM slots for full bandwidth. Add 4× 8 GB RDIMM if the 64 GB is 8×8 GB; the RAM can go to 768 GB.
- **CPUs:** Cascade Lake Gold, up to 165 W. 2× Gold 6230 cost €160 in Ljubljana ([bolha 16019968](https://www.bolha.com/intel-xeon/2x-intel-xeon-gold-6230-srf8w-2.10ghz-20-cores-40-threads-oglas-16019968)).
- **Storage:** 2× onboard M.2 for an NVMe VM pool; 4× 3.5″ bays plus flex bays.

**Risks.**
- **Proprietary:** the Lenovo board, PSU and front panel stay in the Lenovo case. Your own case stays unused.
- **Weight:** up to 25.7 kg (Lenovo PSREF). Expect a Royal Air Maroc overweight fee: €77 for a 23–32 kg piece. Carry the HDDs separately, padded.
- **No remote KVM.** Intel AMT 11 exists but AMT KVM needs an iGPU, which Xeon SP lacks. Add a JetKVM or GL.iNet Comet (~€135, outside the budget; see §4) for BIOS-level access from Singapore.
- **RAM layout unknown.** If it is 4×16 GB, only 4 of 12 channels are used and the bandwidth advantage mostly disappears: one benchmark of 2× Gold 6140 with 4 DIMMs measured 41 GB/s. Ask before buying.
- **PSU wattage unknown** (690 W or 900 W). Both are fine without a GPU.
- **DHL insures only €500.** Ask the seller about extra insurance, or arrange a courier pickup.
- **The Linz 6140 ads are 27 days old.** Fallbacks: 2× Gold 6138 (20C, €25 each, [bazos.sk Bratislava](https://pc.bazos.sk/inzerat/196262284/intel-xeon-gold-6138-20-jadier-40-vlakien.php)), or the 6230 pair above.
- **Boot disk.** The included 250 GB SSD will hold Proxmox and 2–3 Windows VMs. A Samsung PM883 960 GB with power-loss protection ([willhaben, €129 + €2.99](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/samsung-pm883-ssd-2-5-960gb-sata-6-0gbps-1327243837/)) is the first upgrade (net would be €866.68).

---

### Build 2 — Fast-core i9-12900K desktop (gaming-PC harvest) — **net €757.80**

| Part | Source listing | Price | Shipping | Notes |
|---|---|---|---|---|
| Gaming PC: i9-12900K, ASUS Prime Z690M-PLUS D4, 64 GB DDR4-3200 (2×32), Samsung 980 500 GB NVMe, Samsung 870 QVO 2 TB, RTX 3060 12 GB, Thermaltake TH240 AIO, be quiet! System Power 9 600 W, WLAN card, case | [kleinanzeigen 3522007884](https://www.kleinanzeigen.de/s-anzeige/gaming-pc-i9-12900k-rtx-3060-12gb-64gb-ddr4-2-5tb-ssd/3522007884-228-6396), Waldkraiburg DE, private, posted 24.09 | €900 | €0 | Pickup only, ~3 h 15 min each way via Salzburg; a test on site is offered. |
| 2× Toshiba MG08 16 TB | as in Build 1 | €320 | €17.80 | |
| **Upfront** | | **€1,220** | **€17.80** | **€1,237.80** |
| Resell: RTX 3060 12 GB | median €285 × 0.85 | | | −€242 |
| Resell: Samsung 870 QVO 2 TB | median €200 (n=3, €190/200/299) × 0.85; new price is €549.99 | | | −€170 |
| Resell: ATX case | median €60 (n=18) × 0.85 | | | −€51 |
| Resell: PCIe WiFi card | median €20 (n=38) × 0.85 | | | −€17 |
| **Net** | | | | **€757.80** |

Keep: CPU, board, 64 GB, 980 500 GB (Proxmox + VMs), AIO and PSU. They all go into **your own case** (mATX board, standard ATX PSU).

**Why this one.**
- The best per-core speed in the budget: PassMark single 4,128, about 2× the Xeons.
- Multi-core throughput equals Build 1 (41,099).
- It has an iGPU, which allows headless install and Windows-VM graphics through SR-IOV with the out-of-tree i915-sriov-dkms driver.
- It has by far the lowest idle draw.
- A 64 GB DDR4 kit alone asks €350–445 used. Bought separately, the kept parts would cost about €900 at asking prices (see §5).

**Performance class.**
- High-end 2021–22 desktop. Similar to a 5950X in throughput and much faster per core.
- **But:** dual-channel DDR4 (51 GB/s theoretical, 24–29 GB/s STREAM), no AVX-512 (fused off on Alder Lake), no ECC, and a 128 GB RAM ceiling.
- CST uses only the 8 P-cores. For MPI codes, pin ranks or VMs to P-cores (`lscpu -e`).

**Idle power: ~30–42 W** with 2 HDDs, about **€28–53 a year**.
- Basis: the i5-12500 on Z690 measured 13–18 W at the wall on two boards; I estimate 20–30 W for a 12900K without a dGPU, plus 8 W for HDDs and a few watts for the AIO pump and fans.

**Upgrade path.**
- Add 2× 32 GB for 128 GB.
- i9-13900K/14900K drop-in. Raptor Lake degradation risk: insist on microcode 0x12B+.
- PCIe 5.0 x16 for a GPU or 10/25 GbE NIC; 3× M.2.
- Only 4 SATA ports, enough for a 2–3 disk pool.

**Risks.**
- **No ECC** on a 24/7 ZFS host.
- **Bronze PSU.** System Power 9: fine but not efficient at 30 W. A used Corsair RM550x is €65.70 delivered if you want to swap.
- **AIO pump is a 24/7 wear part.** A €27 Arctic Freezer 36 would be a cheap swap.
- **No out-of-band management.**
- **Pickup-only in Bavaria**, and the €480 net saving depends on you actually selling four items. The QLC SSD comparable is thin (3 ads), so the net could be €30–50 higher.
- **Least upgradable for RAM** of the three.

---

### Build 3 — Intel S2600CW dual-Xeon server, CPUs upgraded — **net €762.60**

| Part | Source listing | Price | Shipping | Notes |
|---|---|---|---|---|
| Intel S2600CW2R (SSI-EEB) in Intel P4000G pedestal | [willhaben 2073820500](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/video-workstation-nvidia-geforce-gtx-titan-x-16x-intel-r-xeon-r-cpu-e5-2640-v4-2-40gh-2073820500/), Amstetten NÖ, private, posted 08.10 | €460 | €14.80 | See note below for the full spec. €14.80 is the Austrian Post ≤31.5 kg rate, if the seller agrees; otherwise pickup ~3 h 15 min. |
| 2× Xeon E5-2690 v4 (14C, matched pair) | [willhaben 1531003216](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/2x-xeon-e5-2690v4-cpu-1531003216/), Heinfels (East Tyrol), private, posted 20.09 | €120 | €0 | Pickup ~1 h 20 min from Villach; the seller tests and gives a function guarantee. |
| 2× Toshiba MG08 16 TB | as in Build 1 | €320 | €17.80 | They go straight into the hot-swap bays. |
| **Upfront** | | **€900** | **€32.60** | **€932.60** |
| Resell: GTX Titan X (Maxwell 12 GB) | median €200 (n=5) × 0.85 | | | −€170 |
| **Net** | | | | **€762.60** |

What the S2600CW listing includes:
- Board: Intel S2600CW2R (SSI-EEB, 16 DIMM slots, 10× SATA, BMC).
- CPUs: 2× E5-2640 v4 (10C each).
- RAM: 64 GB as 8×8 GB RDIMM, one per channel, so every channel is filled.
- Storage: 4-bay 3.5″ hot-swap backplane, plus drives (see risks).
- PSU: 750 W redundant cage, one module fitted.
- GPU: GTX Titan X (resold).

Not counted, but available as upside: the 2× E5-2640 v4 removed (one comparable ad at €50 with cooler). Without the CPU upgrade the net is **€642.60** (20 cores).

**Why this one.**
- Every memory channel is already populated. Measured dual-Broadwell STREAM is about 130 GB/s with DDR4-2400; expect ~115 GB/s at 2133.
- 28 cores after a €120 swap; 16 DIMM slots; a real BMC; hot-swap bays for the NAS.
- It is a standard Intel server board, not a Dell/HP/Lenovo proprietary one.
- It is the fallback dual-socket option close to Villach. Both sellers are in Austria; one is a 1 h 20 min drive.

**Performance class.** 2016-era dual-socket server: PassMark 30,547 multi / 2,054 single, AVX2 only. That is about ¾ of Builds 1–2 in throughput and about 2× Build 2's memory bandwidth.

**Idle power: ~85–110 W**, about **€78–138 a year**.
- Basis: a Dell R630 with 2× E5-2640 v4 measured 84 W after switching the BIOS to power-saving (140 W in the performance profile).
- Server fans are louder than Build 1.

**Upgrade path.**
- CPUs: up to 22-core E5-2699 v4 / 2696 v4. Check Intel's supported-processor list for 145 W parts on the S2600CW2R first. An E5-2696 v4 is €85 at the same Heinfels seller.
- RAM: 16 DIMM slots, up to 512 GB RDIMM or 1 TB LRDIMM.
- Remote KVM: an Intel RMM4 Lite key turns on the BMC's remote console. No current listing was found.

**Risks.**
- **Heavy, deep pedestal** (~20–25 kg). Your case stays unused; the EEB board likely won't fit a normal ATX case.
- **Drive list contradicts the photos.** The text lists one Intel P3600 400 GB NVMe, but screenshots and photos show about 500 GB + 1 TB + 800 GB drives. Ask which drives are included: a P3600 would be an ideal VM drive.
- **Only one 750 W PSU module** in the redundant cage.
- **No KVM licence.**
- **Seller says "last price"** and the box has been idle 2 years.

---

## 4. Other builds considered (and why they are not in the top 3)

All include the same 2× MG08 16 TB mirror (€337.80) unless noted.

| Option | Parts | Upfront | Net | Verdict |
|---|---|---|---|---|
| **A. HP Z440, light and simple** | [Z440 E5-2690 v4, 32 GB, GTX 1660S, 2 SSDs, AX210](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/hp-z440-e5-2690v4-gtx-1660-super-1544762681/) (Feldkirch, €350 + €9.90 PayLivery) + 2× 16 GB RDIMM from [Hermagor](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/ddr4-server-ram-16-gb-2133p-1344604666/) (€60 each + €2.99) | €820.69 | **€718.69** (−1660S €85, −WiFi €17) | Best low-risk option. 11–13.5 kg, flies as a normal bag; HP-measured idle 51–62 W; ships with buyer protection. But 14 cores (19,166 PassMark), 4 channels, no KVM. Assumes the 32 GB is 2×16; ask. |
| **B. Supermicro X11DPL-i + 2× Gold 6140 (standard parts, IPMI)** | [Kit €299](https://www.kleinanzeigen.de/s-anzeige/supermicro-x11dpl-i-mainboard-mit-2x-intel-xeon-gold-6140/3532639406-225-8105) + [8×8 GB RDIMM €180, same seller](https://www.kleinanzeigen.de/s-anzeige/8x-8gb-64gb-ddr4-2400-ecc-registered-ram-ksm24rs8-8mei-/3531925755-225-8105) + DHL €17.49 + 2× [Dynatron B-14 square-ILM cooler](https://www.alternate.at/Dynatron/B-14-Square-CPU-K%C3%BChler/html/product/1551241) €110.70 + [Corsair RM850x, 2 EPS cables, €30 + €5.70](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/corsair-rm-850x-netzteil-vollmodular-1704334934/) | €980.69 | €980.69 | **The one to stretch for.** Same CPU power as Build 1 with real IPMI/iKVM, all 8 channels filled, fits your case (12.08″ × 10.15″, 14 mm deeper than ATX), and an M.2 slot. €181 over budget. The seller takes bank transfer or PayPal F&F only. Arctic Freezer 4U-M does **not** fit LGA3647, and narrow-ILM coolers (Dynatron B5/B11, SilverStone XE02-3647N) won't fit this square-ILM board. |
| C. ASUS Z10PA-D8 dual E5-2683 v3 (standard ATX parts) | [Complete build €490 VB](https://www.kleinanzeigen.de/s-anzeige/dual-xeon-workstation-28-kerne-64gb-ram-asus-corsair-top/3530968161-228-2045), Essen, + DHL 20 kg €28.49; includes RM850x, coolers, 960 EVO 250 GB | €856.29 | **€788.29** (−case €51, −GT 630 €17) | Fits your case and stays within budget, but slower Haswell (23,346 PassMark), only 4 of 8 channels filled, no IPMI module, ~1,000 km away. |
| D. Ryzen 9 5950X + 64 GB ECC (AM4) | [5950X €200](https://www.kleinanzeigen.de/s-anzeige/amd-ryzen-9-5950x-16-kerne-32-threads-am4/3528545945-225-136) + [ASUS Prime B550-Plus €95 VB, same seller](https://www.kleinanzeigen.de/s-anzeige/asus-prime-b550-plus-mainboard-am4-b550/3527733785-225-136) + DHL €17.49 + [4×16 GB ECC UDIMM €190 + €14.49](https://www.kleinanzeigen.de/s-anzeige/4x-kingston-kvr24e17d8-16-ddr4-2400-cl17-sdram-ecc-64-gb-/3526472062-225-4445) + Arctic Freezer 36 €36.19 + [RM550x €65.70](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/corsair-rm550x-550w-1384681058/) + [GT 710 €25.70](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/asus-gt710-sl-2gd5-1784456640/) | €982.37 | €982.37 | Best all-round desktop (45,247 / 3,477 PassMark, ECC, ~35–50 W idle), but €182 over budget and dual-channel only. |
| E. Supermicro X10SRi-F + E5-2697 v4 (IPMI, budget) | [Board+CPU €140 VB](https://www.kleinanzeigen.de/s-anzeige/server-mb-supermicro-x10sri-f-xeon-e5-2697v4-18-36c-ohne-ram/3517636108-225-29987) + [4×8 GB RDIMM €99 VB, same seller](https://www.kleinanzeigen.de/s-anzeige/32gb-4x8gb-ddr4-2400-ecc-registered-kingston-ksm24rs8-8mei/3528701995-225-29987) + DHL €17.49 + narrow-ILM Dynatron R-27 €59.80 + RM550x €65.70 + [Intel S4510 480 GB €65](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/intel-ssd-d3-s4510-series-480gb-1486697881/) + ~€5.70 | €790.49 | €790.49 | Cheapest real IPMI/iKVM box in your case, but only 32 GB and 18 Broadwell cores (21,371 PassMark). Seller takes PayPal F&F or bank transfer only. |
| F. Dell R730XD 16×LFF, iDRAC8 Enterprise | [€320 + €14.80 PayLivery](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/dell-poweredge-r730xd-16x-lff-bays-2x-e5-2680-v4-2-40-ghz-16gb-ddr4-ram-1x3-5-2tb-sas-hdds-perc-h730-mini-2x750w-psu-1004962242/) + RAM | ~€840 | ~€840 | Best remote management and 16 bays, but a 28–32 kg, 75 cm-deep 2U rack server: noisy and impractical to fly. |
| HP Z840 128 GB | [€550 + €14.80](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/powerstation-z840-1401254193/), net €250.80 after 2× P4000 and 2 TB HDD | — | €588.60 + SSD | Weakest CPUs (2× E5-2630 v3 at DDR4-1866). Upgrading to E5-2690 v4 needs the 1125 W PSU (wattage unknown). ~22 kg. |
| Remote console add-on (any build) | [GL.iNet Comet €128.99 + €5.90](https://geizhals.at/gl-inet-comet-gl-rm1-a3636909.html) or [JetKVM €129](https://geizhals.at/buildjet-jetkvm-a3801988.html) | +€135–139 | | Strongly recommended for a box in Morocco run from Singapore, but it doesn't fit inside €800 with any build. |

Rejected after verification:
- The €80–90 Dortmund 12 TB drives and the €95 Viernheim 16 TB drive are failing per their own SMART screenshots.
- The Donaueschingen Toshiba set has doctored SMART screenshots.
- The €219 Hungarian 5950X uses a stock press photo and comes from a zero-history seller.
- The Tönning 4×32 GB RDIMM for €180 shows scam signals.
- The "€5" Graz CPU lot is really €70 for the useful CPU, and that CPU exceeds the X11DPL-i's 140 W limit.
- 4-core workstations (Dell 7820 with Silver 4112, HP Z4 G4 W-2123) are too weak for the solvers.
- AM5/DDR5 is out of budget at current RAM prices.

---

## 5. Best prebuilt-harvest and bundle deals

### Harvests (net = price + shipping − realistic resale; resale = median asking price of comparable ads × 0.85)

| Prebuilt | Price + ship | Resell (realistic) | Net | What you keep | Same parts bought separately (asking prices) |
|---|---|---|---|---|---|
| [i9-12900K PC, Waldkraiburg](https://www.kleinanzeigen.de/s-anzeige/gaming-pc-i9-12900k-rtx-3060-12gb-64gb-ddr4-2-5tb-ssd/3522007884-228-6396) | €900 + €0 | RTX 3060 €242, 870 QVO 2 TB €170, case €51, WiFi €17 = **€480** | **€420** | 12900K, Z690 DDR4 board, 64 GB, 500 GB NVMe, AIO, PSU | 12900K €180–299 + Z690 DDR4 board ~€160 + 64 GB DDR4 €350–385 + 500 GB NVMe ~€79 + AIO ~€50 + PSU ~€40 ≈ **€860–1,010**. Harvest saves ~€440–590. |
| [Lenovo P720 2× Gold 5118](https://www.kleinanzeigen.de/s-anzeige/lenovo-thinkstation-p720-workstation-rtx-3060-64-gb-ram-/3531669065-228-3721) | €600 + €45.49 | RTX 3060 €242, 2 TB HDD €68 = **€310** | **€335.49** | Dual LGA3647 workstation with 64 GB ECC, PSU, coolers, 250 GB SSD | No separate-parts equivalent (proprietary). The nearest standard route (X11DPL-i kit + 64 GB + coolers + 2-EPS PSU) costs **€642.89** before storage. |
| [Intel S2600CW server, Amstetten](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/video-workstation-nvidia-geforce-gtx-titan-x-16x-intel-r-xeon-r-cpu-e5-2640-v4-2-40gh-2073820500/) | €460 + €14.80 | Titan X **€170** | **€304.80** | Dual E5 v4, 64 GB (8 ch), BMC, 4 hot-swap bays, chassis, PSU | X10DRi + 2× E5-2630 v4 (€150 VB + €17.49) + 8×8 GB RDIMM (€160 + Packeta) + 2-EPS PSU (€35.70) ≈ €368, with no chassis or bays |
| [HP Z840 128 GB, Lower Austria](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/powerstation-z840-1401254193/) | €550 + €14.80 | 2× P4000 €246, 2 TB HDD €68 = **€314** | **€250.80** | 2× E5-2630 v3 (weak), 128 GB RDIMM, chassis | 128 GB RDIMM alone ≈ €320–450 privately. Mainly a RAM harvest. |
| [HP Z440 2690 v4, Feldkirch](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/hp-z440-e5-2690v4-gtx-1660-super-1544762681/) | €350 + €9.90 | GTX 1660S €85, WiFi €17 = **€102** | **€257.90** | 14C workstation, 32 GB, 2 SSDs | |
| [Dell 7820, Wiesbaden](https://www.kleinanzeigen.de/s-anzeige/dell-precision-7820-workstation/3510016429-228-4911) | €380 + €28.49 | Quadro P4000 **€123** | **€285.49** | 4-core Silver 4112, 32 GB: needs a CPU swap | |
| [Z10PA-D8 build, Essen](https://www.kleinanzeigen.de/s-anzeige/dual-xeon-workstation-28-kerne-64gb-ram-asus-corsair-top/3530968161-228-2045) | €490 + €28.49 | case €51, GT 630 €17 = **€68** | **€450.49** | Standard dual-socket board, 2× 14C, 64 GB, RM850x | |
| [Ryzen 3900X + RTX 3080 Ti, Fischamend](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/gaming-pc-rtx-3080ti-ryzen-9-3900x-32gb-ram-750w-silent-build-1857205100/) | €849 + €0 | 3080 Ti €461, Silent Base 801 €84 = **€545** | **€304** | 3900X, B550, 32 GB, RM750, 360 AIO | Only 32 GB; pickup near Vienna |

Every prebuilt in `deals.csv` has its keep/resell breakdown in the `keep_resell_breakdown` column.

**Vendor-lock and proprietary check.**
- Lenovo, Dell and HP workstation and server boards and PSUs are proprietary: use the machine as a whole.
- Their CPUs and RDIMMs are standard and reusable.
- No Threadripper PRO, Ryzen PRO or EPYC from Dell/Lenovo/HPE (PSB vendor-lock risk) is in any recommended build. The only P620 found (TR PRO, Morocco) is likely Lenovo-locked and was rejected.

### CPU/board/RAM bundles worth knowing

| Bundle | Price | Comment |
|---|---|---|
| [X11DPL-i + 2× Gold 6140](https://www.kleinanzeigen.de/s-anzeige/supermicro-x11dpl-i-mainboard-mit-2x-intel-xeon-gold-6140/3532639406-225-8105) + [8×8 GB RDIMM, same seller](https://www.kleinanzeigen.de/s-anzeige/8x-8gb-64gb-ddr4-2400-ecc-registered-ram-ksm24rs8-8mei-/3531925755-225-8105) | €299 + €180 + €17.49 = €496.49 | Best standard-parts server bundle: 36C, AVX-512, IPMI. Needs coolers and a 2-EPS PSU (§4 B). |
| [X10SRi-F + E5-2697 v4](https://www.kleinanzeigen.de/s-anzeige/server-mb-supermicro-x10sri-f-xeon-e5-2697v4-18-36c-ohne-ram/3517636108-225-29987) + [4×8 GB, same seller](https://www.kleinanzeigen.de/s-anzeige/32gb-4x8gb-ddr4-2400-ecc-registered-kingston-ksm24rs8-8mei/3528701995-225-29987) | €140 VB + €99 VB + €17.49 = €256.49 | Cheapest IPMI platform |
| [5950X](https://www.kleinanzeigen.de/s-anzeige/amd-ryzen-9-5950x-16-kerne-32-threads-am4/3528545945-225-136) + [ASUS Prime B550-Plus, same seller](https://www.kleinanzeigen.de/s-anzeige/asus-prime-b550-plus-mainboard-am4-b550/3527733785-225-136) | €200 + €95 VB + €17.49 = €312.49 | Both bought January 2026, invoice claimed. |
| [ASUS Z11PA-D8 + Silver 4208 + 2×16 GB DDR4-2933](https://www.kleinanzeigen.de/s-anzeige/asus-z11pa-d8-bundle-xeon-silver-4208-32-gb-ecc-ram/3534722825-228-6799) | €220 VB + €17.49 | Standard-size dual LGA3647 board; add 2× Gold 6140 (€61.40) for 36C. Needs RAM and a second cooler. |
| [Ryzen 9 3900X + 64 GB (2×32) + MSI B550](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/amd-ryzen-9-3900x-64gb-ddr4-3600-ram-msi-b550-1796397500/) | €590 + €10.60 PayLivery | Austrian, buyer-protected, 2 free DIMM slots. PayLivery insurance stops at €510. |
| [5950X + B550 Aorus Pro AC + 32 GB + Mugen 5](https://pc.bazos.sk/inzerat/196316116/amd-ryzen-9-5950x-gigabyte-b550-aorus-pro-ac-32gb-ra.php) | €420 | Slovakia (Martin, ~7 h). Shipping must be agreed. |

---

## 6. Buy-now list (likely to sell fast)

| # | Listing | Why it will go |
|---|---|---|
| 1 | [Toshiba MG08 16 TB ×2](https://www.bolha.com/sata3-trdi-diski/prodam-trdi-disk-toshiba-16tb-mg08aca16te-zdrav-oglas-16514405), €160 each (SI) | The only sound used 16 TB drives at ~€10/TB found anywhere. All three builds use them. |
| 2 | [Lenovo P720 2× Gold 5118](https://www.kleinanzeigen.de/s-anzeige/lenovo-thinkstation-p720-workstation-rtx-3060-64-gb-ram-/3531669065-228-3721), €600 VB | 229 views in 5 days; price already cut from €650. |
| 3 | [Xeon Gold 6140 ×2, Linz](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/intel-xeon-gold-6140-18-kerne-36-threads-lga-3647-server-workstation-1-1309917360/), €25 each | Cheap, and the ads are near the end of willhaben's run. |
| 4 | [i9-12900K PC, Waldkraiburg](https://www.kleinanzeigen.de/s-anzeige/gaming-pc-i9-12900k-rtx-3060-12gb-64gb-ddr4-2-5tb-ssd/3522007884-228-6396), €900 | 64 GB as 2×32 at this price is rare in 2026. |
| 5 | [HP Z440 E5-2690 v4, Feldkirch](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/hp-z440-e5-2690v4-gtx-1660-super-1544762681/), €350 | Verifier rated it high sell-fast. |
| 6 | [Ryzen 9 5950X, Stralsund](https://www.kleinanzeigen.de/s-anzeige/amd-ryzen-9-5950x-16-kerne-32-threads-am4/3528545945-225-136), €200 | €50–100 under market. |
| 7 | [Dell R730XD, Vienna](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/dell-poweredge-r730xd-16x-lff-bays-2x-e5-2680-v4-2-40-ghz-16gb-ddr4-ram-1x3-5-2tb-sas-hdds-perc-h730-mini-2x750w-psu-1004962242/), €320 | Price cut today from €440. |
| 8 | [Samsung PM883 960 GB, Vienna](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/samsung-pm883-ssd-2-5-960gb-sata-6-0gbps-1327243837/), €129 | Posted 09.10. Enterprise SSD with power-loss protection, PayLivery. |
| 9 | [Corsair RM850x, Graz](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/corsair-rm-850x-netzteil-vollmodular-1704334934/), €30 | Only needed for option B (two EPS cables). |
| 10 | [HP Z840 2× E5-2667 v3, Graz](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/hp-z840-workstation-2x-xeon-e5-2667-v3-16-kerne-32-threads-lga2011-3-1502285148/), €185 | Cheap dual-socket base, high sell-fast. Needs RAM, GPU and disks. |

**Ageing out:** the [Lassnitzhöhe 4×16 GB RDIMM set](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/64gb-4x16gb-ddr4-rdimm-ram-934742061/) hits 30 days on 10.10, and the [Berlin HC550 18 TB](https://www.kleinanzeigen.de/s-anzeige/western-digital-ultrastar-dc-hc550-18tb-gebraucht-voll-funktio/3509342612-225-3368) on 11.10. Both were active when checked.

---

## 7. Market reference prices found (Oct 2026)

"Used" means private asking prices on kleinanzeigen/willhaben/bolha unless stated. New prices are from geizhals.at, billiger.de or the named shop.

| Item | Price found | Source / basis |
|---|---|---|
| Ryzen 9 5950X | used €200–320 (typ. €250–300) · new €315.05 (billiger.de) / €319.68 (geizhals.at) / €326.56 (cyberport.at) | [KA](https://www.kleinanzeigen.de/s-pc-zubehoer-software/ryzen-9-5950x/k0c225), [billiger](https://www.billiger.de/search?searchstring=AMD+Ryzen+9+5950X&sort=price_asc), [geizhals](https://geizhals.at/amd-ryzen-9-5950x-100-100000059wof-a2392527.html). *Sources differ by up to €11.* |
| Ryzen 9 5900X / 3950X / 3900X | used €180–250 / €180–200 / €90–160 | KA, willhaben (≈50 ads) |
| i9-12900K / i7-13700K | used €180–299 / €195–330 | [KA](https://www.kleinanzeigen.de/s-pc-zubehoer-software/i7-13700k/k0c225) |
| Ryzen 9 9900X / 9950X | new €299.99 / €443.94 | [billiger.de](https://www.billiger.de/search?searchstring=AMD+Ryzen+9+9950X&sort=price_asc) |
| Xeon Gold 6140 / 6230 / E5-2690 v4 / E5-2696 v4 | €25 / €80 each (€160 pair) / €55 (€120 pair) / €85 private · refurb Gold 6230 €89.99, EPYC 7302 €199.99 | willhaben, bolha, [servershop24](https://www.servershop24.de/komponenten/cpus-prozessoren/amd/socket-sp3/) |
| ASRock B550 Pro4 (new) | €91.90 + €4.49 (alza.at via geizhals) | [geizhals](https://geizhals.at/asrock-b550-pro4-a2295762.html) |
| New server boards: X11SPi-TF / H12SSL-i / ROMED8-2T | €610.79 / €829 / €868.98 | [geizhals](https://geizhals.at/?fs=h12ssl-i&hloc=at&hloc=de) |
| DDR4 RDIMM 16 GB / 32 GB | used €35–75 / €60–150 (≈€2.5–3.9/GB) · refurb 32 GB €259.99–299.99 · new 32 GB from €159.80 (2133) | KA/willhaben, [servershop24](https://www.servershop24.de/komponenten/arbeitsspeicher/ddr4/pc4-2666/32gb/), [geizhals](https://geizhals.at/?cat=ramddr3&xf=7500_DDR4~7761_RDIMM~7569_32GB&sort=p). *Refurb costs more than new here.* |
| DDR4 desktop 64 GB (2×32) | used €300–445 · new €478.47+ | KA, [billiger](https://www.billiger.de/search?searchstring=DDR4+3200+64GB+Kit+2x32GB&sort=price_asc) |
| DDR5 64 GB (2×32) | used €500–650 · new €793+ | KA, billiger.de |
| WD Red Plus 8 TB / 12 TB (new) | €336.32 (billiger.de) vs €378.88 (geizhals.at) / €472.33 vs €536.15 | [billiger](https://www.billiger.de/search?searchstring=WD+Red+Plus+8TB&sort=price_asc), [geizhals](https://geizhals.at/?cat=hde7s&sort=r). *DE vs AT sources conflict by about 12%.* |
| Toshiba MG09 18 TB / Seagate Exos X18 18 TB (new) | €575.73 / €800 | billiger.de |
| Used 16–18 TB enterprise HDD | typ. €300–450 · best sound: MG08 16 TB €160, HC550 18 TB €199 VB | KA, willhaben, bolha |
| Samsung 990 Pro 2 TB (new) | €299.89 (billiger.de) vs €369 (geizhals.at) | *Sources conflict.* |
| Samsung 870 QVO 2 TB | new €549.99 · used €190–299 | [billiger](https://www.billiger.de/search?searchstring=Samsung+870+QVO+2TB&sort=price_asc), KA |
| Enterprise SATA SSD 960 GB with power-loss protection | used €100–149 · new PM893 €882.93 | KA/willhaben, geizhals |
| ATX PSU 550–650 W Gold | used €30–70 · new Corsair RM650e €79.99 + €6.39 | [geizhals](https://geizhals.at/?cat=gehps&fs=corsair+rm+e&sort=p) |
| GPU resale (asks): RTX 3060 12 GB / 3070 / 2080 Super / Quadro P4000 / Titan X | €285 / €260 / €235 / €145 / €200 (medians, n=5–33) | KA + willhaben. US cross-check for the RTX 3060: $290 average ([resaleprices.com](https://resaleprices.com/gpu/nvidia-rtx-3060), Jul 2026); $278–300 sold ([jawa.gg](https://www.jawa.gg/product/116009/asus-phoenix-geforce-rtx-3060-12gb)). |
| Shipping DE→AT (DHL, online) | 2 kg €14.49 · 5 kg €17.49 · 10 kg €22.49 · 20 kg €28.49 · 31.5 kg €45.49 | [dhl.de](https://www.dhl.de/de/privatkunden/pakete-versenden/weltweit-versenden/land/oesterreich.html) |
| Shipping SI→AT (Pošta Slovenije Connect) / within AT (willhaben PayLivery) | ≤2 kg €15.50 · 2–5 kg €17.80 / €2.99–14.80 | [posta.si price list](https://www.posta.si/zasebno-site/Documents/Ceniki/Novi-ceniki/Cenik%20Connect%20paket%20-%20velja%20od%201.1.2026.pdf), listings |
| Morocco (on arrival) | Micron 5300 PRO 3.84 TB enterprise SSD 3,190 DH (€286.82); PSUs at EU-new prices; CPUs/RAM 0–32% dearer than the EU | [avito](https://www.avito.ma/fr/abattoirs/autres_mat%C3%A9riels_electroniques/Micron_5300_PRO_3_84TB_SSD_Neuf_57252724.htm), [ultrapc.ma](https://www.ultrapc.ma/) |

FX on 9–10 Oct 2026: 1 EUR = 11.1221 MAD (open.er-api.com), 365.08 HUF and 24.369 CZK (ECB).

---

## 8. Running it in Morocco

- **Electricity.** Household tariff is 1.0732–1.5958 MAD/kWh depending on tranche (≈ €0.10–0.14). Above 150 kWh/month, several sources say *all* kWh are billed at the tranche reached. Each 10 W of 24/7 idle is ≈ 88 kWh ≈ €9–13 a year.
- **Flying it.** On Royal Air Maroc (Europe zone): an extra 23 kg piece costs €100; a 23–32 kg piece costs €77 overweight; 158–203 cm costs €70 oversize ([RAM](https://www.royalairmaroc.com/int-en/excess-baggage)). Austrian Airlines refuses bags over 32 kg ([Austrian](https://www.austrian.com/at/en/excess-baggage)).
  - Builds 1 and 3 are 20–25 kg boxed, so expect an overweight fee.
  - Build 2 weighs as much as your case plus parts.
  - Pack the HDDs separately in anti-static bags and foam, ideally in the cabin.
  - Remove the tower cooler or AIO radiator stress points before checking it in.
- **Customs.** The ADII Marhaba circular gives Moroccans resident abroad (MRE) a duty-free allowance of 25,000 DH once a year for non-commercial personal effects ([circular 6465/311](https://www.bladi.net/img/pdf/circulaire-marhaba-2023-mre.pdf)). I did not find a clear rule for non-MRE travellers or for desktop computers specifically. Check with ADII before flying, and keep invoices or screenshots of the purchase prices.
- **Remote access from Singapore.**
  - Use a VPN (WireGuard or Tailscale) into Proxmox. Never expose IPMI or a BMC to the internet.
  - Set the BIOS to "power on after AC loss".
  - Builds 1 and 2 need a KVM add-on for BIOS-level recovery (§4). Build 3's BMC gives power control and serial console without one.

---

## 9. Questions to ask each seller before buying (nobody has been contacted)

- **P720 (Waltershausen):**
  - DIMM layout (8×8 or 4×16?) and PSU wattage (690 or 900 W)?
  - Will you ship DHL to Austria, with extra insurance above €500?
  - Price with shipping?
- **Linz Gold 6140 ×2:** are both still available? Combined PayLivery possible?
- **MG08 ×2 (Cankova):** will you post both to Austria via Pošta Slovenije (€17.80)? Ask for a current SMART readout and the Toshiba warranty-check result for both serials.
- **Waldkraiburg 12900K PC:**
  - Is the BIOS current?
  - Any WHEA errors?
  - Book a pickup slot with an on-site test (memtest plus a short stress test).
- **Amstetten S2600CW:**
  - Exactly which drives are included (P3600?)?
  - How many PSU modules?
  - Will you ship by Post up to 31.5 kg?
- **Heinfels 2× E5-2690 v4:** pickup slot. The seller tests them in front of you.

---

## 10. Method, coverage and limitations

**Coverage.**
- **Sources checked:**
  - Marketplaces: kleinanzeigen.de, willhaben.at, bolha.com (SI), hardverapro.hu, bazos.cz/sk, subito.it (Friuli), markt.de, quoka.de, avito.ma.
  - Moroccan shops: ultrapc.ma, setupgame.ma, techspace.ma, myordi.ma.
  - Refurbishers: servershop24, it-market, afbshop, esm, harlander, itsco, lapstore, techbuyer, memorysolution, compuram, ram-koenig.
  - Retail: geizhals.at (intermittent), billiger.de, alternate.at/.de, cyberport.at, MediaMarkt.at.
- **Volume:**
  - About 1,000 listings were screened. Every one of the 378 rows in `deals.csv` was opened.
  - Shortlisted listings were re-opened by an independent "skeptic" pass that read the SMART screenshots, CPU-Z and BIOS photos. That pass caught the failing drives, wrong CPU SKUs, a non-ECC "server" RAM kit and doctored screenshots.

**Blocked from the research machine.** I could not use these, so prices from them are not included:
- **eBay (all domains).** This rules out eBay sold listings.
- **Others:** idealo, leboncoin, galaxus, e-tec, mylemon, proshop, computeruniverse, jumia.ma, mytek.ma, pcgamer.ma.
- **hardwareluxx marketplace:** login required.
- **Mindfactory:** captcha.

**Resale values.**
- They are **asking-price medians** from kleinanzeigen + willhaben ads posted 9 Sep – 10 Oct 2026, minus 15%. They are not sold prices, because eBay's sold filter was unreachable. The US cross-check for the RTX 3060 is consistent.
- Thin comparables are flagged in the CSV (870 QVO n=3, Titan X n=5).
- Resale assumes you sell inside Austria via willhaben (the buyer pays PayLivery).

**Shipping rules.** Kleinanzeigen "Versand möglich" and "Direkt kaufen" are **Germany-only**. Every German item needs the seller to agree to ship to Austria, at the DHL prices above, or a pickup. This is flagged per row in `ships_to_at`.

**Payment risk.** Several sellers accept only PayPal Friends & Family or bank transfer, which gives no buyer protection: the X10SRi-F, X11DPL-i RAM and Hochheim RAM sellers among others. This is flagged in `notes`.

**Idle-power figures** are estimates built from the measurements cited. They are not measured on these exact machines.

[^fdtd]: Ruiz-Cabello et al., *PLoS ONE* 15(9) e0238115 (2020): "the main factor limiting FDTD performance … is the memory bandwidth". STREAM figures: Dell/Utah CHPC (dual Skylake/Cascade Lake), OpenBenchmarking (dual-channel desktops).
[^oems]: [OpenBenchmarking pts/openems](https://openbenchmarking.org/test/pts/openems).
[^cst]: 3DS hardware recommendations; GoEngineer on CST licensing (2023): the base licence gives full solver access to two CPU sockets.
[^hfss]: Ansys blog, W. Slagter (2020): 8 GB RAM per core, fill all channels; four cores without HPC licences.
[^feko]: Altair help, unit draw for FekoSolver; Altair community: "max out RAM first, then cores".
