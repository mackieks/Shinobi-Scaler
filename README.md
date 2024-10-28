<picture> <source media="(prefers-color-scheme: dark)" srcset="https://github.com/mackieks/Shinobi-Scaler/blob/shinobi-2/images/logo_light.png"> <img src="https://github.com/mackieks/Shinobi-Scaler/blob/shinobi-2/images/logo_dark.png" height="100"> </picture> 

Shinobi Scaler 2 is a reimagined, miniaturized GBS8200 for portablizers. Like the original GBS8200, it can convert 240p and 480i RGBs to 480p/720p/960p/1080p VGA, making it perfect for connecting retro video game consoles to modern LCDs.

<img src='images/shinobi_new.png' width='350'> <img src='images/untitled.png' width='350'> 

## Features
- [x] 50 x 47mm 4-layer PCB (designed in KiCAD 8.99)
- [x] Compatible with [rama's GBS-Control](https://github.com/ramapcsx2/gbs-control)
- [x] 240p/480i RGBs input; 480p/720p/960p/1080p RGBHV/VGA/YPbPr output
- [x] 0.1" PTHs for power and IO (can be mounted with pin headers on a carrier PCB)
- [x] TV5725 scaler IC and 64Mbit SDRAM from GBS8200
- [x] Integrated ESP8285 with Wi-Fi chip antenna
- [x] Integrated CH343P for programming
- [x] Integrated Si5351A clock generator
- [x] Power from any 2.5V - 5.5V source (including 1S li-ion)
- [x] Draws 1.2W, half the power of Shinobi 1!
<img src='images/power.PNG' width='165'>


<img src='images/schematic.png' width='1000'>

## Gallery
Shinobi 2 PCB

<img src='images/top.jpg' width='350'> <img src='images/bottom.jpg' width='350'> 

1Chip SNES RGBs upscaled to 640x480 VGA, displayed on ZJ050NA-08C LCD

<img src='images/yoshi.jpg' width='400'> <img src='images/sm.jpg' width='400'>

Shinobi 2 testing and power measurement

<img src='images/test2.jpg' width='400'>

## Ordering
Recommended fabrication specs:
- 1mm-thick 4-layer PCB
- ENIG finish
- Solderpaste stencil for top side highly recommended

I maintain a [Mouser project](https://www.mouser.com/ProjectManager/ProjectDetail.aspx?AccessID=5e7ab48fda) with most of the BOM. 

You will still need to source a TV5725 and CH343P elsewhere. Cheap GBS8200s are available from AliExpress, eBay, DHGate, and Amazon if you'd like to harvest the TV5725 and SDRAM from one. [TV5725s](https://www.aliexpress.us/item/3256807282171835.html) are available from AliExpress. CH343Ps are sold on [LCSC](https://www.lcsc.com/product-detail/USB-ICs_WCH-Jiangsu-Qin-Heng-CH343P_C2846043.html) and [AliExpress](https://www.aliexpress.us/item/3256806693647102.html).

## Assembly
A ``bom.html`` file is included to facilitate assembly. Open it in your web browser and enjoy.

For a guide on how to assemble PCBs at home using a solderpaste stencil and hot plate, please see [this document from the Thundervolt repo.](https://github.com/mackieks/thundervolt/blob/main/hardware/ASSEMBLY.md)

## Programming
- Install the [CH343P driver](https://www.wch-ic.com/downloads/CH343SER_EXE.html).
- Plug USB-C into Shinobi 2
- Verify COM port (or your platform's equivalent) is enumerating
- Open GBS-Control release of your choice in Arduino IDE (these steps assume you have already installed requisite libraries, etc.)
- Set up Tools menu as shown, select CH343P port under Port menu, then program
<img src='images/program.png' height='300'>

- When programming is complete, unplug Shinobi 2 and power it back up to access GBS-Control Wi-Fi AP
- After setting up your presets, you can edit line 7211 of the Arduino sketch as shown, then recompile & reupload to totally disable Wi-Fi. This saves ~150mW
<img src='images/disable.png' width='300'>

## To-do
- [ ] 

## License
[Solderpad Hardware License v2.1](https://solderpad.org/licenses/SHL-2.1/)
