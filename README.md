# TK44 Info Page

![Title Image](https://i.imgur.com/ZL7ijve.png)

**TK44 - is a wireless unibody 40% keyboard with features like:**

* Powered by [ZMK Firmware](https://zmk.dev/docs/)
* Based on [Holyiot-18010](http://www.holyiot.com/tp/2019042516322180424.pdf) module
* Hot swappable PCB
* Support 5 pins MX switches
* Li-ion battery
* Hardware power switch
* USB Type-C
* Layout contains full Cyrillic layout (for now used [Jian's layout](http://www.keyboard-layout-editor.com/#/gists/4b6c2af67148f58ddd6c6b2976c4370f))
* 44 or 42 keys layout

![Dummy Layout](https://i.imgur.com/SZQ4iCk.png)

There is "dummy" layout, just for reference

## Photos

![Main Photo](https://i.imgur.com/fLbH7DQ.jpg)

### See more on [Imgur](https://imgur.com/a/DaCdFm3)

# Build Guide

Please, use [**iBom file**](https://github.com/Ladniy/TK44-info/releases/download/v1.0/ibom.html) for the correct placement of components on the PCB

![iBom Image](https://i.imgur.com/vGK9sAb.png)

## BOM

| Name               | Qty | Package  | Value       | Aliexpress                                                      |
| ------------------ | --- | -------- | ----------- | --------------------------------------------------------------- |
| Holyiot            | 1   | SMD      | YJ-18010    | [6.80$ / 1](https://aliexpress.com/item/32868365660.html)       |
| Diode              | 45  | SOD-123  | 1N5819      | [0.99$ / 100](https://aliexpress.com/item/32849879904.html)     |
| Resistor           | 1   | SMD 0603 | 2M          | [0.48$ / 100](https://aliexpress.com/item/32847135098.html)     |
| Resistor           | 1   | SMD 0603 | 820k        | [0.48$ / 100](https://aliexpress.com/item/32847135098.html)     |
| Resistor           | 1   | SMD 0603 | 3.3k        | [0.48$ / 100](https://aliexpress.com/item/32847135098.html)     |
| Resistor           | 1   | SMD 0603 | 100k        | [0.48$ / 100](https://aliexpress.com/item/32847135098.html)     |
| Resistor           | 2   | SMD 0603 | 5.1k        | [0.48$ / 100](https://aliexpress.com/item/32847135098.html)     |
| Resistor           | 2   | SMD 0603 | 1k          | [0.48$ / 100](https://aliexpress.com/item/32847135098.html)     |
| LED's              | 1   | SMD 0603 | Red & Blue  | [0.88$ / 100](https://aliexpress.com/item/32798686869.html)     |
| Charger            | 1   | SOT-23-5 | MCP73831    | [0.98$ / 10](https://aliexpress.com/item/32714249253.html)      |
| P-MOSFET           | 1   | SOT-23   | AO3407      | [1.15$ / 50](https://aliexpress.com/item/32491247912.html)      |
| VCC Regulator      | 1   | SOT-23-5 | AP2112K     | [0.82$ / 10](https://aliexpress.com/item/32884059737.html)      |
| USB Connector      | 1   | SMD      | 1.6mm       | [1.17$ / 10](https://aliexpress.com/item/32998900371.html)      |
| Power Switch       | 1   | SMD      | MSK12C02    | [1.39$ / 50](https://aliexpress.com/item/32856542440.html)      |
| Reset Switch       | 1   | SMD      | 5.2x5.2x1.5 | [0.64$ / 50](https://aliexpress.com/item/32989610390.html)      |
| Hotswap Sockets    | 44  | SMD      | MX          | [3.40$ / 30](https://aliexpress.com/item/1005003166749340.html) |
| Battery Connector  | 1   | JST 1.25 | 2 Pin       | [1.64$ / 50](https://aliexpress.com/item/10000064127272.html)   |
| JST Male Wire      | 1   | JST 1.25 | 2 Pin       | [0.70$ / 20](https://aliexpress.com/item/1005002957075278.html)  |
| Battery            | 1   | 502035   | 300mAh      | [3.65$ / 1](https://aliexpress.comitem/1005003258617053.html)   |


* Holyiot module have several verison:
  * [Unshielded version](https://aliexpress.ru/item/32868365660.html)
  * [Shielded version](https://aliexpress.com/item/32868002366.html)
* Instead of AP2112K VCC Regulator you can use [XC6220](https://aliexpress.ru/item/4000271612572.html). It's more expensive, but have leaks around 8uA vs 55uA at AP2112K. Using XC6220 will help save battery charge.
* Power switch also name as a PCM12, thats can help you to find them in other places
* In current BOM i placed link for new colored Kailh **MX** hotswap sockets, they more cheaper for now moment, but you can use any Kailh **MX** footprint friendly sockets
* For Battery Connector choose "Straight needle"
* For JST Male Wire choose "red black" and 40mm, this will be enought
* You can choose any battery, that fits the size 5x20x35mm (0.19x0.79x1.38")

## Case Build

FR-4 case, as well as the PCB, have cutoffs for breaking off pinky-key.

| Part            | Size        | Length | Qty | Aliexpress                                                      |
| --------------- | ----------- | ------ | --- | --------------------------------------------------------------- |
| Standoffs       | M2          | 8mm    | 8   | [2.46$ / 10](https://aliexpress.com/item/1005001696530309.html) |
| Screws          | M2          | 6mm    | 16  | [1.14$ / 25](https://aliexpress.com/item/1005003106313122.html) |

* Additional:
  * Silicone Bumpers: [black](https://aliexpress.com/item/32912066603.html) or [clear](https://aliexpress.com/item/32680543746.html)

# Firmware

## Flashing controller

For this operation you need J-Link clone programmer, like this:

<img src="https://i.imgur.com/nZcdqkH.jpg"/>

**[Aliexpress 5.49$](https://aliexpress.com/item/32669702891.html)**

## Unlocking controller

First of all download and install [SEGGER J-Link 6.70b](https://www.segger.com/downloads/jlink/#J-LinkSoftwareAndDocumentationPack)

And download [J-Flash project](https://github.com/Ladniy/TK44-info/releases/download/v1.0/tk44_project.jflash)

<img src="https://i.imgur.com/0X5wmET.png"/>

* Connect programmer's pins (VCC, GND, SWC, SWD) to PCB's pins (same pins, marked by silkscreen).
  * You can connect only SWC and SWD pins, in this case, power PCB via USB-C **(please, make sure that battery not installed and power switch in OFF positon)**.
* Connect programmer to PC via USB cable.
* Open JFlash.
* Choose **Open recent project** and choose project file, that you download earlier.
* Click **Start J-Flash**

**After that:**

* Connect to controller: Target --> Connect (**make sure that connect between programmer and PCB is stable, hold wires tight in PCB!**)
* After succesfull connect: Target --> Disconnect

## Bootloader

Download [TK44 bootlader](https://github.com/Ladniy/TK44-info/releases/download/v1.0/tk44_bootloader-0.6.3-49-ge18dabd-dirty_s140_6.1.1.hex)

Move bootlader hex file into root directory (as example: C: disk for windows)

<img src="https://i.imgur.com/kco8mwP.png"/>

* Open JFlashLite, select NRF52840_XXAA if it doesn't at program start.
* Select bootloader and press Program Device, wait for flashing.

## Flashing Firmware

* After flashing controller you need to download ZMK firmware file:
  * [ZMK firmware](https://github.com/Ladniy/TK44-info/releases/download/v1.0/tk44-zmk.uf2)
  * [Or build by yourself](https://github.com/krikun98/zmk-config/tree/tk44)
* Move file from download folder to a directory of your choice for easy access
* Connect PCB through USB Type-C
* Move tk44-zmk.uf2 file into opened explorer window (just like moving files to a USB flash drive)

**After this you can freely connect your TK44 keyboard to PC!**

## References

[Joric's flashing instuction (a lot of variants)](https://github.com/joric/nrfmicro/wiki/Bootloader)

[luantty2 flashing instruction](https://github.com/luantty2/nRF52840-instruction#%E6%A8%A1%E5%9D%97%E7%83%A7%E5%BD%95%E5%9B%BA%E4%BB%B6%E5%89%8D%E7%9A%84%E5%87%86%E5%A4%87%E5%B7%A5%E4%BD%9C)
