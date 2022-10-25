# Shinobi Scaler <img src="images/logo_dark.png#gh-light-mode-only" height="30"/> <img src="images/logo_light.png#gh-dark-mode-only" height="30"/>
Shinobi is a reimagined, miniaturized GBS8200 for portablizers. Like the original GBS8200, it can convert 240p and 480i RGBs to 480p/720p/1080p VGA, making it perfect for connecting retro video game consoles to modern LCDs.

<img src='images/shinobi_new.png' width='350'> <img src='images/untitled.png' width='350'> 

## Features
- [x] 47 x 57mm PCB
- [x] Compatible with [rama's GBS-Control](https://github.com/ramapcsx2/gbs-control)
- [x] TV5725 scaler IC and 64Mbit SDRAM from GBS8200
- [x] Integrated ESP8266 with PCB antenna
- [x] Integrated CH340C USB-Serial for programming
- [x] Integrated Si5351A clock generator
- [x] Power from 3.3V directly, or supply 4-15V to onboard high-current 3.3V regulator

<img src='images/schematic.png' width='1000'>

## Ordering
Recommended fabrication specs:
- 1mm-thick 2-layer PCB
- ENIG finish
- Solderpaste stencil for top side highly recommended

**Note:** There are multiple revisions of the ESP-06 (ESP8266 module). Only the most recent revision is compatible with Shinobi. Make sure your ESP-06 has three "Wi-Fi lines" inside the A.I. Thinker logo circle, and that three of the four corner pads are *not* connected to GND. 

<img src='images/esp06_top.png' width='240'> <img src='images/esp06_bottom.png' width='250'> 

I maintain a [Mouser project](https://www.mouser.com/ProjectManager/ProjectDetail.aspx?AccessID=a0a4651c6a) with most of the BOM. You will still need to source a GBS8200, ESP-06, and CH340C elsewhere. GBS8200s are available at AliExpress, eBay, DHGate, Amazon... I get my [ESP-06s](https://www.aliexpress.us/item/2251832641491582.html) and [CH340Cs](https://www.aliexpress.com/wholesale?&SearchText=ch340c) from AliExpress.

## Assembly
You will need to harvest the TV5725 scaler IC and 64Mbit SDRAM from a working GBS8200 PCB. I also recommend reusing the three 0603 10uH inductors from the VGA output filters (L4, L5, L6 on the GBS8200; L2, L3, L4 on Shinobi). 0402 10uHs are expensive and the original 0603 parts will solder onto Shinobi's footprints just fine.

<img src='images/gbs8200_top_noconn.png' width='500'>

There is an 0805 zero-ohm resistor (R19) in series with the output of the onboard 3.3V regulator. If you intend to power Shinobi from an external 3.3V supply, you can omit this resistor as well as U7 (TPS621351) and its supporting passives. If you choose to remove the zero-ohm and/or U7, the board will need to be powered with an external 3.3V supply during programming.

## Programming
- Install [CH340 drivers](http://www.wch-ic.com/downloads/CH341SER_ZIP.html)
- Bridge the `prg` jumper with solder.
- Plug USB-C into Shinobi
- Verify COM port (or your platform's equivalent) is enumerating
- Open GBS Control release of your choice in Arduino IDE (these steps assume you have already installed requisite libraries, etc.)
- Set up Tools menu as shown, select Shinobi port under Port menu, then program
<img src='images/program.png' height='300'>
- When programming is complete, unplug Shinobi, remove `prg` solder bridge, and power back up to access GBS Control Wi-Fi AP
