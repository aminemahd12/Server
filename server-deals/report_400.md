# Home server for €400: Villach → Morocco

*Researched 9–10 Oct 2026. Every listing below was re-opened on **10 Oct 2026** and was still active. A few shop prices come from the geizhals.at offer list because the shop's own page couldn't be opened from the research machine; each one is marked. Nothing has been bought and no seller has been contacted.*

**Rules this report follows:**
- **Only listings that ship to you.**
  - Austrian sellers with willhaben delivery (PayLivery) whose size/weight limit fits the item, or shops that deliver to Austria.
  - Anything whose ad says pickup only or offers no shipping is excluded. That covers 113 listings; see [`excluded_no_shipping.csv`](excluded_no_shipping.csv).
- **Upfront cash, delivered to Villach.** Nothing has to be resold to stay within budget.
- **Performance figures** are PassMark CPU Mark (multi-thread / single-thread) from cpubenchmark.net, matched by exact CPU id.
- **RAM:** 32 GB is accepted at this budget as a compromise, but only on a machine that can reach 64 GB. The cost of that upgrade is shown.
- **Prebuilt PCs and easy purchases first**, as you asked.

---

## 1. Recommendation

**Buy the complete PC from Pfunds (Tirol): €370 + €9.90 willhaben delivery = €379.90.**

It is the **only** complete PC under €400 that passes every rule. The sweep went through about 2,230 willhaben PC listings priced €150–560, ran more than 100 keyword searches on kleinanzeigen and willhaben, and checked six refurbishers. The next-cheapest machines that qualify are listed in §5; all of them cost more than €400.

| | **Pfunds PC** |
|---|---|
| Listing | [willhaben 828154053](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/gaming-office-pc-intel-i5-12400-32-gb-ram-gtx-1650-1-tb-ssd-windows-11-pro-828154053/): private seller, posted 9 Oct, re-checked 10 Oct |
| Price | €370 + willhaben Post delivery €9.90 (up to 31.5 kg, so a tower fits) = **€379.90** |
| CPU | Intel Core i5-12400, 6 cores / 12 threads, integrated graphics: **PassMark 18,824 / 3,466** ([source](https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core+i5-12400&id=4677)) |
| RAM | 32 GB DDR4 (4 × 8 GB). The board takes up to 128 GB. |
| Board | MSI PRO B760M-P DDR4: standard mATX, 4 DIMM slots, 2 × M.2 (both free), 4 × SATA |
| Storage | 1 TB SATA SSD (fanxiang, budget model) |
| PSU | be quiet! System Power 7 450 W: standard ATX, 80 PLUS Silver |
| Also included | GeForce GTX 1650 (not needed: the CPU has graphics), Cooler Master Q300L case, **Windows 11 Pro** (activated, screenshot in the ad) |
| Idle power (estimate) | ~22–35 W as delivered; **~15–25 W after you take the GTX 1650 out**, since it draws about 7–10 W at idle (keep it in a drawer, no need to sell it) |
| Electricity in Morocco | ~€14–31 a year with the GPU removed |
| Spare budget | €20.10 |

**Why this one.**
- **It needs nothing else.** It arrives working, with Windows 11 Pro, in one parcel, from an Austrian seller with willhaben buyer protection.
- **Everything inside is standard.** The board, PSU and case are retail parts, not proprietary Dell/HP/Lenovo hardware, so you can move them into your own case and upgrade any part later.
- **Strong single-core speed** (3,466, close to a Ryzen 9 5900X). Multi-core is only 18,824.
- **It can grow.** The board takes up to 128 GB and an i7-12700-class CPU (set PL1 to about 125 W). It is a budget board with a weak power stage (4 real CPU phases), so it isn't the place for an i7-13700K.

