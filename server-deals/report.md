# Home server for €800: Villach → Morocco

*Researched 9–10 Oct 2026. Every listing below was re-opened on **10 Oct 2026** and was still active. A few shop prices come from the geizhals.at offer list because the shop's own page couldn't be opened from the research machine; each one is marked. Nothing has been bought and no seller has been contacted.*

**Rules this report follows:**
- **Only listings that ship to you.**
  - Austrian sellers with willhaben delivery (PayLivery) whose size/weight limit fits the item, or shops that deliver to Austria.
  - Anything whose ad says pickup only or offers no shipping is excluded. That covers 113 listings; see [`excluded_no_shipping.csv`](excluded_no_shipping.csv).
- **Upfront cash, delivered to Villach.** Nothing has to be resold to stay within budget.
- **Performance figures** are PassMark CPU Mark (multi-thread / single-thread) from cpubenchmark.net, matched by exact CPU id.
- **RAM:** 64 GB is required at this budget.
- **Storage:** an NVMe SSD plus a pair of 1–2 TB drives is enough, as you said.

Companion reports for smaller budgets: [`report_600.md`](report_600.md) and [`report_400.md`](report_400.md).

**What changed from the previous version of this report:**
- **Old Build 1 is gone.** That was the Waldkraiburg i9-12900K gaming PC, which is **pickup only**.
- **Several earlier alternatives are gone for the same reason:** the Stralsund 5950X, the Villach 3900X, the Röschitz 5900X, and the cheap HP Z440 / Dell T5810 / Heinfels Xeon listings are all pickup-only or offer no shipping.
- **The Xeon E5 v4 builds (old Builds 2 and 3) are dropped.** Their single-core speed (~2,050) is about half of a modern desktop's, and you asked for strong single *and* multi-core performance.
- **No build relies on reselling parts any more.**

---

## 1. Recommendation in one table

| | **B1: i7-13700K + 64 GB** (recommended) | **B2: new i7-12700K + 64 GB** (safest) | **B3: Ryzen 9 5900X + 64 GB ECC** |
|---|---|---|---|
| Delivered total | **€779.68** | €790.88 | €735.88 |
| Spare budget | €20.32 | €9.12 | €64.12 |
| CPU | i7-13700K, 8 P + 8 E cores, 24 threads, used | i7-12700K, 8 P + 4 E, 20 threads, **new with shop warranty** | Ryzen 9 5900X, 12 cores, 24 threads, used |
| **PassMark multi / single** | **45,590 / 4,325** | 34,235 / 4,002 | 38,887 / 3,465 |
| RAM | **64 GB** DDR4-2666 (4 × 16) | **64 GB** DDR4-2666 (4 × 16) | **64 GB** DDR4-2133 **ECC active** (4 × 16) |
| Board | Gigabyte B760M DS3H DDR4 (new, DiTech.at) | same | ASRock B550 Pro4 (new, DiTech.at) |
| Storage | 512 GB NVMe + 2 × 2 TB HDD mirror | same | same |
| Graphics | integrated | integrated | needs a display card (HD 7750 included in the total) |
| Idle power (estimate) | ~25–35 W | ~25–35 W | ~40–55 W |
| Electricity / year in Morocco | ~€23–44 | ~€23–44 | ~€37–69 |
| 4-year cost (total + electricity) | **€872–956** | €883–967 | €883–1,012 |
| Raptor Lake ageing risk | yes: needs the 0x12F BIOS update | **no** (Alder Lake) | no |
| Parcels | 7 | 7 | 8 |

**Ranking against your priorities** (CPU single + multi and 64 GB first, then upgradability, then idle power and ease):
1. **B1.** It is the fastest of the three, the cheapest to run, and among the cheapest to buy. The Tapo smart plug (€22.39) would take it to €802.07, so buy that after the budget.
2. **B2.** It gives up about 25% of multi-core speed for a brand-new CPU with a 2-year shop warranty and no Raptor Lake ageing risk.
3. **B3.** It's the only build with working ECC memory and has the most headroom, but it's slower per core, idles 15–20 W higher (about €14–25 a year more) and sits on the end-of-line AM4 platform.

---

## 2. Build B1: i7-13700K + 64 GB (recommended), €779.68

