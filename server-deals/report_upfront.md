# Home server: lowest cash upfront, no reselling

*Listings checked on 10 Oct 2026 (every one re-opened that afternoon by three independent checks). Delivered to Villach, or collected by you in Klagenfurt. Nothing has been bought and no seller has been contacted.*

> This answers your request: *"the best systems at each price point with the lowest money upfront. Minimize reselling."* Each budget is the **cash you pay**, and nothing has to be resold. The harvest reports ([€800](report.md), [€600](report_600.md), [€400](report_400.md)) are the other approach: cheaper **net**, but they need about €1,000–1,450 up front and several items to sell.

## How the totals are counted

- **Price + delivery + willhaben's buyer-protection fee.**
  - willhaben's help page (updated 8 Oct 2026) says the buyer pays *"mindestens 0,99 € bzw. ab 4,5% vom Artikelpreis (bis max. 49,99€)"*, and its worked example uses 5%. The exact fee is shown only at checkout.
  - So every total is a range: **4.5% / 5%**. The seller pays nothing.
  - Shop orders, the Klagenfurt cash pickup and the foreign sellers have no willhaben fee.
- **Poststation delivery.** Where an ad offers it, delivery to a Post parcel locker (Poststation) in Villach is used, because it is €1–2 cheaper than door delivery. Letters (used only for CPUs and M.2 drives) cannot go to a Poststation.
- **No damage cover by default.** A normal Post parcel only covers loss. Damage to electronics is covered only if the seller books *Erweiterte Haftung* (+€4.90). Only the 13900K seller has. Letters are covered to €50.
- **Not included:** the trip to Klagenfurt for the €25 Seasonic PSU, which only the €800 builds use (the €400 and €600 builds ship everything). Tier-2 delivery costs are labelled **estimate**.
- **Every build has a "budget check"** saying which of these could push it over: door delivery, a €1.99 minimum fee (an older willhaben image shows it), a €4.80 Poststation price (willhaben's help table), or the end of the €2.99 letter promotion (normally €4.40).

## The picks

| Budget | Build | Upfront (4.5% / 5% fee) | CPU (PassMark multi / single) |
|---|---|---|---|
| €400 | **U400-1** i5-13400 + new DS3H board + 64 GB, everything shipped | **€390.36 – €391.58** | 23,886 multi / 3,584 single (PassMark) |
| €600 | **U600-3** i7-13700KF + GT 1030 + 64 GB + matched 1 TB mirror | **€581.50 – €583.56** | about 40,000 multi at 125 W (45,520 stock) / 4,330 single |
| €800 | **U800-1** i9-13900K + 64 GB + 512 GB NVMe + near-new IronWolf Pro 2 TB mirror | **€744.17 – €746.99** | about 48,000 at 125 W / 4,595 |

- **€400: U400-1.** The best CPU that fits (single-core above your 3,400 target, multi-core 20% below 30k) with the full 64 GB, on a new board that takes a 13700K/13900K later. Its i5-13400 is the C0 version (Alder Lake die), so it is **not affected by the Raptor Lake ageing problem**, which matters for a server you can't reach. No mirror yet: a 1 TB pair adds about €44–49 later.
- **€600: U600-3.** Meets every target now (about 40k multi, 4,330 single, 64 GB, a mirror) and stays under €600 in every single fee or delivery case. For CST, which uses the 8 P-cores, the i7-13700KF is only a few percent behind the i9-13900K at the same 125 W cap. **U600-2** (the 13900K, mirror bought later) is €2 cheaper and the faster choice if the NAS can wait.
- **€800: U800-1.** Everything you asked for with Austrian sellers only: the 13900K, 64 GB, a 512 GB NVMe and two nearly unused 2 TB IronWolf Pro NAS drives, with about €53 to spare.

## All builds, ranked within each budget

**€400**

| Build | Upfront | CPU multi / single |
|---|---|---|
| **U400-1** i5-13400 + new DS3H board + 64 GB, everything shipped | **€390.36 – €391.58** | 23,886 / 3,584 |
| **U400-2** Same, with the Enermax 400 W PSU | **€396.36 – €397.58** | 23,886 / 3,584 |
| **U400-3** The Pfunds PC as it is (one parcel) | **€395.55 – €397.40** | 18,824 / 3,466 |

**€600**

| Build | Upfront | CPU multi / single |
|---|---|---|
| **U600-3** i7-13700KF + GT 1030 + 64 GB + matched 1 TB mirror | **€581.50 – €583.56** | ≈40,000 / 4,330 |
| **U600-2** i9-13900K + 64 GB + 512 GB NVMe, mirror bought later | **€579.41 – €581.48** | ≈48,000 / 4,595 |
| **U600-1** i9-13900K + 64 GB + 1 TB mirror, everything shipped | **€597.02 – €598.96** | ≈48,000 / 4,595 |

**€800**

| Build | Upfront | CPU multi / single |
|---|---|---|
| **U800-1** i9-13900K + 64 GB + 512 GB NVMe + near-new IronWolf Pro 2 TB mirror | **€744.17 – €746.99** | ≈48,000 / 4,595 |
| **U800-2** Same, with an HGST 7K2 + WD Red 2 TB mirror (no price request needed) | **€741.40 – €744.18** | ≈48,000 / 4,595 |
| **U800-3** NEW sealed i9-13900KS (Hungary) + 64 GB + 512 GB NVMe + 1 TB mirror | **€771.29 – €772.08** | ≈48,000–50,000 / 4,715 |
| **U800-4** Hagen (DE) bundle with DDR4-3200: the hedge if the 64 GB kit or the 13900K sells | **€769.13 – €769.48** | 44,507 / 4,275 (stock) |

*Multi-core figures at 125 W are sustained estimates from ComputerBase's measured scaling (i7-13700K 88% of stock, i9-13900K 83%). Set PL1 = PL2 = 125 W yourself in the BIOS; the board's default is not 125 W.*

## Build details

### €400

#### U400-1: i5-13400 + new DS3H board + 64 GB, everything shipped

**Upfront: €390.36 – €391.58** (4.5% / 5% fee). Intel i5-13400 (C0, integrated graphics): 23,886 multi / 3,584 single (PassMark). 64 GB DDR4-2400. 256 GB NVMe; no mirror yet. Idle about 18–25 W (estimate). 6 parcels, no trip.

**Buy:**

- **Intel Core i5-13400 (C0 stepping, SRMBP: Alder Lake die), integrated graphics**: €120.00 + €2.99 delivery + fee €5.40–€6.00 = **€128.39–€128.99** ([link](https://www.willhaben.at/iad/object?adId=1760100801))
  *private seller (Radnu, on willhaben since 2022), 1100 Wien, posted 2026-09-14; used, working, fixed price, no warranty; photos show SRMBP and CPU-Z C0. Delivery: willhaben PayLivery letter (Versandtasche) €2.99; no Poststation option. The €2.99 is a promotion (normally €4.40).*
- **64 GB DDR4-2400 ECC UDIMM, 4×16 GB Kingston KTD-PE424E/16G (2Rx8)**: €100.00 + €3.49 delivery + fee €4.50–€5.00 = **€107.99–€108.49** ([link](https://www.willhaben.at/iad/object?adId=1085665164))
  *private seller (Johannes, since 2011), 1050 Wien, posted 2026-10-10; used, 'einwandfreie Funktion', from a running system; sold without warranty or returns; ships only by PayLivery. Delivery: willhaben PayLivery Post up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*
- **Gigabyte B760M DS3H DDR4 (new)**: €95.90 + free delivery = **€95.90** ([link](https://www.ditech.at/de/shop/produkt/5994/gigabyte-ga-b760m-ds3h-ddr4.html))
  *DiTech.at (Austrian shop), Austria, in stock; new, 2-year warranty; 30-day low €91.90. Delivery: free delivery from €49, 1-2 working days.*
- **Corsair VS350 350 W 80 PLUS (75-001834), with power cord**: €10.00 + €3.49 delivery + fee €0.99 = **€14.48** ([link](https://www.willhaben.at/iad/object?adId=2023498904))
  *private seller (Marco, since 2022), 6460 Imst, posted 2026-10-08; used, 'sehr guter Zustand'; label 12 V 25 A (300 W), 200-240 V; about 2020; the cable photo shows a 4+4 CPU plug. Delivery: willhaben PayLivery Post up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*
- **Thermalright Assassin X 120 Refined SE tower cooler (LGA1700, 148 mm)**: €10.00 + €3.49 delivery + fee €0.99 = **€14.48** ([link](https://www.willhaben.at/iad/object?adId=1175187455))
  *private seller (Gal, since 2025), 9100 Völkermarkt, posted 2026-10-03; unused per the ad; box shows LGA1700 support; the pictured fan is the white ARGB type. Delivery: willhaben PayLivery Post up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*
- **SK hynix BC501 256 GB NVMe M.2 (boot + VMs)**: €25.00 + €2.99 delivery + fee €1.13–€1.25 = **€29.12–€29.24** ([link](https://www.willhaben.at/iad/object?adId=1781948440))
  *private seller (Damian, account since Aug 2026), 2410 Hainburg, posted 2026-09-25; used; smartctl photo: PASSED, 6% used, 6,519 h, 0 media errors. Delivery: willhaben PayLivery letter €2.99 (fine for an M.2 drive; promotion, normally €4.40).*

**Budget check:** Still fits with door delivery (€398.21), a €1.99 minimum fee (€394.32), a €4.80 Poststation price (€395.51) or the end of the €2.99 letter promotion (€394.40). It goes over only if several of these happen together (€403.77 with all of them).

#### U400-2: Same, with the Enermax 400 W PSU

**Upfront: €396.36 – €397.58** (4.5% / 5% fee). Intel i5-13400: 23,886 / 3,584. 64 GB DDR4-2400. 256 GB NVMe; no mirror yet. Idle about 18–25 W (estimate). 6 parcels, no trip.

**Buy:**

- **Intel Core i5-13400 (C0 stepping, SRMBP: Alder Lake die), integrated graphics**: €120.00 + €2.99 delivery + fee €5.40–€6.00 = **€128.39–€128.99** ([link](https://www.willhaben.at/iad/object?adId=1760100801))
  *private seller (Radnu, on willhaben since 2022), 1100 Wien, posted 2026-09-14; used, working, fixed price, no warranty; photos show SRMBP and CPU-Z C0. Delivery: willhaben PayLivery letter (Versandtasche) €2.99; no Poststation option. The €2.99 is a promotion (normally €4.40).*
- **64 GB DDR4-2400 ECC UDIMM, 4×16 GB Kingston KTD-PE424E/16G (2Rx8)**: €100.00 + €3.49 delivery + fee €4.50–€5.00 = **€107.99–€108.49** ([link](https://www.willhaben.at/iad/object?adId=1085665164))
  *private seller (Johannes, since 2011), 1050 Wien, posted 2026-10-10; used, 'einwandfreie Funktion', from a running system; sold without warranty or returns; ships only by PayLivery. Delivery: willhaben PayLivery Post up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*
- **Gigabyte B760M DS3H DDR4 (new)**: €95.90 + free delivery = **€95.90** ([link](https://www.ditech.at/de/shop/produkt/5994/gigabyte-ga-b760m-ds3h-ddr4.html))
  *DiTech.at (Austrian shop), Austria, in stock; new, 2-year warranty; 30-day low €91.90. Delivery: free delivery from €49, 1-2 working days.*
- **Enermax MaxPro II 400 W 80 PLUS (EMP400AGT-C)**: €16.00 + €3.49 delivery + fee €0.99 = **€20.48** ([link](https://www.willhaben.at/iad/object?adId=1030643088))
  *private seller (Marko, account since Sep 2026), 6460 Imst, posted 2026-10-02; used, 'wenig gelaufen'; label 12 V 30 A, made Dec 2020; ad lists a 4/8-pin CPU plug and 5 SATA plugs. Delivery: willhaben PayLivery Post up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*
- **Thermalright Assassin X 120 Refined SE tower cooler (LGA1700, 148 mm)**: €10.00 + €3.49 delivery + fee €0.99 = **€14.48** ([link](https://www.willhaben.at/iad/object?adId=1175187455))
  *private seller (Gal, since 2025), 9100 Völkermarkt, posted 2026-10-03; unused per the ad; box shows LGA1700 support; the pictured fan is the white ARGB type. Delivery: willhaben PayLivery Post up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*
- **SK hynix BC501 256 GB NVMe M.2 (boot + VMs)**: €25.00 + €2.99 delivery + fee €1.13–€1.25 = **€29.12–€29.24** ([link](https://www.willhaben.at/iad/object?adId=1781948440))
  *private seller (Damian, account since Aug 2026), 2410 Hainburg, posted 2026-09-25; used; smartctl photo: PASSED, 6% used, 6,519 h, 0 media errors. Delivery: willhaben PayLivery letter €2.99 (fine for an M.2 drive; promotion, normally €4.40).*

**Budget check:** Fragile: over €400 with door delivery (€404.21), a €1.99 minimum fee (€400.32), a €4.80 Poststation price (€401.51) or the end of the letter promotion (€400.40).

#### U400-3: The Pfunds PC as it is (one parcel)

**Upfront: €395.55 – €397.40** (4.5% / 5% fee). Intel i5-12400 (integrated graphics): 18,824 / 3,466. 32 GB DDR4 (4×8, all slots full). 1 TB SSD; no mirror. Idle about 25–30 W with the GTX 1650, 18–22 W without it (estimate). 1 parcel.

**Buy:**

- **Complete PC: i5-12400, MSI PRO B760M-P DDR4, 32 GB (4×8), GTX 1650, 1 TB SSD, be quiet! 450 W, Windows 11 Pro**: €370.00 + €8.90 delivery + fee €16.65–€18.50 = **€395.55–€397.40** ([link](https://www.willhaben.at/iad/object?adId=828154053))
  *private seller (Aaron, since 2019), 6542 Pfunds, posted 2026-10-09; used, working, no warranty; photos match the ad. Delivery: willhaben PayLivery Post up to 31.5 kg: €8.90 to a Poststation, if the box fits a locker (€9.90 to your door).*

**Budget check:** Fits in every case (worst €398.40). It is also the €400 fallback if the 64 GB kit sells, because it doesn't need it.

**Notes for €400:**
- **i5-13400 power:** Intel's default holds it at 65 W in long runs. Raise PL1 and PL2 (for example to 125–148 W) in the BIOS for full speed; the Assassin cooler and either PSU cover that, since there is no graphics card.
- **PSUs:** the VS350 (U400-1) is a basic 350 W unit from about 2020 (12 V 300 W), enough for this CPU and two drives but with no room for a graphics card. Ask for a photo of its CPU plug. The Enermax (U400-2) has 400 W and its 4/8-pin CPU plug is listed in the ad. The best PSU found, the Seasonic BC-650, is a Klagenfurt pickup: with the cheaper D3HP board it makes €396.88–398.10, which leaves only €1.90 for the trip (not counted).
- **Rejected for €400:**
  - The Ryzen 9 3900X build I posted earlier: its MSI B550-A PRO board was marked reserved at 15:59 on 10 Oct.
  - The Lenovo IdeaCentre 5 (Ryzen 7 5700G, 24 GB, €372.65–374.40): lowest cash, but it misses both CPU targets and can't reach 64 GB affordably.
  - No CPU with both 30k multi and 3,400 single fits under €400 with the rest of the parts. The cheap i7-12700K/KF and i5-14400F ads are pickup-only outside Klagenfurt/Villach.

### €600

#### U600-3: i7-13700KF + GT 1030 + 64 GB + matched 1 TB mirror

**Upfront: €581.50 – €583.56** (4.5% / 5% fee). Intel i7-13700KF (no integrated graphics, so a GT 1030): about 40,000 multi at 125 W (45,520 stock) / 4,330 single. 64 GB DDR4-2400. 256 GB NVMe + 2×1 TB Toshiba P300 mirror (2018/2019). Idle about 33–45 W (estimate). 8 parcels, no trip.

**Buy:**

- **Intel Core i7-13700KF (no integrated graphics)**: €185.00 + €3.49 delivery + fee €8.33–€9.25 = **€196.82–€197.74** ([link](https://www.willhaben.at/iad/object?adId=2110196000))
  *private seller (Peter, since 2008), 3400 Kierling, posted 2026-10-10; used, 'Bestzustand, nie übertaktet'. Delivery: willhaben PayLivery Post up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*
- **ASUS GeForce GT 1030 2 GB, low profile (UEFI display card for the KF)**: €35.00 + €3.49 delivery + fee €1.58–€1.75 = **€40.07–€40.24** ([link](https://www.willhaben.at/iad/object?adId=2056181722))
  *private seller (Sam, since 2021), 1180 Wien, posted 2026-09-29; used, working; ask whether a full-height bracket is included. Delivery: willhaben PayLivery Post up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*
- **64 GB DDR4-2400 ECC UDIMM, 4×16 GB Kingston KTD-PE424E/16G (2Rx8)**: €100.00 + €3.49 delivery + fee €4.50–€5.00 = **€107.99–€108.49** ([link](https://www.willhaben.at/iad/object?adId=1085665164))
  *private seller (Johannes, since 2011), 1050 Wien, posted 2026-10-10; used, 'einwandfreie Funktion', from a running system; sold without warranty or returns; ships only by PayLivery. Delivery: willhaben PayLivery Post up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*
- **Gigabyte B760M DS3H DDR4 (new)**: €95.90 + free delivery = **€95.90** ([link](https://www.ditech.at/de/shop/produkt/5994/gigabyte-ga-b760m-ds3h-ddr4.html))
  *DiTech.at (Austrian shop), Austria, in stock; new, 2-year warranty; 30-day low €91.90. Delivery: free delivery from €49, 1-2 working days.*
- **Enermax MaxPro II 400 W 80 PLUS (EMP400AGT-C)**: €16.00 + €3.49 delivery + fee €0.99 = **€20.48** ([link](https://www.willhaben.at/iad/object?adId=1030643088))
  *private seller (Marko, account since Sep 2026), 6460 Imst, posted 2026-10-02; used, 'wenig gelaufen'; label 12 V 30 A, made Dec 2020; ad lists a 4/8-pin CPU plug and 5 SATA plugs. Delivery: willhaben PayLivery Post up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*
- **Thermalright Assassin X 120 Refined SE tower cooler (LGA1700, 148 mm)**: €10.00 + €3.49 delivery + fee €0.99 = **€14.48** ([link](https://www.willhaben.at/iad/object?adId=1175187455))
  *private seller (Gal, since 2025), 9100 Völkermarkt, posted 2026-10-03; unused per the ad; box shows LGA1700 support; the pictured fan is the white ARGB type. Delivery: willhaben PayLivery Post up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*
- **SK hynix BC501 256 GB NVMe M.2 (boot + VMs)**: €25.00 + €2.99 delivery + fee €1.13–€1.25 = **€29.12–€29.24** ([link](https://www.willhaben.at/iad/object?adId=1781948440))
  *private seller (Damian, account since Aug 2026), 2410 Hainburg, posted 2026-09-25; used; smartctl photo: PASSED, 6% used, 6,519 h, 0 media errors. Delivery: willhaben PayLivery letter €2.99 (fine for an M.2 drive; promotion, normally €4.40).*
- **2× Toshiba P300 1 TB 7200 rpm (HDWD110), mirror pair**: €70.00 + €3.49 delivery + fee €3.15–€3.50 = **€76.64–€76.99** ([link](https://www.willhaben.at/iad/object?adId=2002227039))
  *private seller (Aleksandra, since 2019), 1080 Wien, posted 2026-09-12; used, 'funktioniert wie neu'; labels Nov 2018 and Aug 2019; hours not shown. Ad: €40 each, €70 for both. Delivery: one PayLivery request (Anfrage) at €70 for both, one Post parcel up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*

**Budget check:** Fits in every single case (door delivery €596.82, €4.80 Poststation €591.42, €1.99 minimum €586.54). Only all of them together goes over (€601.21).

#### U600-2: i9-13900K + 64 GB + 512 GB NVMe, mirror bought later

**Upfront: €579.41 – €581.48** (4.5% / 5% fee). Intel i9-13900K (integrated graphics): about 48,000 at 125 W / 4,595. 64 GB DDR4-2400. 512 GB NVMe; no mirror yet. Idle about 20–28 W (estimate). 6 parcels, no trip.

**Buy:**

- **Intel Core i9-13900K, integrated graphics**: €260.00 + €8.39 delivery + fee €11.70–€13.00 = **€280.09–€281.39** ([link](https://www.willhaben.at/iad/object?adId=1428668791))
  *private seller (Julian, since 2022), 8010 Graz, posted 2026-09-19; used, 'selten genützt', 'nie übertaktet', still in the seller's PC; photos show the original retail box (BX8071513900K, SRMBH); receipt not mentioned; no Intel warranty for a second owner. Delivery: willhaben PayLivery Post up to 3 kg with the seller-booked damage cover (Erweiterte Haftung): €8.39 to a Poststation (€10.60 to your door).*
- **64 GB DDR4-2400 ECC UDIMM, 4×16 GB Kingston KTD-PE424E/16G (2Rx8)**: €100.00 + €3.49 delivery + fee €4.50–€5.00 = **€107.99–€108.49** ([link](https://www.willhaben.at/iad/object?adId=1085665164))
  *private seller (Johannes, since 2011), 1050 Wien, posted 2026-10-10; used, 'einwandfreie Funktion', from a running system; sold without warranty or returns; ships only by PayLivery. Delivery: willhaben PayLivery Post up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*
- **Gigabyte B760M DS3H DDR4 (new)**: €95.90 + free delivery = **€95.90** ([link](https://www.ditech.at/de/shop/produkt/5994/gigabyte-ga-b760m-ds3h-ddr4.html))
  *DiTech.at (Austrian shop), Austria, in stock; new, 2-year warranty; 30-day low €91.90. Delivery: free delivery from €49, 1-2 working days.*
- **Enermax MaxPro II 400 W 80 PLUS (EMP400AGT-C)**: €16.00 + €3.49 delivery + fee €0.99 = **€20.48** ([link](https://www.willhaben.at/iad/object?adId=1030643088))
  *private seller (Marko, account since Sep 2026), 6460 Imst, posted 2026-10-02; used, 'wenig gelaufen'; label 12 V 30 A, made Dec 2020; ad lists a 4/8-pin CPU plug and 5 SATA plugs. Delivery: willhaben PayLivery Post up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*
- **Thermalright Assassin X 120 Refined SE tower cooler (LGA1700, 148 mm)**: €10.00 + €3.49 delivery + fee €0.99 = **€14.48** ([link](https://www.willhaben.at/iad/object?adId=1175187455))
  *private seller (Gal, since 2025), 9100 Völkermarkt, posted 2026-10-03; unused per the ad; box shows LGA1700 support; the pictured fan is the white ARGB type. Delivery: willhaben PayLivery Post up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*
- **Samsung PM9A1 512 GB NVMe PCIe 4.0 (boot + VMs)**: €55.00 + €2.99 delivery + fee €2.48–€2.75 = **€60.47–€60.74** ([link](https://www.willhaben.at/iad/object?adId=832626534))
  *private seller (Christian, since 2020), 1170 Wien, posted 2026-10-04; used; no health data in the ad. Delivery: willhaben PayLivery letter €2.99 (promotion, normally €4.40).*

**Budget check:** Fits in every single case (door delivery €590.32, €1.99 minimum €583.48, €4.80 Poststation €586.72) and with all of them together (€593.73).

#### U600-1: i9-13900K + 64 GB + 1 TB mirror, everything shipped

**Upfront: €597.02 – €598.96** (4.5% / 5% fee). Intel i9-13900K (integrated graphics): about 48,000 multi at 125 W (58,053 stock) / 4,595 single. 64 GB DDR4-2400. 256 GB NVMe + 2×1 TB HDD mirror (2010/2011 drives). Idle about 28–40 W (estimate). 8 parcels, no trip.

**Buy:**

- **Intel Core i9-13900K, integrated graphics**: €260.00 + €8.39 delivery + fee €11.70–€13.00 = **€280.09–€281.39** ([link](https://www.willhaben.at/iad/object?adId=1428668791))
  *private seller (Julian, since 2022), 8010 Graz, posted 2026-09-19; used, 'selten genützt', 'nie übertaktet', still in the seller's PC; photos show the original retail box (BX8071513900K, SRMBH); receipt not mentioned; no Intel warranty for a second owner. Delivery: willhaben PayLivery Post up to 3 kg with the seller-booked damage cover (Erweiterte Haftung): €8.39 to a Poststation (€10.60 to your door).*
- **64 GB DDR4-2400 ECC UDIMM, 4×16 GB Kingston KTD-PE424E/16G (2Rx8)**: €100.00 + €3.49 delivery + fee €4.50–€5.00 = **€107.99–€108.49** ([link](https://www.willhaben.at/iad/object?adId=1085665164))
  *private seller (Johannes, since 2011), 1050 Wien, posted 2026-10-10; used, 'einwandfreie Funktion', from a running system; sold without warranty or returns; ships only by PayLivery. Delivery: willhaben PayLivery Post up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*
- **Gigabyte B760M DS3H DDR4 (new)**: €95.90 + free delivery = **€95.90** ([link](https://www.ditech.at/de/shop/produkt/5994/gigabyte-ga-b760m-ds3h-ddr4.html))
  *DiTech.at (Austrian shop), Austria, in stock; new, 2-year warranty; 30-day low €91.90. Delivery: free delivery from €49, 1-2 working days.*
- **Enermax MaxPro II 400 W 80 PLUS (EMP400AGT-C)**: €16.00 + €3.49 delivery + fee €0.99 = **€20.48** ([link](https://www.willhaben.at/iad/object?adId=1030643088))
  *private seller (Marko, account since Sep 2026), 6460 Imst, posted 2026-10-02; used, 'wenig gelaufen'; label 12 V 30 A, made Dec 2020; ad lists a 4/8-pin CPU plug and 5 SATA plugs. Delivery: willhaben PayLivery Post up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*
- **Thermalright Assassin X 120 Refined SE tower cooler (LGA1700, 148 mm)**: €10.00 + €3.49 delivery + fee €0.99 = **€14.48** ([link](https://www.willhaben.at/iad/object?adId=1175187455))
  *private seller (Gal, since 2025), 9100 Völkermarkt, posted 2026-10-03; unused per the ad; box shows LGA1700 support; the pictured fan is the white ARGB type. Delivery: willhaben PayLivery Post up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*
- **SK hynix BC501 256 GB NVMe M.2 (boot + VMs)**: €25.00 + €2.99 delivery + fee €1.13–€1.25 = **€29.12–€29.24** ([link](https://www.willhaben.at/iad/object?adId=1781948440))
  *private seller (Damian, account since Aug 2026), 2410 Hainburg, posted 2026-09-25; used; smartctl photo: PASSED, 6% used, 6,519 h, 0 media errors. Delivery: willhaben PayLivery letter €2.99 (fine for an M.2 drive; promotion, normally €4.40).*
- **Seagate Barracuda 1 TB ST31000528AS, 7200 rpm (mirror drive A)**: €20.00 + €3.49 delivery + fee €0.99–€1.00 = **€24.48–€24.49** ([link](https://www.willhaben.at/iad/object?adId=1141285675))
  *private seller (Andy, since 2025), 2413 Berg, posted 2026-09-26; used, 'getestet ohne Fehler'; HDDScan (July 2026): about 475 power-on hours, 4,866 start/stops, 0 bad sectors; made 2010. Delivery: willhaben PayLivery Post parcel up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*
- **WD Caviar Blue 1 TB WD10EALX, 7200 rpm (mirror drive B)**: €20.00 + €3.49 delivery + fee €0.99–€1.00 = **€24.48–€24.49** ([link](https://www.willhaben.at/iad/object?adId=1399395867))
  *private seller (Matthias, since 2025), 3424 Wolfpassing, posted 2026-09-15; 'nicht verwendet, nur ausgepackt' (unused); label Feb 2011; no SMART shown. Delivery: willhaben PayLivery Post parcel up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*

**Budget check:** Only €1.04 to spare. Over €600 with door delivery (€612.22), a €1.99 minimum fee (€603.68), a €4.80 Poststation price (€606.82), the end of the letter promotion (€600.37), or any fee above about 5.24%. Buy the two drives last; without them it is €548.06–549.98.

**Notes for €600:**
- **GT 1030 (U600-3):** the ad says low profile. Ask whether a full-height bracket is included, so it can be screwed into your ATX case for the flight.
- **The P300 pair (U600-3):** desktop CMR drives, dated Nov 2018 and Aug 2019, hours not shown. Agree €70 for both in chat, then send one PayLivery request at €70.
- **The 1 TB drives in U600-1** are from 2010–2011. One has about 475 hours (HDDScan), the other is unused, but both are 15 years old. That matters for a mirror you can't reach from Singapore.
- **Enermax 400 W** in all three: a basic PSU, fine at a 125 W cap. Its efficiency at 30–40 W idle is lower than the Seasonic's. The Seasonic BC-650 (€25 cash, Klagenfurt) is the better PSU, but it costs €4.52 more plus the trip, which U600-1 can't afford.

### €800

#### U800-1: i9-13900K + 64 GB + 512 GB NVMe + near-new IronWolf Pro 2 TB mirror

**Upfront: €744.17 – €746.99** (4.5% / 5% fee). Intel i9-13900K (integrated graphics): about 48,000 at 125 W / 4,595. 64 GB DDR4-2400. 512 GB NVMe + 2×2 TB IronWolf Pro mirror (50 h and 2 h). Idle about 32–45 W (estimate). 6 parcels + 1 Klagenfurt pickup.

**Buy:**

- **Intel Core i9-13900K, integrated graphics**: €260.00 + €8.39 delivery + fee €11.70–€13.00 = **€280.09–€281.39** ([link](https://www.willhaben.at/iad/object?adId=1428668791))
  *private seller (Julian, since 2022), 8010 Graz, posted 2026-09-19; used, 'selten genützt', 'nie übertaktet', still in the seller's PC; photos show the original retail box (BX8071513900K, SRMBH); receipt not mentioned; no Intel warranty for a second owner. Delivery: willhaben PayLivery Post up to 3 kg with the seller-booked damage cover (Erweiterte Haftung): €8.39 to a Poststation (€10.60 to your door).*
- **64 GB DDR4-2400 ECC UDIMM, 4×16 GB Kingston KTD-PE424E/16G (2Rx8)**: €100.00 + €3.49 delivery + fee €4.50–€5.00 = **€107.99–€108.49** ([link](https://www.willhaben.at/iad/object?adId=1085665164))
  *private seller (Johannes, since 2011), 1050 Wien, posted 2026-10-10; used, 'einwandfreie Funktion', from a running system; sold without warranty or returns; ships only by PayLivery. Delivery: willhaben PayLivery Post up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*
- **Gigabyte B760M DS3H DDR4 (new)**: €95.90 + free delivery = **€95.90** ([link](https://www.ditech.at/de/shop/produkt/5994/gigabyte-ga-b760m-ds3h-ddr4.html))
  *DiTech.at (Austrian shop), Austria, in stock; new, 2-year warranty; 30-day low €91.90. Delivery: free delivery from €49, 1-2 working days.*
- **Seasonic CORE BC-650 650 W 80+ Bronze, with invoice (12.08.2026)**: €25.00 + pickup = **€25.00** ([link](https://www.willhaben.at/iad/object?adId=1948908843))
  *private seller (Daniel, account since Aug 2026), 9020 Klagenfurt, posted 2026-09-18; about 1 month used, 'wie neu', e-tec invoice included; 1 CPU plug, exactly 2 SATA power plugs. Delivery: pickup in Klagenfurt, cash (no PayLivery, so no fee and no buyer protection); the trip is not counted.*
- **Thermalright Assassin X 120 Refined SE tower cooler (LGA1700, 148 mm)**: €10.00 + €3.49 delivery + fee €0.99 = **€14.48** ([link](https://www.willhaben.at/iad/object?adId=1175187455))
  *private seller (Gal, since 2025), 9100 Völkermarkt, posted 2026-10-03; unused per the ad; box shows LGA1700 support; the pictured fan is the white ARGB type. Delivery: willhaben PayLivery Post up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*
- **Samsung PM9A1 512 GB NVMe PCIe 4.0 (boot + VMs)**: €55.00 + €2.99 delivery + fee €2.48–€2.75 = **€60.47–€60.74** ([link](https://www.willhaben.at/iad/object?adId=832626534))
  *private seller (Christian, since 2020), 1170 Wien, posted 2026-10-04; used; no health data in the ad. Delivery: willhaben PayLivery letter €2.99 (promotion, normally €4.40).*
- **2× Seagate IronWolf Pro 2 TB ST2000NE0025 (NAS, CMR), mirror pair**: €150.00 + €3.49 delivery + fee €6.75–€7.50 = **€160.24–€160.99** ([link](https://www.willhaben.at/iad/object?adId=1759125813))
  *private seller (Katrin, since 2020), 1170 Wien, posted 2026-10-09; used, nearly new: CrystalDiskInfo 50 h and 2 h, 0 bad sectors; made about Jan 2019. The ad lists 5 drives; these two are €75 each. Delivery: one PayLivery request (Anfrage) at €150 for both, after agreeing in chat; one Post parcel up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*

**Budget check:** Fits in every case, including all of them together (€758.24). There's room for two sensible extras: ask Katrin to book the €4.90 damage cover on the drive parcel, and add a smart plug (€12.48, below): €764.37 in total.

#### U800-2: Same, with an HGST 7K2 + WD Red 2 TB mirror (no price request needed)

**Upfront: €741.40 – €744.18** (4.5% / 5% fee). Intel i9-13900K: about 48,000 at 125 W / 4,595. 64 GB DDR4-2400. 512 GB NVMe + HGST Ultrastar 2 TB + WD Red 2 TB (29 h) mirror. Idle about 30–42 W (estimate). 7 parcels + 1 Klagenfurt pickup.

**Buy:**

- **Intel Core i9-13900K, integrated graphics**: €260.00 + €8.39 delivery + fee €11.70–€13.00 = **€280.09–€281.39** ([link](https://www.willhaben.at/iad/object?adId=1428668791))
  *private seller (Julian, since 2022), 8010 Graz, posted 2026-09-19; used, 'selten genützt', 'nie übertaktet', still in the seller's PC; photos show the original retail box (BX8071513900K, SRMBH); receipt not mentioned; no Intel warranty for a second owner. Delivery: willhaben PayLivery Post up to 3 kg with the seller-booked damage cover (Erweiterte Haftung): €8.39 to a Poststation (€10.60 to your door).*
- **64 GB DDR4-2400 ECC UDIMM, 4×16 GB Kingston KTD-PE424E/16G (2Rx8)**: €100.00 + €3.49 delivery + fee €4.50–€5.00 = **€107.99–€108.49** ([link](https://www.willhaben.at/iad/object?adId=1085665164))
  *private seller (Johannes, since 2011), 1050 Wien, posted 2026-10-10; used, 'einwandfreie Funktion', from a running system; sold without warranty or returns; ships only by PayLivery. Delivery: willhaben PayLivery Post up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*
- **Gigabyte B760M DS3H DDR4 (new)**: €95.90 + free delivery = **€95.90** ([link](https://www.ditech.at/de/shop/produkt/5994/gigabyte-ga-b760m-ds3h-ddr4.html))
  *DiTech.at (Austrian shop), Austria, in stock; new, 2-year warranty; 30-day low €91.90. Delivery: free delivery from €49, 1-2 working days.*
- **Seasonic CORE BC-650 650 W 80+ Bronze, with invoice (12.08.2026)**: €25.00 + pickup = **€25.00** ([link](https://www.willhaben.at/iad/object?adId=1948908843))
  *private seller (Daniel, account since Aug 2026), 9020 Klagenfurt, posted 2026-09-18; about 1 month used, 'wie neu', e-tec invoice included; 1 CPU plug, exactly 2 SATA power plugs. Delivery: pickup in Klagenfurt, cash (no PayLivery, so no fee and no buyer protection); the trip is not counted.*
- **Thermalright Assassin X 120 Refined SE tower cooler (LGA1700, 148 mm)**: €10.00 + €3.49 delivery + fee €0.99 = **€14.48** ([link](https://www.willhaben.at/iad/object?adId=1175187455))
  *private seller (Gal, since 2025), 9100 Völkermarkt, posted 2026-10-03; unused per the ad; box shows LGA1700 support; the pictured fan is the white ARGB type. Delivery: willhaben PayLivery Post up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*
- **Samsung PM9A1 512 GB NVMe PCIe 4.0 (boot + VMs)**: €55.00 + €2.99 delivery + fee €2.48–€2.75 = **€60.47–€60.74** ([link](https://www.willhaben.at/iad/object?adId=832626534))
  *private seller (Christian, since 2020), 1170 Wien, posted 2026-10-04; used; no health data in the ad. Delivery: willhaben PayLivery letter €2.99 (promotion, normally €4.40).*
- **HGST Ultrastar 7K2 2 TB HUS722T2TALA604, enterprise 7200 rpm (mirror drive A)**: €45.00 + €3.49 delivery + fee €2.03–€2.25 = **€50.52–€50.74** ([link](https://www.willhaben.at/iad/object?adId=1071713657))
  *private seller (Christoph, since 2019), 2122 Riedenthal, posted 2026-09-11; used, 'sehr guter Zustand'; label Nov 2017; hours not shown. Delivery: willhaben PayLivery Post parcel up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*
- **WD Red 2 TB WD20EFRX, NAS CMR 5,400 rpm (mirror drive B)**: €99.00 + €3.49 delivery + fee €4.46–€4.95 = **€106.95–€107.44** ([link](https://www.willhaben.at/iad/object?adId=975513975))
  *private seller (Markus, since 2012), 2880 Kirchberg am Wechsel, posted 2026-10-10; used, 29 operating hours (ad text and screenshot); made Oct 2018. Delivery: willhaben PayLivery Post parcel up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*

**Budget check:** Fits in every case (worst €757.64). Use it if Katrin won't sell the two IronWolf Pros for €150.

#### U800-3: NEW sealed i9-13900KS (Hungary) + 64 GB + 512 GB NVMe + 1 TB mirror

**Upfront: €771.29 – €772.08** (4.5% / 5% fee). Intel i9-13900KS, new (integrated graphics): about 48,000–50,000 at 125 W (60,385 stock) / 4,715 single. 64 GB DDR4-2400. 512 GB NVMe + 2×1 TB HDD mirror (2010/2011 drives). Idle about 28–40 W (estimate). 1 foreign seller + 6 parcels + 1 Klagenfurt pickup.

**Buy:**

- **Intel Core i9-13900KS, NEW sealed box (BX8071513900KS), factory warranty to 2029-05-14 per the ad**: €418.49 (CPU + GLS estimate, live Wise quote) = **€418.49** ([link](https://hardverapro.hu/apro/intel_i7-i9_cpuk_13700kf_13900k_13900ks_14700k/friss.html))
  *hardverapro seller J4Fun (20 years, 657 positive ratings; private or business not shown), Budapest, Hungary, posted 2026-09-30; new, unopened; 145,000 Ft with factory warranty (124,990 Ft with 1 month). Delivery: tier 2: the seller must agree to post to Austria ('csomagküldéssel is'). GLS CsomagPont XS 6,490 Ft is an ESTIMATE (size S would be 10,190 Ft). €418.49 is a live Wise quote for 151,490 Ft by bank transfer, fee included; no buyer protection.*
- **64 GB DDR4-2400 ECC UDIMM, 4×16 GB Kingston KTD-PE424E/16G (2Rx8)**: €100.00 + €3.49 delivery + fee €4.50–€5.00 = **€107.99–€108.49** ([link](https://www.willhaben.at/iad/object?adId=1085665164))
  *private seller (Johannes, since 2011), 1050 Wien, posted 2026-10-10; used, 'einwandfreie Funktion', from a running system; sold without warranty or returns; ships only by PayLivery. Delivery: willhaben PayLivery Post up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*
- **Gigabyte B760M DS3H DDR4 (new)**: €95.90 + free delivery = **€95.90** ([link](https://www.ditech.at/de/shop/produkt/5994/gigabyte-ga-b760m-ds3h-ddr4.html))
  *DiTech.at (Austrian shop), Austria, in stock; new, 2-year warranty; 30-day low €91.90. Delivery: free delivery from €49, 1-2 working days.*
- **Seasonic CORE BC-650 650 W 80+ Bronze, with invoice (12.08.2026)**: €25.00 + pickup = **€25.00** ([link](https://www.willhaben.at/iad/object?adId=1948908843))
  *private seller (Daniel, account since Aug 2026), 9020 Klagenfurt, posted 2026-09-18; about 1 month used, 'wie neu', e-tec invoice included; 1 CPU plug, exactly 2 SATA power plugs. Delivery: pickup in Klagenfurt, cash (no PayLivery, so no fee and no buyer protection); the trip is not counted.*
- **Thermalright Assassin X 120 Refined SE tower cooler (LGA1700, 148 mm)**: €10.00 + €3.49 delivery + fee €0.99 = **€14.48** ([link](https://www.willhaben.at/iad/object?adId=1175187455))
  *private seller (Gal, since 2025), 9100 Völkermarkt, posted 2026-10-03; unused per the ad; box shows LGA1700 support; the pictured fan is the white ARGB type. Delivery: willhaben PayLivery Post up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*
- **Samsung PM9A1 512 GB NVMe PCIe 4.0 (boot + VMs)**: €55.00 + €2.99 delivery + fee €2.48–€2.75 = **€60.47–€60.74** ([link](https://www.willhaben.at/iad/object?adId=832626534))
  *private seller (Christian, since 2020), 1170 Wien, posted 2026-10-04; used; no health data in the ad. Delivery: willhaben PayLivery letter €2.99 (promotion, normally €4.40).*
- **Seagate Barracuda 1 TB ST31000528AS, 7200 rpm (mirror drive A)**: €20.00 + €3.49 delivery + fee €0.99–€1.00 = **€24.48–€24.49** ([link](https://www.willhaben.at/iad/object?adId=1141285675))
  *private seller (Andy, since 2025), 2413 Berg, posted 2026-09-26; used, 'getestet ohne Fehler'; HDDScan (July 2026): about 475 power-on hours, 4,866 start/stops, 0 bad sectors; made 2010. Delivery: willhaben PayLivery Post parcel up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*
- **WD Caviar Blue 1 TB WD10EALX, 7200 rpm (mirror drive B)**: €20.00 + €3.49 delivery + fee €0.99–€1.00 = **€24.48–€24.49** ([link](https://www.willhaben.at/iad/object?adId=1399395867))
  *private seller (Matthias, since 2025), 3424 Wolfpassing, posted 2026-09-15; 'nicht verwendet, nur ausgepackt' (unused); label Feb 2011; no SMART shown. Delivery: willhaben PayLivery Post parcel up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*

**Budget check:** Against the estimate: €781.50–782.29 if GLS charges size S, and over €800 (€803.91) if that combines with door delivery, a €1.99 minimum and damage cover on both drives.

#### U800-4: Hagen (DE) bundle with DDR4-3200: the hedge if the 64 GB kit or the 13900K sells

**Upfront: €769.13 – €769.48** (4.5% / 5% fee). Intel i9-13900 (non-K, integrated graphics): 44,507 / 4,275 stock (an estimate at 100–125 W on this board). 64 GB DDR4-3200 (33% more bandwidth). 128 GB M.2 + 2×1 TB Toshiba P300 mirror. Idle about 30–42 W (estimate). 1 German seller + 1 parcel + 1 Klagenfurt pickup.

**Buy:**

- **Bundle: i9-13900 + Gigabyte B760M D3HP DDR4 + 64 GB DDR4-3200 (4×16) + Noctua NH-U14S + 128 GB M.2**: €650.00 + €17.49 DHL estimate = **€667.49** ([link](https://www.kleinanzeigen.de/s-anzeige/gb-mainboard-i9-13900-64gb-ddr4-128gb-m-2-bundle/3527633702-225-2013))
  *private seller on Kleinanzeigen, 58099 Hagen, Germany, posted 2026-09-30; used, 'Gut', all parts working; price negotiable (VB). Delivery: tier 2: 'Versand möglich' (domestic from €6.19); the seller must agree to post to Austria. DHL parcel DE→AT up to 5 kg €17.49 online is an ESTIMATE (€20.49 at a branch); paid by bank transfer, no buyer protection.*
- **Seasonic CORE BC-650 650 W 80+ Bronze, with invoice (12.08.2026)**: €25.00 + pickup = **€25.00** ([link](https://www.willhaben.at/iad/object?adId=1948908843))
  *private seller (Daniel, account since Aug 2026), 9020 Klagenfurt, posted 2026-09-18; about 1 month used, 'wie neu', e-tec invoice included; 1 CPU plug, exactly 2 SATA power plugs. Delivery: pickup in Klagenfurt, cash (no PayLivery, so no fee and no buyer protection); the trip is not counted.*
- **2× Toshiba P300 1 TB 7200 rpm (HDWD110), mirror pair**: €70.00 + €3.49 delivery + fee €3.15–€3.50 = **€76.64–€76.99** ([link](https://www.willhaben.at/iad/object?adId=2002227039))
  *private seller (Aleksandra, since 2019), 1080 Wien, posted 2026-09-12; used, 'funktioniert wie neu'; labels Nov 2018 and Aug 2019; hours not shown. Ad: €40 each, €70 for both. Delivery: one PayLivery request (Anfrage) at €70 for both, one Post parcel up to 3 kg: €3.49 to a Poststation (€5.70 to your door).*

**Budget check:** Fits against the estimate (DHL at a branch: €772.48). The €667.49 is an unprotected bank transfer.

**Notes for €800:**
- **IronWolf Pro pair (U800-1):** the ad lists five drives with the price field showing €50 (the cheapest). The two Pros are €75 each in the ad text. willhaben's help says several items from one ad are bought with one PayLivery request at the agreed price, after agreeing in chat. Ask Katrin to pad each drive and book the €4.90 damage cover.
- **No-trip version:** with the shipped Enermax 400 W instead of the Klagenfurt Seasonic, U800-1 is €739.65–742.47 and U800-2 €736.88–739.66. At €800 the Seasonic (1 month old, invoice) is worth the trip.
- **The new i9-13900KS (U800-3):** at 125 W it is only about 2–4% faster than the 13900K. The ad promises a factory warranty to 2029-05-14, but Intel honours it only with an invoice from an authorised reseller, so ask for that first. The payment is an unprotected bank transfer, and GLS is an estimate.
- **The Hagen bundle (U800-4):** the only build here with DDR4-3200 (+33% memory bandwidth for FDTD), and the only one that needs neither the €105.70 RAM kit nor the Graz 13900K. Its D3HP board has a smaller power circuit (4+1+1 phases), so keep the CPU at 100–125 W. The Noctua NH-U14S is 165 mm tall, so check your case. The 128 GB SSD is too small for the VMs; add one later.
- **Smart plug:** a TP-Link Tapo P110 ([willhaben 1404571179](https://www.willhaben.at/iad/object?adId=1404571179), €9 + €2.49 Poststation + €0.99 fee = €12.48) lets you power-cycle the server from Singapore. It has a Schuko plug, so check it fits Moroccan sockets (types C/E).

## What could go wrong

- **One RAM kit carries almost every build.** The 64 GB kit at €105.70 (willhaben 1085665164, posted 10 Oct) is in every build except U400-3 and U800-4. The next 64 GB kit costs €250 + delivery. If it sells:
  - €400 becomes U400-3 (Pfunds PC, 32 GB);
  - €600 has no 64 GB build (the 13900K with 32 GB is the compromise);
  - €800 becomes U800-4 (Hagen bundle).
- **Used Raptor Lake CPUs (13900K, 13700KF, 13900KS).** They can degrade, and there is no Intel warranty for a second owner. Before the CPU goes in, flash the DS3H's newest BIOS (**F25**, microcode 0x137; anything from F21 has the 0x12F fix) with the Q-Flash Plus button, which needs no CPU. Then set PL1 = PL2 = 125 W (100–110 W in a Moroccan summer).
- **willhaben's 48-hour claim window.** A problem must be reported within 48 h. Buy everything on the same day (the RAM kit first, because it's scarce), so the CPU and RAM arrive together and can be tested at once: memtest86 (one pass), a stress test (OCCT or y-cruncher), Intel's Processor Diagnostic Tool and a check for WHEA errors. When the 48 h starts at a Poststation is not shown; ask willhaben support.
- **No remote console.** B760 boards have no IPMI, so a hang needs someone in Morocco to press the button. In the BIOS set *AC BACK* to *Always On*, enable Proxmox's hardware watchdog (iTCO_wdt), reach the server only through a VPN, and use the smart plug for hard resets.
- **Flight and climate.** Take the cooler off the board, and carry the CPU, RAM, SSD and drives in padded hand luggage. Buy a UPS in Morocco. Moroccan customs rules for used parts were not checked.

## What changed since the builds I posted in chat

- **€400:** the i5-13400 build now fits, at €390.36–391.58, with a cheaper SSD (SK hynix BC501) and a shipped PSU (Corsair VS350). The 3900X build is gone (its board is reserved).
- **€600:** the pick is now the 13700KF build with a matched P300 pair, because the 13900K-with-mirror build has only €1 to spare. The Budapest 14700K was dropped: Intel's warranty does not pass to a second owner (*"This Limited Warranty is not transferrable to subsequent purchasers"*), and its shop warranty would have to be claimed in Hungary.
- **€800:** U800-1 is unchanged at €744.17–746.99. The new 13900KS from Hungary is the warranty option.
- **The Graz 13900K comes with its original box** (BX8071513900K), which I had missed. There is still no receipt.

## Files

- **[upfront_builds.csv](upfront_builds.csv):** every line of every build: price, delivery used, fee at 4.5% and 5%, seller, location, posting date, condition and link.