**What it is not.** At 18,824 multi-core it has about 41% of the throughput of the recommended €600 and €800 builds (A1/B1, i7-13700K, 45,590).
- It runs Proxmox, Windows VMs and the network drive well.
- CST runs (P-cores only: 6 here vs 8) will take roughly 1.5–2× longer.
- Memory-bound FDTD/FEM runs gain much less from a faster CPU, because both machines have the same dual-channel DDR4. The openEMS benchmark on OpenBenchmarking gives 40 MCells/s for an i5-12400 vs 70 for an i9-13900K.

€400 can't buy a 30,000+ CPU together with RAM, a board, a PSU and an SSD in today's market. The cheapest such parts sets are €570.18 (Ryzen 9 5900X) and €576.69 (sealed i5-13600K); the recommended i7-13700K set is €586.69 (see `report_600.md`).

---

## 2. The upgrade path (all from real, shippable listings checked 10 Oct)

| Step | What | Listing | Delivered | Result |
|---|---|---|---|---|
| 1 | Drive mirror: 2 × 2 TB CMR HDD | [WD Red Plus + WD Black, Wien 17](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/2tb-festplatten-1759125813/) (SMART screenshots: 0 bad sectors; 42,180 h and 16,752 h) | €105.70 if the seller accepts one €100 offer for both; €111.40 if bought as two orders | ZFS mirror for the network drive |
| 2 | 64 GB RAM | [4 × 16 GB DDR4-2666, Arlsdorf (Carinthia)](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/64-gb-ddr4-ram-2666mhz-1774557909/), memtest 0 errors; ships as a €2.99 letter (carrier liability €50; PayLivery refunds you if it never arrives) | €192.99 | 64 GB. This replaces the 4 × 8 GB, which you can keep as spares. |
| 3 | Faster CPU: i7-12700, 8P + 4E | [i7-12700 box with stock cooler, Graz](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/intel-core-1-7-12700-12-kern-cpu-1934965542/) | €229.70 | 29,755 / 3,840. 65 W base, up to 180 W turbo; the 450 W unit handles that with the GTX 1650 removed. Set PL1 to about 125 W because this board's power stage is weak. |

This PC plus steps 1, 2 and 3 comes to €908.29 in total. That's more than the €800 build in `report.md`, which gets an i7-13700K and 64 GB for €779.68.

An i7-13700K is **not** a sensible upgrade for this PC, because the board's power stage throttles it. For that class of CPU, build the €600 A1 parts set instead.

**If you can stretch to about €590 now, the €600 report gives far more for the money than buying this PC and upgrading it later.** Buy this PC only if €400 is a hard limit.

---

## 3. Risks and what to ask the seller (nobody has been contacted)

**Risks:**
- **The PSU is old.** The be quiet! System Power 7 450 W (80 PLUS Silver) is a design from about 2012–2016. It's fine for a 65 W i5 plus 2 drives, but it's the first part to replace for 24/7 use. A new be quiet! Pure Power 12 550 W is €64.90 + €8.90 at alternate.at.
- **The SSD is a budget model.** The fanxiang SATA SSD is probably DRAM-less: fine as a boot drive, slow for VM disks. The board has 2 free M.2 slots for a proper NVMe later, e.g. [Samsung PM9A1 512 GB, €57.99](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/m-2-mz-vl25120-samsung-512gb-pci-express-4-0x4-nvme-internal-solid-state-drive-832626534/).
- **One drive, so no redundancy yet.** Keep important files backed up until the mirror (step 1) is in.
- **Private sale, no warranty or returns.** willhaben PayLivery holds your payment until the parcel arrives.
- **It may sell fast.** It was posted on 9 Oct.

**Ask the seller:**
1. A photo of the BIOS screen (BIOS version) and of CPU-Z (Memory tab).
2. How old the PSU is.
3. Whether the Windows 11 Pro licence is a retail or OEM key.
4. That the PC is packed with the GPU removed or secured, and the cooler checked after transport.

---

## 4. Running it in Morocco (applies to every build)

