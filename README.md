# Shinobi Scaler 
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="images/logo_light.png">
  <source media="(prefers-color-scheme: light)" srcset="images/logo_dark.png">
</picture>
Shinobi is a reimagined, miniaturized GBS8200. Like the original GBS8200, it can convert 240p and 480i RGBs to 480p/720p/1080p VGA, making it perfect for connecting retro video game consoles to modern LCDs.

<img src='images/shinobi_new.png' width='350'> <img src='images/untitled.png' width='350'> 

## Features
- [x] 47 x 57mm PCB
- [x] Compatible with [rama's GBS-Control](https://github.com/ramapcsx2/gbs-control)
- [x] TV5725 Scaler IC and 64 Mbit SDRAM from GBS8200
- [x] Integrated ESP8266 with PCB antenna
- [x] Integrated CH340C USB-Serial for programming
- [x] Integrated Si5351A clock generator
- [x] Power from 3.3V directly, or supply 4-15V to onboard high-current 3.3V regulator

<img src='images/schematic.png' width='700'>

## Ordering
Recommended fabrication specs:
- 1mm-thick 2-layer PCB
- ENIG finish
- Solderpaste stencil recommended

**Note:** There are multiple revisions of the ESP-06 (ESP8266 module). Only the most recent revision is compatible with Shinobi. Make sure your ESP-06 has three "Wi-Fi lines" inside the A.I. Thinker logo circle, and that three of the four corner pads are *not* connected to GND. 

<img src='images/esp06_top.png' width='240'> <img src='images/esp06_bottom.png' width='250'> 

I maintain a [Mouser project](https://www.mouser.com/ProjectManager/ProjectDetail.aspx?AccessID=a0a4651c6a) containing most of the BOM. You will still need to source a GBS8200, ESP-06, and CH340C elsewhere. I get my [ESP-06s](https://www.aliexpress.us/item/2251832641491582.html) and [CH340Cs](https://www.aliexpress.com/wholesale?&SearchText=ch340c) from AliExpress.

## Assembly
