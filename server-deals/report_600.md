# Home server for €600: Villach → Morocco

*Researched 9–10 Oct 2026. Every listing below was re-opened on **10 Oct 2026** and was still active. A few shop prices come from the geizhals.at offer list because the shop's own page couldn't be opened from the research machine; each one is marked. Nothing has been bought and no seller has been contacted.*

**Rules this report follows:**
- **Only listings that ship to you.**
  - Austrian sellers with willhaben delivery (PayLivery) whose size/weight limit fits the item, or shops that deliver to Austria.
  - Anything whose ad says pickup only or offers no shipping is excluded. That covers 113 listings; see [`excluded_no_shipping.csv`](excluded_no_shipping.csv).
- **Upfront cash, delivered to Villach.** Nothing has to be resold to stay within budget.
- **Performance figures** are PassMark CPU Mark (multi-thread / single-thread) from cpubenchmark.net, matched by exact CPU id.
- **RAM:** 64 GB is the goal. At this budget 32 GB is accepted as a compromise, but only with 2 free slots and a priced path to 64 GB.
- **Storage:** you said a 512 GB–1 TB SSD plus a pair of 1–2 TB drives is enough. A1–A3 can't fit the drive pair within €600, so it's a later +€105.70. The only in-budget options that include a mirror are the TAROX PC + 2 × 2 TB (€593.60, §4) and the Pfunds PC + 2 × 2 TB (€485.60, 32 GB).

---

## 1. Recommendation in one table

| | **A1: i7-13700K parts build** (recommended) | **A2: i7-12700 + 64 GB parts build** | **A3: Pfunds prebuilt + 64 GB** (easiest) |
|---|---|---|---|
| Delivered total | **€586.69** | €599.99 | €572.89 |
| Spare budget | €13.31 | €0.01 (or €5.01 with the cheaper PSU in §3) | €27.11 |
| CPU | i7-13700K, 8 P + 8 E cores, 24 threads | i7-12700, 8 P + 4 E, 20 threads | i5-12400, 6 cores, 12 threads |
| **PassMark multi / single** | **45,590 / 4,325** | 29,755 / 3,840 | 18,824 / 3,466 |
| RAM | 32 GB (2 × 16 DDR4-2933), **2 slots free** | **64 GB** (4 × 16 DDR4-2133) | **64 GB** (4 × 16 DDR4-2666) |
| Cost to reach 64 GB | +€105.70 (one more 2 × 16 kit) | — | — |
| Storage | 512 GB NVMe (Samsung PM9A1) | 512 GB NVMe (Samsung PM9A1) | 1 TB SATA SSD (budget) |
| Drive mirror (2 × 2 TB) | Later, +€105.70 | Later, +€105.70 | Later, +€105.70 |
| Idle power (estimate) | ~17–27 W | ~17–27 W | ~15–25 W (with its GTX 1650 removed) |
| Electricity / year in Morocco | ~€16–34 | ~€16–34 | ~€14–31 |
| Parcels to receive | 6 | 5 | 2 |
| Windows licence | no | no | **Windows 11 Pro** included |

**My pick: A1.**
- It has 2.4× the multi-core and 25% more single-core speed than A3. Today it costs €13.80 more but has 32 GB instead of 64 GB; with the RAM matched (+€105.70), it's €119.50 more.
- Of everything checked, it's the fastest CPU that fits €600. The i9-13900K would come to €601.59.
- The RAM gap is cheap to close later: one more 2 × 16 GB kit for €105.70 gives 64 GB. A CPU can't be upgraded that cheaply.

**When to choose the others:**
- **A2** if 64 GB on day one matters more than CPU speed. Its RAM is DDR4-2133, with 20% less bandwidth than A3's 2666 kit, so memory-bound FDTD/FEM runs can take up to ~25% longer.
- **A3** if you want a working PC in two parcels, with Windows 11 Pro, and accept a much slower CPU.

> **What €600 can't buy:** a 30,000+ CPU together with 64 GB. The cheapest such set is €630.18: the €800 report's B3 (Ryzen 9 5900X + 64 GB ECC) without its drives. With the i7-13700K and the 2666 kit it's €673.98 (B1 without drives). Under €600, 64 GB comes only with the 29,755-point i7-12700 (A2) or the 18,824-point prebuilt (A3).

---