- **Electricity.** Household tariffs run 0.90–1.60 MAD/kWh by tranche. These figures assume a household above 200 kWh/month: 1.1676–1.5958 MAD/kWh ≈ €0.105–0.143 per kWh at 1 EUR = 11.1221 MAD. **Every watt of 24/7 idle costs €0.92–1.26 a year.**
- **Remote access from Singapore.**
  - Use Tailscale or WireGuard into Proxmox. Never expose the web UI directly.
  - In the BIOS, set "Restore on AC power loss = Power On".
  - A Wi-Fi smart plug lets you hard power-cycle the box remotely. The [TP-Link Tapo P110](https://geizhals.at/tp-link-tapo-p110-a3694802.html) Type E version is €17.90 + €4.49 at alza.at (price from the geizhals offer list) and fits Moroccan Type E sockets. It doesn't fit this budget; it's the first add-on.
- **Flying it.**
  - Move the board, CPU, RAM and PSU into your own case, or carry the Q300L case as checked baggage.
  - Take the CPU cooler off, or pack it firmly, before the flight.
  - Carry drives in the cabin.
- **Heat and dust.** Keep the box in a ventilated room, not a closet. Set Proxmox drive-temperature alerts at 50 °C and clean the filters every few months.

---

## 5. Everything else considered (and why it lost)

| Option | Delivered | Why not |
|---|---|---|
| [TAROX Business PC, i5-14400, 32 GB (2 × 16), 500 GB NVMe, Gleisdorf](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/leistungsstarker-business-pc-i5-14400-32-gb-ram-500-gb-ssd-2030927090/) | €487.90 | Over €400. Faster (25,010 / 3,741); it's in the €600 report. |
| [Dell OptiPlex 3000 SFF, i5-12500, 16 GB, refurbished (refurbed.at)](https://www.refurbed.at/p/dell-optiplex-3000-sff/301509/) | €447.05 | Over €400. Only 16 GB, and the SFF case can't take 2 HDDs. It does come with a shop warranty. |
| [Lenovo IdeaCentre 5, Ryzen 7 5700G, 24 GB, Eferding](https://www.willhaben.at/iad/object?adId=1523651041) | €357.90 | Lenovo's spec sheet gives 2 slots and 32 GB max, so it can never reach 64 GB. Single-core 3,282 is below target. Proprietary board and PSU. |
| Building from parts | ≥ €570 | The cheapest strong parts sets are €570.18 (Ryzen 9 5900X + board + 32 GB + PSU + cooler + SSD + display card) and €576.69 (sealed i5-13600K). The recommended i7-13700K set is €586.69. |
| Used Xeon E5 v4 workstations (HP Z440, Dell T5810) | — (not priced) | Single-core ~2,050, barely half the target; you asked for strong single *and* multi. Most of the cheap ones are pickup-only. |
| Gaming PCs with big GPUs | — | They would need the GPU resold to fit the budget. You asked to minimise reselling. |

---

## 6. Method and limits

- **Sources:**
  - Marketplaces: willhaben.at and kleinanzeigen.de (tier 2 only).
  - Shops/refurbishers: DiTech.at and alternate.at (pages opened); alza.at (price from the geizhals.at offer list); refurbed.at, afbshop.de, itsco.de, lapstore.de, harlander.com, servershop24.de.
  - Not reachable from the research machine: eBay, leboncoin and Amazon product pages (Amazon prices come from geizhals.at offer lists).
- **Shipping check:** every ad's shipping field and text was read by script, in German, Slovenian, Hungarian, Czech/Slovak and Italian. Pickup-only, no-shipping and domestic-only ads were removed.
- **Verification:** each shortlisted listing was re-opened by a second, independent pass that looked at the photos and screenshots, then re-opened again on 10 Oct for this report.
- **Estimates:** idle power figures are estimates from comparable measurements (Hardwareluxx idle tests of 12th-gen Intel on Z690 DDR4 boards), not measured on this PC.
- All listings are in [`deals.csv`](deals.csv) (`used_in_build` = "€400").