| Part | Listing | Seller, where, posted | Price | Delivery | Shipping |
|---|---|---|---|---|---|
| CPU: Intel Core i7-13700K, used | [willhaben 1691159762](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/intel-i7-13700k-1691159762/) | private, Fritzens (Tirol), 05.10 | €250 | €5.70 | willhaben Post ≤ 3 kg |
| Board: Gigabyte B760M DS3H DDR4, **new** | [DiTech.at, Art.-Nr. 361952](https://www.ditech.at/s/de/b760m-ds3h-ddr4): in stock, delivery in 1–2 working days | Austrian shop (branch in Klagenfurt) | €95.90 | €0 | free delivery in AT from €49 |
| RAM: **64 GB**, 4 × 16 GB SK hynix DDR4-2666 desktop UDIMM, memtest 0 errors | [willhaben 1774557909](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/64-gb-ddr4-ram-2666mhz-1774557909/) | private, Arlsdorf (Carinthia), 04.10 | €190 | €2.99 | willhaben letter |
| PSU: Corsair RM650i 650 W Gold, fully modular, all cables | [willhaben 1261438596](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/corsair-rm650i-1261438596/) | private, Haag, 04.10 | €45 | €5.70 | willhaben Post |
| Cooler: Arctic Freezer 36 (heatsink never mounted) | [willhaben 1153939913](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/cpu-kuehler-arctic-freezer-36-fuer-amd-und-intel-ungenutzt-1153939913/) | private, Gänserndorf, 24.09 | €15 | €5.70 | willhaben Post |
| SSD: Samsung PM9A1 512 GB NVMe (TLC + DRAM, PCIe 4.0) | [willhaben 832626534](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/m-2-mz-vl25120-samsung-512gb-pci-express-4-0x4-nvme-internal-solid-state-drive-832626534/) | private, Wien, 04.10 | €55 | €2.99 | willhaben letter |
| HDD mirror: 2 × 2 TB CMR (WD Red Plus 42,180 h + WD Black 16,752 h; SMART screenshots show 0 bad sectors) | [willhaben 1759125813](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/2tb-festplatten-1759125813/) | private, Wien 17, 09.10 | €100 | €5.70 | willhaben Post (both drives in one parcel) |
| **Total** | | | **€750.90** | **€28.78** | **€779.68** |
| *After the budget:* TP-Link Tapo P110 smart plug, **Type E** (fits Moroccan sockets) | [geizhals → alza.at](https://geizhals.at/tp-link-tapo-p110-a3694802.html) (price from the geizhals offer list; alza's page couldn't be opened) | shop | €17.90 | €4.49 | shop delivery in AT |
| **Total with plug** | | | | | €802.07, over budget, so buy it later |

Everything goes into **your own case**. All parts are standard ATX, and the board is mATX, which fits an ATX case.

**Why this build.**
- **Performance.** Apart from the i9-13900K variant below (€794.58, more exposed to Raptor Lake ageing), the i7-13700K is the strongest single- and multi-core CPU that fits with 64 GB. It has 8 performance cores, which is what CST uses, plus 8 efficiency cores for VMs and background jobs.
- **Integrated graphics.** Proxmox installs headless, there's no display card to power, and idle stays at about 25–35 W with both drives spinning.
- **Room to grow.** The new board has 4 DDR4 slots (up to 128 GB), 2 × M.2 PCIe 4.0, 4 × SATA (the 2 HDDs plus 2 more), 2.5 GbE and a PCIe 4.0 x16 slot for a GPU or 10 GbE card later.
- **Easy buying.** Every item ships within Austria with buyer protection (willhaben PayLivery) or from a shop. No pickups, and no German or Slovenian sellers who'd have to agree to post.

**Performance class.** About 11% more multi-core and 5% more single-core than the old i9-12900K build (41,099 / 4,128), and 2.1–2.4× the old Xeon builds (E5-2697 v4 / E5-2690 v4). RAM bandwidth is 42.7 GB/s theoretical: dual-channel DDR4-2666 with 2 modules per channel.

**Idle power: ~25–35 W, about €23–44 a year in Morocco.** The basis:
- **CPU, board and SSD:** an i5-12500 on two Z690 DDR4 boards, using only integrated graphics, measured 13–18 W at the wall (Hardwareluxx low-idle thread). The range adds margin for the 13700K, 4 DIMMs and this board.
- **Drives:** the WD Red Plus idles at about 2.5 W and the WD Black at about 6 W.

**Upgrade path:**
- **128 GB:** replace the four 16 GB modules with 4 × 32 GB.
- **Drives:** 2 more SATA ports, plus the second M.2 slot.
- **CPU:** a 14th-gen i7/i9 fits after a BIOS update (the board's Q-Flash Plus button flashes from a USB stick without a CPU). Keep the ~180 W power limit with this board and cooler.
- **Remote console:** a GL.iNet Comet GL-RM1 KVM (€128.99 + €5.90 at mylemon.at, per the geizhals offer list on 10 Oct), when the budget allows.

**Variants (swap only the CPU):**

| CPU | Listing | Delivered | Build total | PassMark | Note |
|---|---|---|---|---|---|
| **i5-13600K, new and factory-sealed, invoice from 26.05.2023** | [willhaben 1079149837](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/intel-core-i5-13600k-lga1700-neu-ovp-versiegelt-1079149837/), private, Stams, 24.09 | €245.70 | **€769.68** | 37,437 / 4,110 | Never used, with the original invoice. Intel doesn't honour warranty claims from second owners, so it carries no warranty for you. It also needs the 0x12F BIOS first. Only 6 P-cores. |
| i9-13900K, used, boxed | [willhaben 1428668791](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/intel-core-i9-13900k-1428668791/), private, Graz, 19.09 | €270.60 | €794.58 | 58,053 / 4,595 | Fastest, but the most exposed to Raptor Lake ageing. The Freezer 36 limits it to about 180 W. Only if it has an invoice, which proves where it came from; Intel won't honour warranty for a second owner. |
| i9-12900K, used, boxed | [willhaben 1219333468](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/intel-core-i9-12900k-1219333468/), private, Wien, 23.09 | €260.60 | €784.58 | 41,099 / 4,128 | No ageing risk, but the ad has only a stock image. Ask for a real photo. |

**Risks.**
- **Raptor Lake ageing** affects the 13th/14th-gen chips on Intel's list: i9, i7 and the i5-13600K/14600K.
  - Before any heavy load, update the board BIOS to Intel microcode **0x12F or newer**. That's Intel's May 2025 fix for machines left on for days under light load, which is exactly how a 24/7 server runs. The board's shipping BIOS already runs 13th-gen chips, so you can install the CPU first and flash from a USB stick.
  - Keep Intel's default power limits.
  - Ask the seller whether the chip was ever unstable.
  - This used chip has no box or invoice, so there is no Intel warranty. The sealed i5-13600K variant avoids a chip of unknown history, but it has no warranty for you either.
- **Cooling.** The Freezer 36 can't hold the 13700K's 253 W peak. Set PL1/PL2 to about 180 W in the BIOS, which costs a few percent of multi-core speed.
- **The board's M.2 slots are NVMe-only.** That's fine here; never add an M.2 SATA SSD.
- **The drives are used.** The WD Red has 4.8 years of power-on time, and the WD Black is from 2016. A mirror protects against one failure, but it is **not a backup**: keep important data off-site too.
  - The two drives are €50 each. Buying both in one €100 + €5.70 parcel needs the seller to accept an offer for both. Bought separately, they cost €5.70 more.
  - The seller appears to resell a stock of used drives (inventory numbers on the labels), so pay only through PayLivery.
  - The same seller also has 2 × IronWolf Pro 2 TB showing 50 h and 2 h. They were made in January 2019 and the low hours may have been reset, so ask for `smartctl -l farm` before trusting them. At €150 + €5.70 they would make the build €829.68, over budget, and their warranty has expired.
- **The PSU is about 8–11 years old** (first-generation RM650i), though it's a premium unit. Confirm the 4+4-pin CPU (EPS) cable and 2+ SATA leads are included.
- **The SSD's health isn't stated.** Ask for a CrystalDiskInfo screenshot.
- **The board price is DiTech.at's** (Austrian, opened 10 Oct). The geizhals offer list also shows Amazon.at at €88.64 and galaxus.at at €89.67. Those pages couldn't be opened from here; if their prices hold, they save about €6–7.

---

## 3. Build B2: new i7-12700K + 64 GB (safest), €790.88

The same parts as B1, with the used i7-13700K swapped for a **new i7-12700K from alternate.at**:

| Part | Listing | Delivered |
|---|---|---|
| CPU: Intel Core i7-12700K, **new (tray)**, in stock | [alternate.at](https://www.alternate.at/Intel/Core-i7-12700K-Prozessor/html/product/1778357) | €258 + €8.90 = €266.90 |
| Board, 64 GB RAM, PSU, cooler, SSD, HDD mirror | as in B1 | €523.98 |
| **Total** | | **€790.88** |

**Why:**
- **Shop warranty.** 2 years of statutory warranty plus a 14-day return right.
- **No Raptor Lake ageing risk**, because Alder Lake isn't affected.
- **The board's BIOS works as shipped** with 12th-gen chips.
- **The same 8 P-cores** as B1 for CST.

**Cost:** 25% less multi-core and 7% less single-core than B1, for €11.20 more. The Tapo plug would take it to €813.27, over budget.

**Alternative new CPU:** the [i5-14600K at alternate.at](https://www.alternate.at/Intel/Core-i5-14600K-Prozessor/html/product/100009806) costs €258.80 delivered and makes the build **€782.78**, at 38,355 / 4,264. It's faster than the 12700K but has 6 P-cores, and it's on Intel's Raptor Lake ageing list. If the board's BIOS predates 14th-gen support, it won't start with this chip, so first flash the newest BIOS (0x12F or later) with the board's Q-Flash Plus button, which needs no CPU.

**Risks:** a tray CPU comes without a cooler (the Freezer 36 is in the build). Set PL2 to about 180 W. The other parts carry the same caveats as B1.

---

## 4. Build B3: Ryzen 9 5900X + 64 GB ECC, €735.88

| Part | Listing | Seller, where, posted | Delivered |
|---|---|---|---|
| CPU: AMD Ryzen 9 5900X, used | [willhaben 1353259458](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/amd-ryzen-9-5900x-am4-cpu-1353259458/) | private, Wien, 08.10 | €220 + €5.70 = €225.70 |
| Board: ASRock B550 Pro4, **new** (ECC UDIMM supported with Ryzen 5000) | [DiTech.at, Art.-Nr. 304106](https://www.ditech.at/s/de/b550-pro4): ships in 2–3 working days | Austrian shop | €95.90 (free delivery from €49) |
| RAM: **64 GB ECC**, 4 × 16 GB Samsung DDR4-2133 ECC UDIMM | [willhaben 1153528073](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/64gb-2rx8-pc4-2133p-ee1-10-samsung-ram-1153528073/) | private, Allerheiligen bei Wildon, 06.10 | €160 + €5.70 = €165.70 |
| Display card: AMD HD 7750 1 GB | [willhaben 1532020151](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/hd-7750-1g-gddr5-1532020151/) | private, Dunkelsteinerwald, 04.10 | €10 + €3.49 (DPD) = €13.49 |
| PSU, cooler, SSD, HDD mirror | as in B1 | | €235.09 |
| **Total** | | | **€735.88** |

**Why:**
- **Working ECC memory.** The ASRock B550 Pro4 enables ECC with a Ryzen 5000 CPU, which is valuable for a 24/7 ZFS host.
- **12 equal cores**, so CST uses all 12.
- **€64.12 left**, enough for the Tapo plug (€22.39) and the tested display card below.

**Costs and risks:**
- **Slower per core** (3,465 vs 4,325).
- **Higher idle:** about 40–55 W, roughly €14–25 a year more than B1. Part of this is the display card, which you can pull after setup if the board boots without one.
- **Slow RAM.** DDR4-2133 has about 20% less bandwidth than B1's 2666 kit, which matters for FDTD/FEM.
- **AM4 is end-of-line.** The best drop-in is a 5950X.
- **Thin seller evidence.** The 5900X ad shows stock photos only, so ask for a real photo. The RAM seller's account is 10 days old (the photos are genuine), so pay only through PayLivery.
- **The HD 7750's ad doesn't say it works.** Ask, or take the tested [Villach-Auen HD 7750](https://www.willhaben.at/iad/object?adId=1025369866) at €24.70 (+€11.21).
- **The HD 7750 is a 2012 card** and probably has no UEFI GOP. Leave CSM enabled in the B550 BIOS (don't turn it off for Secure Boot), or you'll get no picture until you clear the CMOS.

---

## 5. What about the P720 and the Ryzen 9 options you asked about earlier?

| Earlier option | Status on 10 Oct | Verdict |
|---|---|---|
| Lenovo P720, 2 × Xeon Gold (Waltershausen DE) | Ships only within Germany (the seller says pickup is ideal); about 30 kg | **Rejected.** Single-core 2,141 per Gold 6140 fails your target, and it's a dual-CPU machine weighing about 30 kg. |
| Ryzen 9 5950X, Stralsund | Shipping field says "Nur Abholung" (pickup only) | **Excluded.** |
| New Ryzen 9 5950X (cyberport.at €326.56 + €9.99) in B3 | ships | B3 would cost €846.73, **over budget**. |
| New Ryzen 9 5900XT 16-core (cyberport.at €296.90 + €9.99) in B3 | ships | B3 would cost €817.07, **over budget**. |
| Röschitz 5900X PC, Villach 3900X | Pickup only / no shipping | **Excluded.** |

---

## 6. Buying order (on your go-ahead)

1. **The CPU and the 64 GB RAM kit first.** Used CPUs and RAM sell fastest. Ask the §7 questions before paying.
2. **The board** (shop).
3. **The PSU, cooler, SSD and HDD pair.** Make the €100 offer for both drives in one parcel.
4. **After the budget:** the Tapo P110 Type E smart plug (€22.39); it fits within €800 only in B3.

Pay private sellers only **through willhaben PayLivery**, which holds your money until delivery. Never pay by bank transfer outside it.

---

## 7. Questions for the sellers (nobody has been contacted)

- **i7-13700K (Fritzens):**
  - Which BIOS/microcode did it run, and since when?
  - Were there ever crashes or WHEA errors?
  - Is there an invoice?
  - Please send a second photo of the chip.
- **i5-13600K (Stams, if you choose that variant):** please send a photo of the invoice and confirm the seal is unbroken.
- **64 GB RAM (Arlsdorf):** is the memtest screenshot available? Please pack the modules in anti-static bags with padding. The ad's only delivery option is a €2.99 letter, whose carrier liability is just €50, but PayLivery refunds you if it never arrives.
- **RM650i (Haag):** are the 4+4-pin CPU (EPS) cable and at least 2 SATA power leads included? Roughly when was it bought?
- **PM9A1 (Wien):** please send a CrystalDiskInfo or smartctl screenshot (percentage used, power-on hours, media errors).
- **Freezer 36 (Gänserndorf):** are the LGA1700 (or AM4, for B3) mounting parts complete?
- **2 TB drives (Wien 17):** would you accept €100 for the WD Red Plus and WD Black together, shipped in one PayLivery parcel? Please confirm the SMART screenshots are current.
- **5900X (Wien, B3):** please send a photo of the actual CPU. Can you show it running (Ryzen Master or a CPU-Z screenshot)?
- **ECC RAM (Allerheiligen, B3):** have the modules been tested? Payment through PayLivery only.
- **HD 7750 (Dunkelsteinerwald, B3):** does the card work? A photo of it running?
- **i9-12900K (Wien, if you choose that variant):** please send a photo of the actual chip showing its S-spec.

---

## 8. Running it in Morocco

- **Electricity.** Household tariffs run 0.90–1.60 MAD/kWh by tranche. These figures assume a household above 200 kWh/month: 1.1676–1.5958 MAD/kWh ≈ €0.105–0.143 per kWh at 1 EUR = 11.1221 MAD. **Every watt of 24/7 idle costs €0.92–1.26 a year.** A 24/7 server can push a household into a dearer tranche.
- **Remote access from Singapore.**
  - Use Tailscale or WireGuard into Proxmox. Never expose the web UI directly.
  - In the BIOS, set "Restore on AC power loss = Power On".
  - With the Tapo P110 you can hard power-cycle the box and watch its wattage from your phone.
  - These builds have no remote BIOS console. A GL.iNet Comet GL-RM1 KVM (€128.99 + €5.90 at mylemon.at, per the geizhals offer list) adds one later.
- **Flying it.**
  - Builds B1–B3 travel as parts in your own case, about 8–10 kg in checked baggage.
  - Take the Freezer 36 off or pack it firmly.
  - Carry the SSD and HDDs in the cabin, in anti-static bags.
  - If you are a Moroccan resident abroad (MRE), the ADII Marhaba circular (2023) gives a 25,000 DH duty-free allowance for personal effects. Confirm the current rules with ADII before flying, and keep the purchase receipts.
- **Heat, dust and power cuts.**
  - Keep the box in a ventilated room, not a closet.
  - Set Proxmox drive-temperature alerts at 50 °C and clean the filters every few months.
  - A small UPS with USB shutdown (NUT) is the next add-on after the budget.

---

## 9. Market notes (prices seen 9–10 Oct 2026, delivered to Villach)

| Item | What it costs now |
|---|---|
| Used fast Intel CPUs (willhaben, PayLivery) | i7-13700K €255.70, i9-12900K €260.60, i9-13900K €270.60, i7-12700 €229.70, sealed i5-13600K €245.70 |
| New CPUs (alternate.at) | i5-14600K €258.80, i7-12700K €266.90, i5-14500 €255.80 |
| New B760 DDR4 boards | Gigabyte B760M DS3H DDR4 €95.90 at DiTech.at (geizhals also lists Amazon.at at €88.64); MSI PRO B760M-P DDR4 from €99.76 + €5.90 (mylemon.at, via geizhals) |
| 64 GB DDR4 | used 4 × 16 GB €165.70 (ECC 2133) to €192.99 (2666); used 2 × 32 GB €360.60; a sealed 2 × 32 GB kit from a private seller €405.70; new 2 × 32 GB from €493.12 (shop) |
| 32 GB DDR4 | used 2 × 16 GB €105.70–142.99; a sealed, new single 32 GB module from a private seller €145.70 |
| 2 TB HDD | used CMR €50–75 each (SMART-checked); new WD Red Plus 2 TB €152.26 at Amazon.at. The new Toshiba S300 2 TB at alternate.at is **SMR**, so avoid it for ZFS. |
| NVMe SSD | used Samsung 512 GB €57.99–62.67; used PM981 1 TB €101.99; new 1 TB TLC + DRAM from €194.99 |
| PSU 550–650 W Gold | used €40.70–65.70; new be quiet! Pure Power 12 550 W €73.80 |

The DRAM and NAND shortage of 2025–26 is why new RAM and SSDs cost so much more than used. Every build here buys them used from Austrian sellers.

---

## 10. Method and limits

- **Sources:**
  - Marketplaces: willhaben.at (tier 1), plus kleinanzeigen.de, bolha.com, hardverapro.hu and bazos (tier 2, fallback only; none was needed in these builds).
  - Shops/refurbishers: DiTech.at and alternate.at (pages opened); cyberport.at, alza.at, e-tec.at, Amazon.at and galaxus.at (prices from geizhals.at offer lists); refurbed.at, afbshop.de, itsco.de, lapstore.de, harlander.com, servershop24.de.
  - Morocco: ultrapc.ma and avito.ma, as buy-on-arrival references only.
  - Not reachable from the research machine: eBay, leboncoin and Amazon product pages (Amazon prices come from geizhals.at).
- **Shipping check:** all 316 earlier marketplace ads and every new one were re-opened by script, and their shipping field and text read in German, Slovenian, Hungarian, Czech/Slovak and Italian. Pickup-only, no-shipping, domestic-only and contradictory ads (113 in total) were removed into [`excluded_no_shipping.csv`](excluded_no_shipping.csv), with the evidence for each.
- **Verification:**
  - Each shortlisted listing was re-opened by an independent pass that tried to rule it out from its photos and screenshots: RAM labels, SMART screenshots, CPU photos, PSU labels.
  - Every listing in these builds was re-opened again on 10 Oct.
  - PassMark scores were matched to cpubenchmark.net by exact CPU id.
- **Estimates, not measurements:**
  - Idle power figures come from comparable measurements (Hardwareluxx idle tests of 12th-gen Intel on Z690 DDR4 boards; WD and Toshiba datasheets).
  - Electricity uses the tariff above.
  - Prices can change at any time.
- **All listings** that can be shipped are in [`deals.csv`](deals.csv). The `source_tier` column marks how easy each is to buy: tier 1 is an Austrian seller with delivery or a shop shipping to Austria. The `used_in_build` column marks which report and build use each one.
