![GitHub repo size](https://img.shields.io/github/repo-size/kelu124/lit3rick?style=plastic)
![GitHub language count](https://img.shields.io/github/languages/count/kelu124/lit3rick?style=plastic)
![GitHub top language](https://img.shields.io/github/languages/top/kelu124/lit3rick?style=plastic)
![GitHub last commit](https://img.shields.io/github/last-commit/kelu124/lit3rick?color=red&style=plastic)
[![Previous iteration](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.5792245-blue.svg)](https://zenodo.org/record/5792245#.YhvC_oTMJuQ)

[![Slack](https://badgen.net/badge/icon/slack?icon=slack&label)](https://join.slack.com/t/usdevkit/shared_invite/zt-2g501obl-z53YHyGOOMZjeCXuXzjZow)
[![made-with-Markdown](https://img.shields.io/badge/Made%20with-Markdown-1f425f.svg)](http://commonmark.org)

[![Patreon](https://img.shields.io/badge/patreon-donate-orange.svg)](https://www.patreon.com/kelu124) 
[![Kofi](https://badgen.net/badge/icon/kofi?icon=kofi&label)](https://ko-fi.com/G2G81MT0G)



# the up5k lit3rick open hardware ultrasound pulse echo board, with -28dB to 92dB gain

### OSHWA certified ! 

[https://certification.oshwa.org/fr000016.html](https://certification.oshwa.org/fr000016.html)

## Presentation of the hardware

* Lattice: up5k. Onboard RAM for 64k points saves. (128kB onboard RAM)
* Onboard flash 
* Pulser : HV7361GA-G: 
  * Can manage +-100V pulses. Onboard is 5V pulse.
  * Integrated circuit protection from HV
* Time gain compensation : [AD8332](altium/ad8332.md) using both channels, chained
  * HI setting: -4dB to __92dB__ amp
  * LO setting: -28dB to 68dB amp
* ADC: 10bits, up to 64Msps here. Test in progress for 80MHz acqs. 

* Previous iteration: [documentation released: 10.5281/zenodo.5792245](https://zenodo.org/record/5792245#.YhvClITMJuQ)  

* [Schematics](/altium/OUTPUT/Schematics/ice40_schematic.PDF)

[![](build/schematics.png)](/altium/OUTPUT/Schematics/ice40_schematic.PDF)

# Pics

## Design 

![](/bot.png)

![](/top.png)

## Prod

![](build/imagelit3_32.png)

## Python user code

* Principles are [here](/lit3-32/icestudio/Readme.md)
* Python code is [here](/icestudio/python/python.py)

## Verilog: using icestudio (work in progress)

![](/icestudio/icestudio_screenshot.png)

.. and a list of binaries. `823f03fdc4bc9354f3f7d20d9fca6d58` is the latest stable one.

```
823f03fdc4bc9354f3f7d20d9fca6d58  ./20230114_GainTests/bins/working.bin
e33742aa40016c3d32f804f4f5a2916f  ./20230114_GainTests/bins/pll_test_impl_1.bin
823f03fdc4bc9354f3f7d20d9fca6d58  ./20230114_GainTests/bins/hardware.bin
e3ddac9e455002339cf0d9cd9f03672c  ./program/blink.bin
823f03fdc4bc9354f3f7d20d9fca6d58  ./icestudio/lit3/ice-build/lit3bin/hardware.bin
70a0563b9e889dcdd5ab43a0825b8bfc  ./icestudio/old/corePLL/ice-build/corePLL/hardware.bin
823f03fdc4bc9354f3f7d20d9fca6d58  ./example/bins/working.bin
e33742aa40016c3d32f804f4f5a2916f  ./example/bins/pll_test_impl_1.bin
823f03fdc4bc9354f3f7d20d9fca6d58  ./example/bins/hardware.bin
```

# Outputs

Below are echoes from a 5V pulse, gain at 350/1000, HILO being low.

![](icestudio/G350_HL0_5V.jpg)

# License

This work is based on two previous TAPR projects, [the echOmods project](https://github.com/kelu124/echomods/), and the [un0rick project](https://github.com/kelu124/un0rick) - its boards are open hardware and software, developped with open-source elements as much as possible.

Copyright Kelu124 (kelu124@gmail.com) 2021.

* The hardware is licensed under TAPR Open Hardware License (www.tapr.org/OHL)
* The software components are free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.
* The documentation is licensed under a [Creative Commons Attribution-ShareAlike 3.0 Unported License](http://creativecommons.org/licenses/by-sa/3.0/).

## Disclaimer

This project is distributed WITHOUT ANY EXPRESS OR IMPLIED WARRANTY, INCLUDING OF MERCHANTABILITY, SATISFACTORY QUALITY AND FITNESS FOR A PARTICULAR PURPOSE. 

