# Home server shortlist: ready-built, worth the money

*10 Oct 2026. Ready-built machines you can get in Austria: willhaben with a parcel that fits, a pickup in Villach or Klagenfurt, or a pickup in Vienna on a weekend trip. Nothing has been bought and no seller has been contacted.*

Your use: Proxmox, CST and other FDTD/FEM solvers, Windows VMs and a small NAS mirror. The box runs 24/7 in Morocco, so every watt at idle costs about €0.92–1.26 a year. The CPU targets are about 30,000 multi-core and 3,400 single-core (PassMark).

## The list

| # | Build | You pay | CPU (multi / single) | RAM | Idle (est.) | Upfront + 4 years of power | What you do |
|---|---|---|---|---|---|---|---|
| **1** | **Wien Ryzen 9 5900X tower, 64 GB** + GT 1030 | **€835** at the asking price, about €755 if you get it to €720 | 38,887 / 3,465 ✔ | **64 GB DDR4-3200** ✔ | 45–55 W | €1,001–1,112 (€921–1,032 negotiated) | Plug in the display card |
| **2** | **Gigabyte X470 Aorus Ultra tower + Ryzen 9 5900X + 64 GB**, three Vienna sellers | **≈€653** (+€40 for a mirror) | 38,887 / 3,465 ✔ | **64 GB DDR4-2400** ✔ | 45–55 W | €819–931 | CPU swap and BIOS update |
| **3** | **Geekom A7 mini PC**, Vienna | **€615** pickup (€651–656 shipped) | 29,718 / 3,845 (≈ target) | 32 GB DDR5 | **5–9 W** | **€633–660** | Nothing |
| **4** | **TAROX i5-14400 business tower + 2×16 GB**, shipped | **€606–609** | 25,010 / 3,741 (≈20–22k in long runs) | **64 GB DDR4** ✔ | 15–20 W | €664–710 | Plug in 2 RAM sticks |
| **5** | **HP Pro Tower 400 G9, i7-12700**, Vienna pickup | **€370** | 29,755 / 3,840 (≈22–25k in long runs) | 32 GB DDR4 | 10–15 W | **€407–446** | Nothing |

✔ = meets the target. "Upfront + 4 years" uses €3.68–5.04 per idle watt over 4 years.

### 1. Wien Ryzen 9 5900X tower: best all-round
- **Listing:** [willhaben 1798028937](https://www.willhaben.at/iad/object?adId=1798028937), €800, *"Preis noch verhandelbar"*. Private seller, 1220 Wien-Donaustadt, posted 28 Sep.
- **What's in it:** MSI X570 Gaming Pro Carbon WiFi, 64 GB Kingston FURY (probably 2×32, so 2 slots free), 1 TB M.2. From the photos: a be quiet! Pure Base 500 case and a be quiet! Dark Rock Pro cooler, so it should be very quiet.
- **No graphics card is included.** The 5900X has no built-in graphics, so add the [ASUS GT 1030](https://www.willhaben.at/iad/object?adId=2056181722) (€35, Wien 1180) and bring it to the pickup to test the PC.
- **Mirror:** 2× 2 TB [Seagate](https://www.willhaben.at/iad/object?adId=1590741658) for €40, or 2× near-new [IronWolf Pro](https://www.willhaben.at/iad/object?adId=1759125813) for €150, both in Wien 1170.
- **Ask the seller:** PSU model, whether the RAM is 2×32, the SSD model, and whether you can test it at pickup.

### 2. X470 Aorus Ultra + 5900X + 64 GB: the same CPU and RAM for about €100–180 less
- **The parts:**
  - [PC](https://www.willhaben.at/iad/object?adId=811188315), €325, Wien 1080: be quiet! Pure Power 11 Gold PSU, Scythe Mugen 5 cooler, Pure Base 600 case, GTX 1050 Ti, Ryzen 5 2600.
  - [Ryzen 9 5900X](https://www.willhaben.at/iad/object?adId=1353259458), €220, Wien 1020.
  - [64 GB DDR4-2400 ECC UDIMM kit](https://www.willhaben.at/iad/object?adId=1085665164), €108.49 delivered. The seller ships only, so it comes by post.
- **The work:** ask the PC seller to update the BIOS for Ryzen 5000 (F60 or newer), then swap the CPU and fit the 4 RAM sticks. It's the most hands-on build on this list.
- **Getting it home:** both 5900X builds can be collected on the same Vienna trip.

### 3. Geekom A7 mini PC: the power and mini-rack pick
- **Listing:** [willhaben 1641122438](https://www.willhaben.at/iad/kaufen-und-verkaufen/d/geekom-a7-mini-pc-amd-ryzen-9-7940hs-8-kerne-16-threads-bis-zu-5-2-ghz-32-gb-ddr5-2tb-ssd-mini-computer-amd-radeon-780m-bt5-2-wi-fi-6e-8k-1641122438/), €615, Wien 1020.
- **What's in it:** Ryzen 9 7940HS, 32 GB DDR5-5600, 2 TB NVMe, 11 × 11 cm. It sits in a 10-inch rack, idles at about 5–9 W and is quiet at idle.
- **Limits:** 32 GB is the practical ceiling (64 GB costs €500+), there's no room for a proper mirror, and there's no remote console.

### 4. TAROX i5-14400 + 2×16 GB: frugal 64 GB with no travel
- **The parts:** [PC](https://www.willhaben.at/iad/object?adId=2030927090) €470 (Gleisdorf, shipped) + [2×16 GB](https://www.willhaben.at/iad/object?adId=2051940506) €100.
- **Limits:** the CPU is below target, so CST and FDTD runs take longer. Confirm 4 RAM slots before buying the RAM.

### 5. HP Pro Tower 400 G9: the budget pick
- **Listing:** [willhaben 1847590599](https://www.willhaben.at/iad/object?adId=1847590599), €370, Wien-Floridsdorf, pickup only.
- **What's in it:** i7-12700, 32 GB DDR4, 512 GB NVMe, built-in graphics.
- **Limits:**
  - HP's small cooler holds long runs to about 22–25k multi-core.
  - Only 2 RAM slots, so 64 GB means a 2×32 kit (about €350).
  - One drive bay.

## Not worth it (and why)
- **Lenovo P360, i9-12900K (Stuttgart, €525):** sold, the seller confirmed on 10 Oct.
- **Acer Predator Orion 3000 (Villach, €800):** 32 GB of DDR5 (64 GB costs €600+), needs its RTX 4060, and idles at 35–50 W. Option 1 gives 64 GB for about the same money.
- **New office and workstation towers from shops:** €840–1,270 for 16–64 GB. Option 1 or 2 is better value.
- **Pfunds i5-12400 PC (€397 shipped):** beaten by the Vienna HP Pro Tower (option 5) if you go to Vienna.
- **Short-depth rack servers:** the affordable ones have old, slow CPUs.

## Before buying any of them
- **BIOS settings:** set it to power on after a power cut, and cap power for summer. On the 5900X builds, Eco Mode (65 W) is an option.
- **Remote resets:** add a [smart plug](https://www.willhaben.at/iad/object?adId=1404571179) (€12.48) to power-cycle it from Singapore.
- **The flight:** take out the tower cooler and graphics card, and carry the drives in your hand luggage.
- **Cash pickups have no buyer protection:** check that it boots, that the RAM shows in the BIOS, and that it survives about 10 minutes of a stress test before paying.