## 2. Build A1: i7-13700K + 32 GB (recommended), €586.69

| Part | Listing | Seller, where, posted | Price | Delivery | Shipping |
|---|---|---|---|---|---|
| CPU: Intel Core i7-13700K, used | [willhaben 1691159762](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/intel-i7-13700k-1691159762/) | private, Fritzens (Tirol), 05.10 | €250 | €5.70 | willhaben Post ≤ 3 kg |
| Board: Gigabyte B760M DS3H DDR4, **new** | [DiTech.at, Art.-Nr. 361952](https://www.ditech.at/s/de/b760m-ds3h-ddr4): in stock, delivery in 1–2 working days | Austrian shop (branch in Klagenfurt) | €95.90 | €0 | free delivery in AT from €49 |
| RAM: 32 GB (2 × 16 GB Samsung DDR4-2933 UDIMM, Lenovo pulls) | [willhaben 1602251551](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/32gb-2x16gb-samsung-pc4-2933y-pc-ram-workstation-1602251551/) | private, Völkermarkt (Carinthia), 08.10 | €100 | €5.70 | willhaben Post |
| PSU: Corsair RM650i 650 W Gold, fully modular, all cables | [willhaben 1261438596](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/corsair-rm650i-1261438596/) | private, Haag, 04.10 | €45 | €5.70 | willhaben Post |
| Cooler: Arctic Freezer 36 (heatsink never mounted) | [willhaben 1153939913](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/cpu-kuehler-arctic-freezer-36-fuer-amd-und-intel-ungenutzt-1153939913/) | private, Gänserndorf, 24.09 | €15 | €5.70 | willhaben Post |
| SSD: Samsung PM9A1 512 GB NVMe (TLC + DRAM, PCIe 4.0) | [willhaben 832626534](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/m-2-mz-vl25120-samsung-512gb-pci-express-4-0x4-nvme-internal-solid-state-drive-832626534/) | private, Wien, 04.10 | €55 | €2.99 | willhaben letter |
| **Total** | | | **€560.90** | **€25.79** | **€586.69** |

Everything goes into **your own case**. All parts are standard ATX, and the board is mATX, which fits an ATX case.

**Why this build.**
- **The best single- and multi-core speed reachable under €600.** The i9-13900K would be €601.59. The i7-13700K has 8 performance cores (CST uses only P-cores) plus 8 efficiency cores.
- **Integrated graphics**, so no display card is needed. Proxmox installs headless, and idle power stays low.
- **A new board with a 2-year shop warranty.** It has 4 DDR4 slots (up to 128 GB), 2 × M.2 PCIe 4.0, 4 × SATA and 2.5 GbE.
- **A strong PSU.** 650 W Gold with headroom, and Linux can read its power draw over USB.

**Upgrade path, priced from real listings:**

| When | What | Listing | Delivered | Gives |
|---|---|---|---|---|
| First | +32 GB: 2 × 16 GB SK hynix DDR4-2666 (same seller) | [willhaben 940319184](https://www.willhaben.at/iad/object?adId=940319184) (posted 27.09) | €105.70 | **64 GB** (both kits run at 2666) |
| Then | 2 × 2 TB CMR HDD mirror (WD Red Plus + WD Black) | [willhaben 1759125813](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/2tb-festplatten-1759125813/) | €105.70 (one €100 offer) | Network-drive mirror |
| Optional | TP-Link Tapo P110 smart plug, Type E (Moroccan sockets) | [geizhals → alza.at](https://geizhals.at/tp-link-tapo-p110-a3694802.html) | €22.39 | Remote power-cycle from Singapore |

With all three: €820.48, the same machine as the €800 report's Build 1 apart from the RAM.

**Risks.**
- **Raptor Lake ageing.** The 13th/14th-gen chips on Intel's list (i9, i7 and the i5-13600K/14600K) can degrade under old BIOS microcode.
  - Update the board BIOS to Intel microcode **0x12F or newer** before any heavy load, and keep Intel's default power limits. 0x12F is Intel's May 2025 fix for machines left on for days under light load, which is how a 24/7 server runs.
  - Ask the seller whether the CPU was ever unstable.
  - This used CPU comes without a box or invoice, so there is no Intel warranty.
  - **Alternative:** the factory-sealed [i5-13600K in Stams](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/intel-core-i5-13600k-lga1700-neu-ovp-versiegelt-1079149837/), €245.70, never used, with its invoice from 26.05.2023. The build becomes **€576.69** with 37,437 / 4,110.
    - It avoids a chip of unknown history.
    - It's on Intel's ageing list too and needs the same BIOS update before first use.
    - Intel doesn't honour warranty claims from second owners, so don't count on its 5-year term (to May 2028).
- **Cooling.** The Freezer 36 can't hold the 13700K's 253 W peak. Set PL1/PL2 to about 180 W in the BIOS. It costs a few percent of multi-core speed and is quieter.
- **The board's M.2 slots are NVMe-only.** That's fine for the PM9A1; never buy an M.2 SATA SSD for this board.
- **The SSD's health isn't stated.** Ask for a CrystalDiskInfo screenshot (percentage used, errors).
- **The PSU is about 8–11 years old** (first-generation RM650i). It's a premium unit, but ask the seller to confirm the 4+4-pin CPU (EPS) cable and 2+ SATA power leads are included.
- **The board price is DiTech.at's** (Austrian, opened 10 Oct). The geizhals offer list also shows Amazon.at at €88.64 and galaxus.at at €89.67. Those pages couldn't be opened from here; if their prices hold, they save about €6–7.

---

## 3. Build A2: i7-12700 + 64 GB, €599.99

| Part | Listing | Seller, where, posted | Delivered |
|---|---|---|---|
| CPU: Intel Core i7-12700 box **with Intel stock cooler**, used | [willhaben 1934965542](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/intel-core-1-7-12700-12-kern-cpu-1934965542/) | private, Graz, 02.10 | €224 + €5.70 = €229.70 |
| Board: Gigabyte B760M DS3H DDR4, new | as in A1 | DiTech.at | €95.90 |
| RAM: 64 GB (4 × 16 GB Samsung DDR4-2133 **ECC** UDIMM) | [willhaben 1153528073](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/64gb-2rx8-pc4-2133p-ee1-10-samsung-ram-1153528073/) | private, Allerheiligen bei Wildon (Styria), 06.10 | €160 + €5.70 = €165.70 |
| PSU: Corsair RM650i | as in A1 | | €50.70 |
| SSD: Samsung PM9A1 512 GB NVMe | as in A1 | | €57.99 |
| **Total** | | | **€599.99** |

**€599.99 leaves just €0.01.** To get some margin, take the [be quiet! Straight Power 11 Platinum 550 W, Stattersdorf](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/be-quiet-straight-power-11-platinum-1659391269/) (€40 + €5.70; the seller lists the 24-pin, one 8-pin CPU and SATA cables, but says it hasn't been tested) instead of the RM650i. The build becomes **€594.99**.

**Why:** it has 64 GB on day one and keeps the 8 performance cores (CST), with no Raptor Lake ageing risk (Alder Lake), integrated graphics and a cooler in the box.

**Risks:**
- **The CPU is slower:** 29,755 / 3,840, just under the 30,000 multi-core target. The stock cooler limits sustained all-core power, so add a Freezer 36 (€20.70) later. The adds in this list would take A2 over budget.
- **The RAM is ECC UDIMM at DDR4-2133.**
  - On this Intel B760 board it runs **without ECC**. These modules usually work on Intel desktop boards, but they're not on Gigabyte's tested list.
  - Bandwidth is 20% below DDR4-2666, so memory-bound runs can take up to ~25% longer.
  - The seller's account is 10 days old; the photos are clearly their own. Pay only through PayLivery.
  - If you want to avoid both points, the [Arlsdorf 4 × 16 GB DDR4-2666 desktop kit](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/64-gb-ddr4-ram-2666mhz-1774557909/) (€192.99) makes A2 €627.28, over budget.
- **Check the CPU model before paying.** The ad's photos don't show the chip's top. Ask for a photo of the heatspreader showing "i7-12700" (not 12700F, which has no graphics; S-spec SRL4Q).

---

## 4. Build A3: Pfunds prebuilt + 64 GB (easiest), €572.89

| Part | Listing | Seller, where, posted | Delivered |
|---|---|---|---|
| Complete PC: i5-12400, 32 GB (4 × 8), MSI PRO B760M-P DDR4, 1 TB SATA SSD, GTX 1650, be quiet! 450 W, Q300L case, Windows 11 Pro | [willhaben 828154053](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/gaming-office-pc-intel-i5-12400-32-gb-ram-gtx-1650-1-tb-ssd-windows-11-pro-828154053/) | private, Pfunds (Tirol), 09.10 | €370 + €9.90 (Post ≤ 31.5 kg) = €379.90 |
| RAM: 64 GB (4 × 16 GB SK hynix DDR4-2666 desktop), memtest 0 errors | [willhaben 1774557909](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/64-gb-ddr4-ram-2666mhz-1774557909/) | private, Arlsdorf (Carinthia), 04.10 | €190 + €2.99 = €192.99 |
| **Total** | | | **€572.89** |

**Why:** it arrives working, in two parcels, with 64 GB (the old 4 × 8 GB become spares) and Windows 11 Pro. The board is a budget B760 with a weaker power stage than A1's (4 vs 8 real CPU phases), so the sensible CPU upgrade is the i7-12700 (€229.70): it runs on the existing PSU with PL1 set to about 125 W. An i7-13700K would need a stronger board.

**Risks:** the CPU is the weakest here (18,824 / 3,466). The PSU is old: a be quiet! System Power 7 450 W, 80 PLUS Silver, a design from about 2012–2016. The SSD is a budget DRAM-less model. Take the GTX 1650 out to save about 7–10 W; keep it, there's no need to sell it. The 64 GB kit ships as a €2.99 letter (carrier liability €50), but PayLivery refunds you if it never arrives.

**Also considered, with a drive mirror:** [TAROX Business PC, i5-14400 (25,010 / 3,741), 32 GB (2 × 16), 500 GB NVMe, Gleisdorf](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/leistungsstarker-business-pc-i5-14400-32-gb-ram-500-gb-ssd-2030927090/), €487.90, plus the 2 × 2 TB pair €105.70 = **€593.60**. It lost to A3 for four reasons:
- **The board isn't named in the ad.** The TAROX datasheet says 4 slots, but this is unconfirmed.
- **The case has a single 3.5″ bay**, so the mirror needs your own case.
- **Its only willhaben delivery option is "up to 10 kg".** The tower should be under that, but ask.
- **It has 32 GB, not 64.**

---

## 5. Buying order (on your go-ahead)

1. **A1/A2: the CPU first** (A1: Fritzens 13700K, or the sealed Stams 13600K; A2: Graz 12700), because used CPUs sell fastest. Ask the questions in §6 before paying.
2. **A1/A2: the RAM**, for the same reason.
3. **A1/A2: the board, PSU, cooler and SSD.** These are a shop item and slower-moving private ads.
4. **A3: the Pfunds PC first, then the Arlsdorf 64 GB kit.**
5. Later: the second RAM kit (A1), the HDD pair and the Tapo plug.

Pay every private seller **through willhaben PayLivery**, which holds your money until delivery. Never pay by bank transfer outside it.

---

## 6. Questions for the sellers

- **i7-13700K (Fritzens):**
  - Which BIOS/microcode did it run, and since when?
  - Were there ever crashes or WHEA errors?
  - Is there an invoice?
  - Please send a second photo of the chip.
- **i5-13600K (Stams, if you choose that swap):** please send a photo of the invoice and confirm the seal is unbroken.
- **i7-12700 (Graz):** please send a photo of the heatspreader showing the model and S-spec SRL4Q (to rule out a 12700F).
- **RM650i (Haag):** are the 4+4-pin CPU (EPS) cable and at least 2 SATA power leads included? Roughly when was it bought?
- **PM9A1 (Wien):** please send a CrystalDiskInfo or smartctl screenshot (percentage used, power-on hours, media errors).
- **Freezer 36 (Gänserndorf):** are the Intel LGA1700 backplate and standoffs complete?
- **ECC RAM (Allerheiligen, A2 only):** have the modules been tested? Would you accept PayLivery only?
- **Pfunds PC (A3):**
  - A BIOS photo and a CPU-Z Memory-tab screenshot.
  - The PSU's age.
  - Is the Windows key retail or OEM?
- **64 GB kit (Arlsdorf, A3):** is the memtest screenshot available? Please pack the modules with padding.
- **2 TB drives (Wien 17, later):** would you accept €100 for the WD Red Plus and WD Black in one PayLivery parcel?

---

## 7. Running it in Morocco

- **Electricity.** Household tariffs run 0.90–1.60 MAD/kWh by tranche. These figures assume a household above 200 kWh/month: 1.1676–1.5958 MAD/kWh ≈ €0.105–0.143 per kWh at 1 EUR = 11.1221 MAD. **Every watt of 24/7 idle costs €0.92–1.26 a year.** All three builds idle at about 15–27 W without a graphics card.
- **Remote access from Singapore.**
  - Use Tailscale or WireGuard into Proxmox.
  - In the BIOS, set "Restore on AC power loss = Power On".
  - Add the Tapo P110 Type E smart plug (€22.39) so you can power-cycle the box from anywhere.
  - None of these builds has a remote BIOS console (IPMI). A GL.iNet Comet GL-RM1 KVM (€128.99 + €5.90 at mylemon.at, per the geizhals offer list) adds one later.
- **Flying it.**
  - Builds A1/A2 travel as parts in your own case, about 8–10 kg in checked baggage.
  - Take the cooler off, or pack it so it can't swing.
  - Carry the SSD and any HDDs in the cabin.
- **Heat and dust.** Keep the box in a ventilated room, not a closet. Set Proxmox temperature alerts and clean the filters every few months. A small UPS is a good later add-on.

---

## 8. Rejected, and why

| Option | Why not |
|---|---|
| i9-13900K (Graz, €270.60, 58,053 / 4,595) in A1 | €601.59, so just over budget. It's also the CPU most exposed to Raptor Lake ageing, and a Freezer 36 caps it well below its rated power. |
| i9-12900K (Wien, €260.60, 41,099 / 4,128) in A1 | €591.59, but the ad shows only a stock box image and a doubtful screenshot. It's slower than the 13700K for more money. |
| New i5-14600K / i7-12700K from alternate.at in A1 | €589.79 / €597.89. They fit and come with a 2-year shop warranty, but they're slower than the used 13700K (38,355 / 4,264 and 34,235 / 4,002). A reasonable swap if a warranty matters more to you. The 14600K also needs the 0x12F BIOS first. |
| Ryzen 9 5900X build ([5900X Wien €225.70](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/amd-ryzen-9-5900x-am4-cpu-1353259458/) + ASRock B550 Pro4 €95.90 (DiTech.at) + the same 2 × 16 GB, PSU, cooler and SSD + an HD 7750 display card €13.49) | Fits at €570.18, but it's slower than A1 on both counts (38,887 / 3,465), needs a display card, and idles about 15–20 W higher. The 5900X ad shows only stock photos. |
| Old Xeon E5 v4 workstations | Single-core ~2,050, far below the target. |
| Waldkraiburg 12900K PC, Stralsund 5950X, Villach 3900X, Röschitz 5900X, cheap Z440/T5810 workstations | **Pickup only or no shipping offered.** Removed; see `excluded_no_shipping.csv`. |
| Gaming PCs with big GPUs | They only fit the budget if the GPU is resold, and you asked to minimise reselling. |

---

## 9. Method and limits

- **Sources:**
  - Marketplaces: willhaben.at (tier 1) and kleinanzeigen.de (tier 2; no tier-2 item was needed here).
  - Shops/refurbishers: DiTech.at and alternate.at (pages opened); cyberport.at, alza.at, e-tec.at, Amazon.at and galaxus.at (prices from geizhals.at offer lists); refurbed.at, afbshop.de, itsco.de, lapstore.de, harlander.com, servershop24.de.
  - Not reachable from the research machine: eBay, leboncoin and Amazon product pages (Amazon prices come from geizhals.at).
- **Shipping check:** every ad's shipping field and text was read by script, in German, Slovenian, Hungarian, Czech/Slovak and Italian. Pickup-only, no-shipping and domestic-only ads were removed.
- **Verification:** each shortlisted listing was re-opened by a second, independent pass that looked at the photos and screenshots (RAM labels, SMART, CPU photos), then re-opened again on 10 Oct for this report.
- **Estimates:** idle power figures are estimates from comparable measurements (Hardwareluxx idle tests of 12th-gen Intel on Z690 DDR4 boards; WD and Toshiba datasheets), not measurements of these machines.
- All listings are in [`deals.csv`](deals.csv) (`used_in_build` = "€600 …").
