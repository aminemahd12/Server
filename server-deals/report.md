# Home server deal research — Villach → Morocco

*Listings were checked on 9–10 Oct 2026 in two independent passes. The parts in the recommended builds were re-opened a third time on 10 Oct. Prices are as listed and shipping is to Villach. "Net" = price + shipping − realistic resale of the parts you don't need.*

**Every listing is in [`deals.csv`](deals.csv)**: 381 rows, each opened, all ≤ 30 days old and none reserved or sold. Rows used in a build are at the top (`used_in_build`).

**What I optimised for:**
- CPU/RAM performance for the solvers and Windows VMs.
- A reliable, large NAS.
- Upgradability.
- Low 24/7 power draw and ease of use. You said this matters, so single-CPU builds are preferred and dual-CPU machines only appear where they are unusually cheap (§4).

---

## 1. Recommendation in one table

| | **Build 1 — i9-12900K desktop** (recommended) | **Build 2 — HP Z440 workstation** | **Build 3 — Supermicro X10SRi-F server board** |
|---|---|---|---|
| What it is | Gaming PC bought whole; you keep CPU, board, RAM, PSU, cooler and SSD, move them into **your case**, and resell the GPU, QLC SSD, case and WiFi card | A ready-made HP workstation with an E5-2690 v4, plus 32 GB more RAM; resell its GTX 1660 Super and WiFi card | Server board + CPU + RAM from one seller, with a new cooler, a used PSU and an SSD, built into **your case** |
| CPU | i9-12900K, 16 cores / 24 threads (8 P + 8 E) | Xeon E5-2690 v4, 14 / 28 | Xeon E5-2697 v4, 18 / 36 |
| RAM | 64 GB DDR4-3200 (2×32), non-ECC, 4 slots (max 128 GB) | 64 GB DDR4 **ECC** RDIMM, 8 slots (max 256 GB) | 32 GB DDR4-2400 **ECC** RDIMM (4×8), 8 slots (max 512 GB) |
| NAS | 2× Toshiba MG08 16 TB, ZFS mirror (16 TB usable) | same | same |
| VM / boot SSD | Samsung 980 500 GB NVMe | 240 + 256 GB SATA SSDs (included) | Intel D3-S4510 480 GB (enterprise, power-loss protection) |
| PassMark multi / single | **41,099 / 4,128** | 19,166 / 2,067 | 21,371 / 2,038 |
| Memory bandwidth (theoretical) | 51 GB/s (2 channels) | 68 GB/s (4 ch, DDR4-2133 modules) | 77 GB/s (4 ch) |
| **Idle power** (whole box, 2 HDDs; estimate) | **~30–42 W** | ~55–65 W | ~45–60 W |
| **Electricity per year in Morocco** | **€28–53** | €51–82 | €41–75 |
| Upfront cash | €1,237.80 | €846.39 | €790.49 |
| Resale of unused parts | −€480 | −€102 | — |
| **Net cost** | **€757.80** | **€744.39** | **€790.49** |
| **4-year cost** (net + electricity) | **€868–969** | €948–1,072 | €956–1,092 |
| Remote management | None built in (add a €135 KVM later) | None (no BMC; Intel AMT can't do KVM without an iGPU) | **Full IPMI web console** (remote BIOS, power, ISO mount) |
| Ease of use | Normal desktop, iGPU, quiet; Proxmox runs fine | Finished, quiet, 11–13.5 kg machine; nothing to assemble | Needs assembly; server BIOS; fans need setting up |

**My pick: Build 1.**
- It is the fastest of the three, about 2× the Xeons' throughput and 2× their single-core speed.
- It uses the least power (cheapest over 4 years) and fits your own case.
- The trade-offs: no ECC, no remote console until you add a KVM, a 128 GB RAM ceiling, and you must sell four parts to reach the net price.

**When to choose Build 2 or 3 instead:**
- **Build 2** if you want ECC and a no-assembly, no-reselling-hassle machine (only a GPU and WiFi card to sell). It is also the cheapest. It costs about €25–30 a year more in power and is about half as fast.
- **Build 3** if being able to fix the box from Singapore (BIOS, reinstall, power-cycle) matters more than speed. It is the only build with remote management included.

> Nothing has been bought and no seller has been contacted. §9 lists what to ask each seller. The buy-now list is in §6.

**Should you consider a dual-CPU box?** The cheapest found is a Lenovo P720 with 2× Xeon Gold upgraded to 2× Gold 6140: 36 cores, AVX-512, 12 memory channels for **€734.69 net** (§4).
- That is absurdly cheap for the hardware.
- But it idles at ~65–90 W, costs €30–60 a year more power than Build 1, weighs about 25 kg, has no remote console, and needs NUMA pinning to use it well.
- Only worth it if you run CST Studio or very large FDTD meshes every day.

---

## 2. What the October 2026 market looks like (and why the builds look like this)

- **DRAM and NAND shortage.**
  - New 2×32 GB DDR4 costs from €478; 2×32 GB DDR5 from €793; a new 870 QVO 2 TB €550; new NAS HDDs €36–52 per TB.
  - Any build that buys 64 GB of new RAM, or new disks, is out of budget.
  - So the RAM has to come inside a used machine (Builds 1 and 2) or as cheap used server RDIMMs (Build 3, at about €2.5–3.9/GB).
- **Prebuilt harvesting works.** GPUs and SSDs hold their value: an RTX 3060 12 GB asks €285 used, and a 2 TB QLC SSD about €200. A €900 gaming PC therefore costs about €420 net for the parts you keep.
- **Storage.**
  - The three cheapest large used drives found (€80–95 for 12–16 TB) were all failing according to the sellers' own SMART screenshots. Another set had doctored screenshots.
  - The Toshiba MG08 16 TB pair in Slovenia is the cheapest sound option: 9.6k and 8.9k hours, 0 bad sectors, €160 each. All three builds use it.
- **Power.**
  - Morocco's household tariff is 1.07–1.60 MAD/kWh (≈ €0.10–0.14).
  - Every 10 W of 24/7 idle costs €9–13 a year.
  - Modern desktop platforms idle at 15–30 W without a graphics card; Xeon E5 v4 workstations at 50–60 W; dual-socket servers at 80–140 W.
- **Within €800 but rejected:**
  - Ryzen 9 5950X + 64 GB ECC (AM4) costs €982; it's the best all-round desktop if you can stretch (§4).
  - AM5/DDR5 is out of reach at current RAM prices.
  - Dual-socket options are in §4.

**Solver fit** (single-CPU view):

| Solver type | What it needs | Best here |
|---|---|---|
| openEMS (single process), HFSS / FEKO on a base licence (4 cores), Sonnet | Per-core speed and RAM capacity; openEMS scales poorly across many cores (PTS openEMS: i9-13900K 70 MCells/s vs 11–21 on 32–64-core Threadripper/EPYC)[^oems] | **Build 1** |
| CST Studio | Uses P-cores only; the base licence covers 2 full sockets; wants all memory channels filled[^cst] | Build 1 (8 fast P-cores), or the dual P720 in §4 for big jobs |
| Large FDTD meshes (MEEP, openEMS MPI), Elmer / Palace (MPI) | Memory bandwidth first[^fdtd] | Builds 2/3 have 4 channels (68–77 GB/s) vs 2 channels on Build 1 (51 GB/s). That is a ~35–50% edge, but Build 1 has 2× the compute. |
| Large FEM direct solves (HFSS, Palace, FEKO MoM) | RAM capacity: 8 GB per core recommended[^hfss] | Build 3 upgrades cheapest (8 slots, up to 512 GB); Build 1 is capped at 128 GB |

---

## 3. The three builds

### Build 1 — i9-12900K desktop in your own case (gaming-PC harvest) — **net €757.80**

| Part | Source listing | Price | Shipping | Notes |
|---|---|---|---|---|
| Gaming PC: i9-12900K, ASUS Prime Z690M-PLUS D4 (mATX), 64 GB DDR4-3200 (2×32), Samsung 980 500 GB NVMe, Samsung 870 QVO 2 TB, RTX 3060 12 GB, Thermaltake TH240 V2 AIO, be quiet! System Power 9 600 W, WLAN card, ATX case | [kleinanzeigen 3522007884](https://www.kleinanzeigen.de/s-anzeige/gaming-pc-i9-12900k-rtx-3060-12gb-64gb-ddr4-2-5tb-ssd/3522007884-228-6396), Waldkraiburg (Bavaria), private, posted 24.09, re-checked active 10.10 | €900 | €0 | **Pickup only**, ~3 h 15 min each way via Salzburg; the seller offers a test on site |
| Toshiba MG08ACA16TE 16 TB #1 (9,639 h, 0 realloc/pending) | [bolha 16514405](https://www.bolha.com/sata3-trdi-diski/prodam-trdi-disk-toshiba-16tb-mg08aca16te-zdrav-oglas-16514405), Cankova SI, private, posted 08.10 | €160 | €17.80 | One Pošta Slovenije 2–5 kg parcel for both drives. bolha's escrow only ships inside Slovenia, so agree the shipment or pick up (~3 h). |
| Toshiba MG08ACA16TE 16 TB #2 (8,938 h, 0 realloc) | [bolha 16514386](https://www.bolha.com/sata3-trdi-diski/trdi-disk-toshiba-16tb-mg08aca16te-zdrav-oglas-16514386), same seller | €160 | — | |
| **Upfront** | | **€1,220** | **€17.80** | **€1,237.80** |
| Resell: RTX 3060 12 GB | asking median €285 (12 ads) × 0.85 | | | −€242 |
| Resell: Samsung 870 QVO 2 TB | asking median €200 (3 ads: €190/200/299) × 0.85; new price is €549.99 | | | −€170 |
| Resell: ATX case | asking median €60 (18 ads) × 0.85 | | | −€51 |
| Resell: PCIe WiFi card | asking median €20 (38 ads) × 0.85 | | | −€17 |
| **Net** | | | | **€757.80** |

**Why.**
- The best per-core speed in the budget (PassMark single 4,128, about 2× the Xeons) and the highest multi-core throughput (41,099).
- An iGPU, so it runs headless with no extra graphics card. Windows VMs can share the iGPU via SR-IOV using the out-of-tree i915-sriov-dkms driver.
- The lowest idle power.
- Bought separately, the parts you keep would cost about €860–1,010 at current asking prices (12900K €180–299, Z690 DDR4 board ~€160, 64 GB DDR4 €350–385, 500 GB NVMe ~€79, AIO ~€50, PSU ~€40). The harvest saves €440–590.

**Performance class.**
- High-end 2021–22 desktop: about Ryzen 9 5950X throughput with faster single cores.
- Limits: dual-channel DDR4 (51 GB/s theoretical, 24–29 GB/s measured STREAM on this class), no AVX-512 (fused off on Alder Lake), no ECC, 128 GB maximum.
- CST uses only the 8 P-cores.
- For MPI solvers and VMs, pin to the P-cores (`lscpu -e` shows which cores are which).

**Idle power: ~30–42 W** at the wall, about **€28–53 a year**.
- Basis: an i5-12500 on Z690 measured 13–18 W at the wall on two boards (Hardwareluxx). I estimate 20–30 W for a 12900K without a dGPU, plus 8 W for two MG08 drives (Toshiba datasheet: 4 W idle each) and a few watts for the AIO pump and fans.
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
- **You must sell four items** to reach €757.80. The QLC SSD comparable is thin, so the net could be €30–50 higher.
- **Pickup only** in Bavaria.

---

### Build 2 — HP Z440 workstation with 64 GB ECC — **net €744.39**

| Part | Source listing | Price | Shipping | Notes |
|---|---|---|---|---|
| HP Z440: Xeon E5-2690 v4 (14C), 32 GB DDR4, GTX 1660 Super, 240 GB + 256 GB SATA SSDs, Intel AX210 WiFi, Win11 Pro | [willhaben 1544762681](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/hp-z440-e5-2690v4-gtx-1660-super-1544762681/), Feldkirch, private, posted 04.10, re-checked active 10.10 | €350 | €9.90 | **Ships within Austria with willhaben buyer protection** (PayLivery Post ≤31.5 kg) |
| 2× 16 GB DDR4-2133 ECC RDIMM (Samsung M393A2G40DB0-CPB) | [willhaben 1344604666](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/ddr4-server-ram-16-gb-2133p-1344604666/), Hermagor (45 min from Villach), private, 16 modules available | €120 (€60 each; bulk price negotiable) | €2.99 | PayLivery letter, or pick up and test |
| ASUS GT 710 2 GB, passive | [willhaben 1784456640](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/asus-gt710-sl-2gd5-1784456640/), Anger (Styria), private | €20 | €5.70 | Xeon E5 has no iGPU. This passive card replaces the GTX 1660 Super to cut idle power. Skip it (−€25.70) if your Z440 boots headless. |
| 2× Toshiba MG08 16 TB | as in Build 1 | €320 | €17.80 | They go in the Z440's two internal 3.5″ bays |
| **Upfront** | | **€810** | **€36.39** | **€846.39** |
| Resell: GTX 1660 Super | asking median €100 (12 ads) × 0.85 | | | −€85 |
| Resell: Intel AX210 WiFi card | asking median €20 × 0.85 | | | −€17 |
| **Net** | | | | **€744.39** |

**Why.**
- The easiest box to own: a finished, quiet, 11–13.5 kg HP workstation that flies as a normal checked bag.
- ECC RDIMMs (the Z440 takes registered ECC memory only), 64 GB across all 4 channels, and one seller with buyer protection.
- The cheapest build here, with HP's own measured idle figures.

**Performance class.**
- 2016 single-socket workstation: about half of Build 1's throughput (PassMark 19,166 / 2,067), AVX2 only.
- 4-channel memory (68 GB/s with these DDR4-2133 modules) is about 1/3 more bandwidth than Build 1, which helps memory-bound FDTD.

**Idle power: ~55–65 W**, about **€51–82 a year**.
- Basis: HP's QuickSpecs measured 51.2–61.5 W Windows idle for Z440 configurations with Quadro cards and 1–4 HDDs.

**Upgrade path.**
- RAM: 8 slots. HP lists 128 GB maximum; Kingston lists 256 GB with 32 GB RDIMMs. More than 4 DIMMs need HP's memory cooling kit.
- CPU: HP's list stops at 140 W, and the E5-2690 v4 (135 W) is already near the top. 145 W 18–22-core parts are unofficial; one user report says an E5-2697A v4 works after BIOS 02.59.
- NVMe through a PCIe adapter; boot support is mixed per HP forums.

**Risks.**
- **RAM layout unknown.** The ad doesn't say whether the 32 GB is 2×16 or 4×8. If it's 4×8, adding 2×16 means 6 DIMMs (needs the HP cooling kit) and unbalanced channels. Then buy 4×16 instead (4 modules from Hermagor = €240 + €2.99; net becomes €864.39).
- **PSU wattage unknown** (525 W or 700 W). Both are fine without a big GPU. The 525 W unit has only 2 SATA power leads, so you need a splitter for 4 drives.
- **Proprietary HP** board, PSU and chassis: your own case stays unused.
- **No remote console** (no BMC).
- **About half the speed** of Build 1, for more power.
- **Cheaper Z440 base:** a [Z440 with 64 GB](https://www.bolha.com/hp-compaq-namizni-racunalniki/hp-z440-xenon-64gb-ssd-500gb-windows-11-pro-oglas-15420999) is €250 in Postojna (SI, 1 h 40 min), plus a 2690 v4. But the ad uses a stock photo, is an old renewed listing, and gives no specs, so ask for real photos first.

---

### Build 3 — Supermicro X10SRi-F + E5-2697 v4 in your own case (IPMI) — **€790.49**

| Part | Source listing | Price | Shipping | Notes |
|---|---|---|---|---|
| Supermicro X10SRi-F (ATX, IPMI with HTML5 iKVM, 10× SATA, 8 RDIMM slots) + Xeon E5-2697 v4 (18C) | [kleinanzeigen 3517636108](https://www.kleinanzeigen.de/s-anzeige/server-mb-supermicro-x10sri-f-xeon-e5-2697v4-18-36c-ohne-ram/3517636108-225-29987), Düsseldorf, private, posted 20.09, re-checked active 10.10 | €140 VB | €17.49 | One DHL 5 kg DE→AT parcel together with the RAM, if the seller agrees |
| 4× 8 GB DDR4-2400 ECC RDIMM (Kingston KSM24RS8/8MEI) | [kleinanzeigen 3528701995](https://www.kleinanzeigen.de/s-anzeige/32gb-4x8gb-ddr4-2400-ecc-registered-kingston-ksm24rs8-8mei/3528701995-225-29987), same seller | €99 VB | — | Fills all 4 channels |
| Dynatron R-27 cooler, **narrow ILM** (new) | [alternate.at](https://www.alternate.at/Dynatron/Xeon-CPU-K%C3%BChler-R-27/html/product/1180332), in stock | €50.90 | €8.90 | The X10SRi-F uses Supermicro's **narrow** ILM, so normal desktop coolers won't fit. |
| Corsair RM550x 550 W 80 Plus Gold (2018), with box and all cables | [willhaben 1384681058](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/corsair-rm550x-550w-1384681058/), Premstätten (Styria), private | €60 | €5.70 | PayLivery. One EPS cable, which is all a single-socket board needs. |
| Intel D3-S4510 480 GB SATA SSD (20,659 h, 3.1 TB written, health 100%) | [willhaben 1486697881](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/intel-ssd-d3-s4510-series-480gb-1486697881/), Ertl (Lower Austria), private | €65 | €5.70 | No PayLivery option, so ask for an Austrian Post parcel or pick up. |
| 2× Toshiba MG08 16 TB | as in Build 1 | €320 | €17.80 | |
| **Total (nothing to resell)** | | **€734.90** | **€55.59** | **€790.49** |

**Why.**
- The only build in budget with **real out-of-band management**: IPMI/iKVM gives you BIOS, console, power and virtual-ISO access from Singapore. That is a big ease-of-use win for an unattended box.
- ECC, standard ATX parts in **your case**, and an enterprise SSD with power-loss protection for the VMs.
- The most RAM headroom: 8 slots, up to 512 GB+ RDIMM.

**Performance class.**
- 2016 single-socket server: PassMark 21,371 / 2,038, about half of Build 1. AVX2 only.
- 4-channel DDR4-2400 gives 77 GB/s theoretical.
- 32 GB is tight for Windows VMs plus big FEM jobs, so treat RAM as the first upgrade.

**Idle power: ~45–60 W**, about **€41–75 a year**.
- Basis: a lean X10SRM-F (same platform) with an E5-2620 v4 measured 30 W (Proxmox forum). I estimate 40–60 W for a bare X10SRi-F + E5 v4 + RDIMMs + SSD, plus 8 W for two HDDs.

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

---

## 4. Other options considered

All include the same 2× MG08 16 TB mirror (€337.80) unless noted. Idle figures are estimates with 2 HDDs.

| Option | Parts | Net | Idle | Verdict |
|---|---|---|---|---|
| **Dual CPU, cheapest: Lenovo P720 with 2× Gold 6140** | [P720, 2× Gold 5118, 64 GB, RTX 3060, €600 VB + DHL €45.49](https://www.kleinanzeigen.de/s-anzeige/lenovo-thinkstation-p720-workstation-rtx-3060-64-gb-ram-/3531669065-228-3721) + 2× Gold 6140 from Linz ([#1](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/intel-xeon-gold-6140-18-kerne-36-threads-lga-3647-server-workstation-1-1309917360/), [#2](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/intel-xeon-gold-6140-18-kerne-36-threads-lga-3647-server-workstation-2-841391018/), €25 + €5.70 each); resell RTX 3060 (€242) + 2 TB HDD (€68) | **€734.69** (upfront €1,044.69) | 65–90 W (€60–113/yr) | 36 cores, AVX-512, 12 channels: as much throughput as Build 1 with 4–6× the bandwidth. But heavy (up to 25.7 kg), proprietary, no KVM, NUMA. You can run it on **one** Gold 6140 (~48–65 W, net €703.99) and keep the second socket for later. Only worth it for daily CST or huge FDTD jobs. |
| Ryzen 9 5950X + 64 GB ECC (AM4), in your case | [5950X €200](https://www.kleinanzeigen.de/s-anzeige/amd-ryzen-9-5950x-16-kerne-32-threads-am4/3528545945-225-136) + [ASUS Prime B550-Plus €95 VB, same seller](https://www.kleinanzeigen.de/s-anzeige/asus-prime-b550-plus-mainboard-am4-b550/3527733785-225-136) + DHL €17.49 + [4×16 GB ECC UDIMM €190 + €14.49](https://www.kleinanzeigen.de/s-anzeige/4x-kingston-kvr24e17d8-16-ddr4-2400-cl17-sdram-ecc-64-gb-/3526472062-225-4445) + Arctic Freezer 36 €36.19 + [RM550x €65.70](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/corsair-rm550x-550w-1384681058/) + [GT 710 €25.70](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/asus-gt710-sl-2gd5-1784456640/) | €982.37 | 35–50 W | **The best single-CPU box if you can stretch €182**: ECC, 45,247 / 3,477 PassMark, low idle. Measured 42 W at the wall on a B550 board, though that was with an RTX 3080 fitted (ComputerBase); it should be lower with a GT 710. |
| [i7-13700K PC with RX 7800 XT, Klagenfurt](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/13700k-amd7800xt-mis-b760-gaming-plus-wifi-ram-nicht-enthalten-1877323555/), 35 min from Villach | €750 (or PayLivery €7.90); resell RX 7800 XT (€444); **no RAM included** | ~€306 + RAM + mirror | ~30–40 W | **Ask the seller whether the board is the "B760 Gaming Plus WiFi DDR4".** That model name exists in [DDR4 and DDR5 versions](https://www.scan.co.uk/products/msi-b760-gaming-plus-wifi-intel-b760-s-1700-ddr4-sata3-pcie-40-2x-m2-25gbe-usb-32-gen2-atx). If DDR4: add 64 GB DDR4 (e.g. a 4×16 GB set in Arlsdorf, Carinthia, €190 + €2.99, which the verifier identified as non-ECC desktop RAM) for **≈ €836.79** total, with a 13700K (45,590 / 4,325 PassMark). If DDR5: 64 GB costs €550+, out of budget. PSU brand and cooler are not stated. |
| Supermicro X11DPL-i + 2× Gold 6140 (dual, standard parts, IPMI) | [Kit €299](https://www.kleinanzeigen.de/s-anzeige/supermicro-x11dpl-i-mainboard-mit-2x-intel-xeon-gold-6140/3532639406-225-8105) + [8×8 GB €180, same seller](https://www.kleinanzeigen.de/s-anzeige/8x-8gb-64gb-ddr4-2400-ecc-registered-ram-ksm24rs8-8mei-/3531925755-225-8105) + DHL €17.49 + 2× [Dynatron B-14](https://www.alternate.at/Dynatron/B-14-Square-CPU-K%C3%BChler/html/product/1551241) €110.70 + [RM850x €35.70](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/corsair-rm-850x-netzteil-vollmodular-1704334934/) | €980.69 | 80–100 W | Over budget and power-hungry. Square-ILM board: Arctic Freezer 4U-M doesn't fit LGA3647. |
| Intel S2600CW dual E5 server | [€460 + €14.80](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/video-workstation-nvidia-geforce-gtx-titan-x-16x-intel-r-xeon-r-cpu-e5-2640-v4-2-40gh-2073820500/), resell Titan X €170, + [2× E5-2690 v4 €120](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/2x-xeon-e5-2690v4-cpu-1531003216/) | €762.60 | 85–110 W (€78–138/yr) | 28 cores, 8 channels, BMC, hot-swap bays. Heavy, loud, highest power draw. |
| ASUS Z10PA-D8 dual E5-2683 v3 (standard parts) | [€490 VB + €28.49](https://www.kleinanzeigen.de/s-anzeige/dual-xeon-workstation-28-kerne-64gb-ram-asus-corsair-top/3530968161-228-2045), resell case + GT 630 (€68) | €788.29 | 80–100 W | Fits your case, but slow Haswell and power-hungry. |
| Dell R730XD (iDRAC8 Enterprise, 16× 3.5″) | [€320 + €14.80](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/dell-poweredge-r730xd-16x-lff-bays-2x-e5-2680-v4-2-40-ghz-16gb-ddr4-ram-1x3-5-2tb-sas-hdds-perc-h730-mini-2x750w-psu-1004962242/) + RAM | ~€840 | 100–150 W | 2U rack server, 28–32 kg, loud. Not for a home in Morocco. |
| Remote console add-on (any build) | [GL.iNet Comet €128.99 + €5.90](https://geizhals.at/gl-inet-comet-gl-rm1-a3636909.html) / [JetKVM €129](https://geizhals.at/buildjet-jetkvm-a3801988.html) | +€135–139 | +2–3 W | Strongly recommended for Builds 1 and 2 once the budget allows |

**Rejected after verification:**
- **Failing drives:** the €80–90 Dortmund 12 TB drives and the €95 Viernheim 16 TB, per their own SMART screenshots.
- **Doctored SMART:** the Donaueschingen Toshiba set.
- **Scam signals:** the €219 Hungarian 5950X (stock press photo, zero-history seller) and the Tönning 4×32 GB RDIMM for €180.
- **Too weak:** 4-core workstations (Dell 7820 with Silver 4112, HP Z4 G4 W-2123).
- **Over budget:** AM5/DDR5.

---

## 5. Best prebuilt-harvest and bundle deals

### Harvests

Net = price + shipping − realistic resale. Realistic resale = median asking price of comparable ads × 0.85.

| Prebuilt | Price + ship | Resell (realistic) | Net | What you keep | Same parts bought separately |
|---|---|---|---|---|---|
| [i9-12900K PC, Waldkraiburg](https://www.kleinanzeigen.de/s-anzeige/gaming-pc-i9-12900k-rtx-3060-12gb-64gb-ddr4-2-5tb-ssd/3522007884-228-6396) (**Build 1**) | €900 + €0 | RTX 3060 €242, 870 QVO €170, case €51, WiFi €17 = **€480** | **€420** | 12900K, Z690 DDR4 board, 64 GB, 500 GB NVMe, AIO, PSU (all standard) | ≈ €860–1,010 at asking prices; saves ~€440–590 |
| [HP Z440 E5-2690 v4, Feldkirch](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/hp-z440-e5-2690v4-gtx-1660-super-1544762681/) (**Build 2**) | €350 + €9.90 | GTX 1660S €85, WiFi €17 = **€102** | **€257.90** | Whole workstation (HP proprietary board/PSU), 14C, 32 GB ECC, 2 SSDs | No parts equivalent (proprietary). The nearest standard route (X10SRi-F kit + 32 GB + cooler + PSU) costs €382 before an SSD. |
| [i7-13700K + RX 7800 XT, Klagenfurt](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/13700k-amd7800xt-mis-b760-gaming-plus-wifi-ram-nicht-enthalten-1877323555/) | €750 + €0 | RX 7800 XT €444 (case unstated, not counted) = **€444** | **€306** | 13700K, MSI B760 (DDR4 or DDR5?), 500 GB M.2, 750 W PSU, no RAM | 13700K alone €195–330 used |
| [Lenovo P720 2× Gold 5118](https://www.kleinanzeigen.de/s-anzeige/lenovo-thinkstation-p720-workstation-rtx-3060-64-gb-ram-/3531669065-228-3721) | €600 + €45.49 | RTX 3060 €242, 2 TB HDD €68 = **€310** | **€335.49** | Dual LGA3647 workstation, 64 GB ECC (proprietary) | Standard dual route (X11DPL-i kit + RAM + coolers + PSU) costs €642.89 before storage |
| [Intel S2600CW, Amstetten](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/video-workstation-nvidia-geforce-gtx-titan-x-16x-intel-r-xeon-r-cpu-e5-2640-v4-2-40gh-2073820500/) | €460 + €14.80 | Titan X **€170** | **€304.80** | Dual E5 v4, 64 GB, BMC, chassis | |
| [HP Z840 128 GB](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/powerstation-z840-1401254193/) | €550 + €14.80 | 2× P4000 €246, 2 TB HDD €68 = **€314** | **€250.80** | 2× weak E5-2630 v3, 128 GB RDIMM | Mainly a RAM harvest (128 GB RDIMM ≈ €320–450 privately) |
| [Ryzen 3900X + RTX 3080 Ti, Fischamend](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/gaming-pc-rtx-3080ti-ryzen-9-3900x-32gb-ram-750w-silent-build-1857205100/) | €849 + €0 | 3080 Ti €461, Silent Base 801 €84 = **€545** | **€304** | 3900X, B550, 32 GB, RM750, 360 AIO | Only 32 GB, no SSD, no iGPU |

Every prebuilt in `deals.csv` has its keep/resell breakdown in the `keep_resell_breakdown` column.

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

## 6. Buy-now list (likely to sell fast)

| # | Listing | Why it will go |
|---|---|---|
| 1 | [Toshiba MG08 16 TB ×2](https://www.bolha.com/sata3-trdi-diski/prodam-trdi-disk-toshiba-16tb-mg08aca16te-zdrav-oglas-16514405), €160 each (SI) | The only sound used 16 TB drives at ~€10/TB found anywhere; every build uses them. |
| 2 | [i9-12900K PC, Waldkraiburg](https://www.kleinanzeigen.de/s-anzeige/gaming-pc-i9-12900k-rtx-3060-12gb-64gb-ddr4-2-5tb-ssd/3522007884-228-6396), €900 | 64 GB as 2×32 at this price is rare in 2026. |
| 3 | [HP Z440 E5-2690 v4, Feldkirch](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/hp-z440-e5-2690v4-gtx-1660-super-1544762681/), €350 | Verifier rated it high sell-fast. Cheap Austrian shipping. |
| 4 | [X10SRi-F + E5-2697 v4](https://www.kleinanzeigen.de/s-anzeige/server-mb-supermicro-x10sri-f-xeon-e5-2697v4-18-36c-ohne-ram/3517636108-225-29987), €140 VB | Price already cut from €199. Few IPMI boards are listed. |
| 5 | [Samsung PM883 960 GB, Vienna](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/samsung-pm883-ssd-2-5-960gb-sata-6-0gbps-1327243837/), €129 + €2.99 | Posted 09.10. Optional VM-SSD upgrade for any build. |
| 6 | [Ryzen 9 5950X, Stralsund](https://www.kleinanzeigen.de/s-anzeige/amd-ryzen-9-5950x-16-kerne-32-threads-am4/3528545945-225-136), €200 | €50–100 under market. Only relevant if you stretch for AM4. |
| 7 | [Lenovo P720 2× Gold 5118](https://www.kleinanzeigen.de/s-anzeige/lenovo-thinkstation-p720-workstation-rtx-3060-64-gb-ram-/3531669065-228-3721), €600 VB | Only if you want the dual-CPU option. |

**Ageing out:** the [Berlin HC550 18 TB](https://www.kleinanzeigen.de/s-anzeige/western-digital-ultrastar-dc-hc550-18tb-gebraucht-voll-funktio/3509342612-225-3368) (a fallback HDD) passes 30 days on 11.10.

**Fallback HDD:** if the MG08 pair goes, the nearest option is the [IronWolf Pro 16 TB in Villach-Auen](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/seagate-ironwolf-pro-16-tb-nas-hdd-long-generic-smart-geprueft-923408488/): €299 each, 8.2k h, several units, test on site.

---

## 7. Market reference prices found (Oct 2026)

"Used" means private asking prices on kleinanzeigen/willhaben/bolha unless stated. New prices are from geizhals.at, billiger.de or the named shop.

| Item | Price found | Source / basis |
|---|---|---|
| Ryzen 9 5950X | used €200–320 (typ. €250–300) · new €315.05 (billiger.de) / €319.68 (geizhals.at) / €326.56 (cyberport.at) | [KA](https://www.kleinanzeigen.de/s-pc-zubehoer-software/ryzen-9-5950x/k0c225), [billiger](https://www.billiger.de/search?searchstring=AMD+Ryzen+9+5950X&sort=price_asc), [geizhals](https://geizhals.at/amd-ryzen-9-5950x-100-100000059wof-a2392527.html). *Sources differ by up to €11.* |
| Ryzen 9 5900X / 3950X / 3900X | used €180–250 / €180–200 / €90–160 | KA, willhaben (≈50 ads) |
| i9-12900K / i7-13700K | used €180–299 / €195–330 | [KA](https://www.kleinanzeigen.de/s-pc-zubehoer-software/i7-13700k/k0c225) |
| Ryzen 9 9900X / 9950X | new €299.99 / €443.94 | [billiger.de](https://www.billiger.de/search?searchstring=AMD+Ryzen+9+9950X&sort=price_asc) |
| Xeon E5-2690 v4 / E5-2696 v4 / Gold 6140 / Gold 6230 | €55 (€120 pair) / €85 / €25 / €80 each (€160 pair) private · refurb Gold 6230 €89.99, EPYC 7302 €199.99 | willhaben, bolha, [servershop24](https://www.servershop24.de/komponenten/cpus-prozessoren/amd/socket-sp3/) |
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
| Enterprise SATA SSD 480–960 GB with power-loss protection | used €65–149 · new PM893 960 GB €882.93 | KA/willhaben, geizhals |
| ATX PSU 550–650 W Gold | used €30–70 · new Corsair RM650e €79.99 + €6.39 | [geizhals](https://geizhals.at/?cat=gehps&fs=corsair+rm+e&sort=p) |
| Coolers for Xeons | Dynatron R-27 (narrow ILM) €50.90; Dynatron B-14 (LGA3647 square ILM) €50.90; + €8.90 shipping | [alternate.at](https://www.alternate.at/Dynatron/Xeon-CPU-K%C3%BChler-R-27/html/product/1180332) |
| GPU resale (asks): RTX 3060 12 GB / RX 7800 XT / 2080 Super / GTX 1660 Super / Titan X | €285 / €522 / €235 / €100 / €200 (medians, n=5–33) | KA + willhaben. US cross-check for the RTX 3060: $290 average ([resaleprices.com](https://resaleprices.com/gpu/nvidia-rtx-3060), Jul 2026); $278–300 sold ([jawa.gg](https://www.jawa.gg/product/116009/asus-phoenix-geforce-rtx-3060-12gb)). |
| Remote KVM | GL.iNet Comet €128.99 + €5.90; JetKVM €129; PiKVM V4 Mini €309 | [geizhals](https://geizhals.at/gl-inet-comet-gl-rm1-a3636909.html) |
| Shipping DE→AT (DHL, online) | 2 kg €14.49 · 5 kg €17.49 · 10 kg €22.49 · 20 kg €28.49 · 31.5 kg €45.49 | [dhl.de](https://www.dhl.de/de/privatkunden/pakete-versenden/weltweit-versenden/land/oesterreich.html) |
| Shipping SI→AT (Pošta Slovenije Connect) / within AT (willhaben PayLivery) | ≤2 kg €15.50 · 2–5 kg €17.80 / €2.99–14.80 | [posta.si price list](https://www.posta.si/zasebno-site/Documents/Ceniki/Novi-ceniki/Cenik%20Connect%20paket%20-%20velja%20od%201.1.2026.pdf), listings |
| Morocco (on arrival) | Micron 5300 PRO 3.84 TB enterprise SSD 3,190 DH (€286.82); PSUs at EU-new prices; CPUs/RAM 0–32% dearer than the EU | [avito](https://www.avito.ma/fr/abattoirs/autres_mat%C3%A9riels_electroniques/Micron_5300_PRO_3_84TB_SSD_Neuf_57252724.htm), [ultrapc.ma](https://www.ultrapc.ma/) |

FX on 9–10 Oct 2026: 1 EUR = 11.1221 MAD (open.er-api.com), 365.08 HUF and 24.369 CZK (ECB).

---

## 8. Running it in Morocco

- **Electricity.**
  - Household tariff: 1.0732–1.5958 MAD/kWh depending on tranche (≈ €0.10–0.14). Above 150 kWh/month, several sources say *all* kWh are billed at the tranche reached. A 24/7 server can push a household into a dearer tranche.
  - Each 10 W of idle is ≈ 88 kWh ≈ €9–13 a year. Build 1 idles 15–30 W below Builds 2 and 3.
  - To save more:
    - Set the BIOS to a power-saving profile and enable C-states and ASPM.
    - On Build 1, run `powertop --auto-tune` and remove the dGPU.
    - Let the HDDs spin down only if the NAS is idle for long periods; constant spin-up/down wears drives.
- **Flying it** (Royal Air Maroc, Europe zone): an extra 23 kg piece costs €100; a 23–32 kg piece €77 overweight; 158–203 cm €70 oversize ([RAM](https://www.royalairmaroc.com/int-en/excess-baggage)). Austrian Airlines refuses bags over 32 kg ([Austrian](https://www.austrian.com/at/en/excess-baggage)).
  - Builds 1 and 3 weigh your case plus parts.
  - Build 2 (HP Z440, 431.8 × 168.9 × 444.7 mm, 11–13.5 kg) fits normal checked baggage when boxed.
  - Carry the HDDs separately in anti-static bags and foam, ideally in the cabin.
  - Remove the AIO radiator or tower cooler before checking it in.
- **Customs.** The ADII Marhaba circular gives Moroccans resident abroad (MRE) a duty-free allowance of 25,000 DH once a year for non-commercial personal effects ([circular 6465/311](https://www.bladi.net/img/pdf/circulaire-marhaba-2023-mre.pdf)). I found no clear rule for non-MRE travellers or for desktop computers specifically. Check with ADII before flying, and keep invoices or screenshots of purchase prices.
- **Remote access from Singapore.**
  - Use a VPN (WireGuard or Tailscale) into Proxmox. Never expose IPMI to the internet.
  - Set the BIOS to "power on after AC loss".
  - Build 3 has IPMI/iKVM built in. For Builds 1 and 2, a €135 KVM (§4) plus a smart plug covers BIOS-level recovery.

---

## 9. Questions to ask each seller before buying (nobody has been contacted)

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
  - About 1,000 listings were screened. Every one of the 381 rows in `deals.csv` was opened.
  - Shortlisted listings were re-opened by an independent "skeptic" pass that read the SMART screenshots and the CPU-Z/BIOS photos. That pass caught the failing drives, wrong CPU SKUs, a non-ECC "server" RAM kit and doctored screenshots.

**Blocked from the research machine.** I could not use these, so prices from them are not included:
- **eBay (all domains).** This rules out eBay sold listings.
- **Others:** idealo, leboncoin, galaxus, e-tec, mylemon, proshop, computeruniverse, jumia.ma, mytek.ma, pcgamer.ma, msi.com.
- **hardwareluxx marketplace:** login required.
- **Mindfactory:** captcha.

**Resale values.**
- They are asking-price medians from kleinanzeigen + willhaben ads posted 9 Sep – 10 Oct 2026, minus 15%. They are not sold prices, because eBay's sold filter was unreachable. The US cross-check for the RTX 3060 is consistent.
- Thin comparables are flagged in the CSV (870 QVO n=3, Titan X n=5).
- Resale assumes you sell inside Austria via willhaben (the buyer pays PayLivery).

**Shipping rules.** Kleinanzeigen "Versand möglich" and "Direkt kaufen" are **Germany-only**. Every German item needs the seller to agree to ship to Austria, at the DHL prices above, or a pickup. This is flagged per row in `ships_to_at`.

**Payment risk.** Several sellers accept only PayPal Friends & Family or bank transfer, which gives no buyer protection: the X10SRi-F, X11DPL-i RAM and Hochheim RAM sellers among others. This is flagged in `notes`.

**Idle power** figures are estimates from the measurements cited (HP QuickSpecs, ComputerBase, Hardwareluxx, Proxmox/Reddit user reports, Toshiba and Intel datasheets). They are not measured on these exact machines.

**Few options in some areas.**
- Single-socket boards newer than Broadwell (X11SPi, H11/H12SSL, W680, C422) were essentially absent from the used market in the last 30 days.
- Sound large HDDs under €200 were scarce: only the MG08 pair and the HC550.

[^fdtd]: Ruiz-Cabello et al., *PLoS ONE* 15(9) e0238115 (2020): "the main factor limiting FDTD performance … is the memory bandwidth".
[^oems]: [OpenBenchmarking pts/openems](https://openbenchmarking.org/test/pts/openems).
[^cst]: 3DS hardware recommendations; GoEngineer on CST licensing (2023): the base licence gives full solver access to two CPU sockets.
[^hfss]: Ansys blog, W. Slagter (2020): 8 GB RAM per core, fill all channels; four cores without HPC licences.
