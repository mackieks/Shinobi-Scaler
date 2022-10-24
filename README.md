# Shinobi Scaler
Shinobi is a reimagined, miniaturized GBS8200. Like the original GBS8200, it can convert 240p and 480i RGBs to 480p/720p/1080p VGA, making it perfect for connecting retro video game consoles to modern LCDs.

<img src='images/shinobi_new.png' width='350'> <img src='images/untitled.png' width='350'> 

## Features
- [x] TV5725 Scaler IC 

## Ordering
Recommended fabrication specs:
- 1mm-thick 2-layer PCB
- ENIG finish
- Solderpaste stencil recommended

**Note:** There are multiple revisions of the ESP-06 (ESP8266 module). Only the most recent revision is compatible with Shinobi. Make sure your ESP-06 has three "Wi-Fi lines" inside the A.I. Thinker logo circle, and that three of the four corner pads are *not* connected to GND. 

/placeholder for esp-06 images

I maintain a [Mouser project](https://www.mouser.com/ProjectManager/ProjectDetail.aspx?AccessID=a0a4651c6a) containing most of the BOM. You will still need to source a GBS8200, ESP-06, and CH340C elsewhere. I get my ESP-06s from [AliExpress](https://www.aliexpress.us/item/2251832641491582.html) and harvest CH340Cs from cheap Wemos D1 Mini dev boards.

## Assembly
