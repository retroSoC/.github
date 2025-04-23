## Hi, retroSoC 👋

retroSoC contains a bundle of IPs which aim to improve development experience of processor and SoC design. Now it mainly focus on frontend and verification field. We hope it can be integrated by other components to build a common workflow for agile hardware development from frontend to backend one day.

## Motivation
<!-- | Type | List |
| :---: | :---: |
| System     | uart, spi-FLASH, amba bus, dma, trace, clint, plic, jtag, rcu, pmu, core, archinfo |
| Peripheral | timer, rtc, wdg, pwm, gpio, ps2, spi, qspi, octspi, i2c, i2s, sdio |
| Memory     | sram, sdram, psram, nand-FLASH, ddr1, ddr2, ddr3, chiplink |
| Graphics   | vga, hdmi, lcd, mipi-dsi, video-engine, gpu |
| Communication | usb, ethernet, pcie |
| Application | crc, aes, sha, rsa, rng, foc, cnn, isp | -->

| retroSoC | information |
| :---:    | :---      |
| TINY | **A Minimum RV32E Educational MCU(<10K instances)** |
| | CORE(**ongoing):** OSOC CORE(pre-learned, SCP, Single Cylcle Processor) |
| | BUS: NATIVE bridge(NATIVE mux, NATIVE2APB), single power/clock domain, 16-32MHz(SMIC110, IHP/SKY130) |
| | SYSTEM IP: 1xARCHINFO |
| | MEMORY IP: 128KB OCM, 16MB SPI NOR FLASH, 512KB/1MB QPI FRAM, 8/16MB QPI PSRAM |
| | INTERFACE IP: 2xUART, 4xGPIO, 2xTIMER, 1xI2C, 1xQSPI |
| | PACKAGE: QFN48 |
| | DEMO: smart band |
| MINI | **A Lightweight RV32I/EMC MCU(10K~50K instances)** |
| | CORE: PicoRV32, KianV(RV32E, tt07), **ongoing:** DarkRISCV, SERV, tinyQV, FemtoRV32, TinySys, VexRiscv |
| | BUS: NATIVE bridge(NATIVE mux, NATIVE2APB), single power/clock domain, 24-108MHz(SMIC110, IHP/SKY130) |
| | SYSTEM IP: 1xARCHINFO, 1xRCU |
| | MEMORY IP: 128KB OCM, 16MB SPI NOR FLASH, 512KB/1MB QPI FRAM, 8/16MB QPI PSRAM |
| | INTERFACE IP: 2xUART, 16xGPIO, 2xTIMER, 1xRNG, 4xPWM, 1xWDG, 1xPS2, 1xI2C, 1xQSPI, 1xSDIO |
| | MULTIMEDIA IP: 1xI2S |
| | PACKAGE: QFN48/64 |
| | DEMO: smart band, micro quadcopter |
| STD | **A Complete RV32IMAC MCU(20K~80K instances)** |
| | CORE(**ongoing):** OSOC Core(RV32E, B-phase), Hummingbirdv2 E203, CV32E40P, ibex, Harzard3, SCR1, RV12(RVLogic), Glacial, VeeR EH1, VexRiscv |
| | BUS: AHB/AXI bridge(AHB/AXI splitter, AHB/AXI2APB), single power, multi clock domain, 72-196MHz(SMIC110, IHP/SKY130) |
| | SYSTEM IP: 1xARCHINFO, 1xRCU, 1XPLIC |
| | MEMORY IP: 128KB OCM, 16MB SPI NOR FLASH, 512KB/1MB QPI FRAM, 8/16MB QPI PSRAM, 32MB DDR OPI PSRAM |
| | INTERFACE IP: 2xUART, 16xGPIO, 2xTIMER, 1xRNG, 4xPWM, 1xPS2, 1xI2C, 1xQSPI, 1xSDIO |
| | MULTIMEDIA IP: 1xI2S, 1xVGA, 1xDVP, 1xDMA |
| | PACKAGE: QFN88 |
| | DEMO: game console |
| PRO | **A High-performance RV32/64GC SoC(60K~200K instances)** |
| | CORE(**ongoing):** OSOC Core(RV64G, A-phase), Nanhu-G(XiangShan), biriscv, CVA6, ‌VexRiscv, Rocket Chip, BOOM, RRV64, GreenRio |
| | BUS: AXI bridge(AXI splitter, AXI2APB), single power, multi clock domain, 72-196MHz(SMIC110, IHP/SKY130) |
| | SYSTEM IP: 1xARCHINFO, 1xRCU, 1XPLIC |
| | MEMORY IP: 128KB OCM, 16MB SPI NOR FLASH, 512KB/1MB QPI FRAM, 8/16MB QPI PSRAM, 32MB DDR OPI PSRAM |
| | INTERFACE IP: 2xUART, 32xGPIO, 4xTIMER, 1xRNG, 4xPWM, 1xPS2, 1xI2C, 2xQSPI, 1xSDIO |
| | MULTIMEDIA IP: 1xI2S, 1xVGA, 1xDVP, 1xDMA, 1x2D GRAPHIC ACCEL |
| | PACKAGE: QFP100 |
| | DEMO:  game console, single board computer |

IPs list and development state:

| clusterIP       | MILESTONE |
| :---:    | :---     |
| system | Common Component, Interrupt Controller, Reset&Clock Unit |
| [common](https://github.com/retroSoC/common) | <img src="https://img.shields.io/badge/SPC-done-green?style=flat-square"> <img src="https://img.shields.io/badge/RTF-done-green?style=flat-square"> <img src="https://img.shields.io/badge/SMT-done-green?style=flat-square"> <img src="https://img.shields.io/badge/UVV-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FUC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/COC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/SOI-done-green?style=flat-square"> <img src="https://img.shields.io/badge/FPE-done-green?style=flat-square"> <img src="https://img.shields.io/badge/TPT-no-wheat?style=flat-square"> |
| [archinfo](https://github.com/retroSoC/archinfo) | <img src="https://img.shields.io/badge/SPC-done-green?style=flat-square"> <img src="https://img.shields.io/badge/RTF-done-green?style=flat-square"> <img src="https://img.shields.io/badge/SMT-done-green?style=flat-square"> <img src="https://img.shields.io/badge/UVV-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FUC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/COC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/SOI-done-green?style=flat-square"> <img src="https://img.shields.io/badge/FPE-done-green?style=flat-square"> <img src="https://img.shields.io/badge/TPT-no-wheat?style=flat-square"> |
| [clint](https://github.com/retroSoC/clint) | <img src="https://img.shields.io/badge/SPC-done-green?style=flat-square"> <img src="https://img.shields.io/badge/RTF-done-green?style=flat-square"> <img src="https://img.shields.io/badge/SMT-done-green?style=flat-square"> <img src="https://img.shields.io/badge/UVV-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FUC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/COC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/SOI-done-green?style=flat-square"> <img src="https://img.shields.io/badge/FPE-done-green?style=flat-square"> <img src="https://img.shields.io/badge/TPT-no-wheat?style=flat-square"> |
| [plic](https://github.com/retroSoC/plic) | <img src="https://img.shields.io/badge/SPC-done-green?style=flat-square"> <img src="https://img.shields.io/badge/RTF-done-green?style=flat-square"> <img src="https://img.shields.io/badge/SMT-done-green?style=flat-square"> <img src="https://img.shields.io/badge/UVV-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FUC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/COC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/SOI-done-green?style=flat-square"> <img src="https://img.shields.io/badge/FPE-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/TPT-no-wheat?style=flat-square"> |
| [rcu](https://github.com/retroSoC/rcu) | <img src="https://img.shields.io/badge/SPC-done-green?style=flat-square"> <img src="https://img.shields.io/badge/RTF-done-green?style=flat-square"> <img src="https://img.shields.io/badge/SMT-done-green?style=flat-square"> <img src="https://img.shields.io/badge/UVV-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FUC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/COC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/SOI-done-green?style=flat-square"> <img src="https://img.shields.io/badge/FPE-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/TPT-no-wheat?style=flat-square"> |
| interface | Low-speed Peripherals |
| [gpio](https://github.com/retroSoC/gpio) | <img src="https://img.shields.io/badge/SPC-done-green?style=flat-square"> <img src="https://img.shields.io/badge/RTF-done-green?style=flat-square"> <img src="https://img.shields.io/badge/SMT-done-green?style=flat-square"> <img src="https://img.shields.io/badge/UVV-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FUC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/COC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/SOI-done-green?style=flat-square"> <img src="https://img.shields.io/badge/FPE-done-green?style=flat-square"> <img src="https://img.shields.io/badge/TPT-no-wheat?style=flat-square"> |
| [uart](https://github.com/retroSoC/uart) | <img src="https://img.shields.io/badge/SPC-done-green?style=flat-square"> <img src="https://img.shields.io/badge/RTF-done-green?style=flat-square"> <img src="https://img.shields.io/badge/SMT-done-green?style=flat-square"> <img src="https://img.shields.io/badge/UVV-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FUC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/COC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/SOI-done-green?style=flat-square"> <img src="https://img.shields.io/badge/FPE-done-green?style=flat-square"> <img src="https://img.shields.io/badge/TPT-no-wheat?style=flat-square">
| [ps2](https://github.com/retroSoC/ps2) | <img src="https://img.shields.io/badge/SPC-done-green?style=flat-square"> <img src="https://img.shields.io/badge/RTF-done-green?style=flat-square"> <img src="https://img.shields.io/badge/SMT-done-green?style=flat-square"> <img src="https://img.shields.io/badge/UVV-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FUC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/COC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/SOI-done-green?style=flat-square"> <img src="https://img.shields.io/badge/FPE-done-green?style=flat-square"> <img src="https://img.shields.io/badge/TPT-no-wheat?style=flat-square"> |
| [timer](https://github.com/retroSoC/timer) | <img src="https://img.shields.io/badge/SPC-done-green?style=flat-square"> <img src="https://img.shields.io/badge/RTF-done-green?style=flat-square"> <img src="https://img.shields.io/badge/SMT-done-green?style=flat-square"> <img src="https://img.shields.io/badge/UVV-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FUC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/COC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/SOI-done-green?style=flat-square"> <img src="https://img.shields.io/badge/FPE-done-green?style=flat-square"> <img src="https://img.shields.io/badge/TPT-no-wheat?style=flat-square"> |
| [pwm](https://github.com/retroSoC/pwm) | <img src="https://img.shields.io/badge/SPC-done-green?style=flat-square"> <img src="https://img.shields.io/badge/RTF-done-green?style=flat-square"> <img src="https://img.shields.io/badge/SMT-done-green?style=flat-square"> <img src="https://img.shields.io/badge/UVV-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FUC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/COC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/SOI-done-green?style=flat-square"> <img src="https://img.shields.io/badge/FPE-done-green?style=flat-square"> <img src="https://img.shields.io/badge/TPT-no-wheat?style=flat-square"> |
| [wdg](https://github.com/retroSoC/wdg) | <img src="https://img.shields.io/badge/SPC-done-green?style=flat-square"> <img src="https://img.shields.io/badge/RTF-done-green?style=flat-square"> <img src="https://img.shields.io/badge/SMT-done-green?style=flat-square"> <img src="https://img.shields.io/badge/UVV-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FUC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/COC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/SOI-done-green?style=flat-square"> <img src="https://img.shields.io/badge/FPE-done-green?style=flat-square"> <img src="https://img.shields.io/badge/TPT-no-wheat?style=flat-square"> |
| [rtc](https://github.com/retroSoC/rtc) | <img src="https://img.shields.io/badge/SPC-done-green?style=flat-square"> <img src="https://img.shields.io/badge/RTF-done-green?style=flat-square"> <img src="https://img.shields.io/badge/SMT-done-green?style=flat-square"> <img src="https://img.shields.io/badge/UVV-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FUC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/COC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/SOI-done-green?style=flat-square"> <img src="https://img.shields.io/badge/FPE-done-green?style=flat-square"> <img src="https://img.shields.io/badge/TPT-no-wheat?style=flat-square"> |
| [i2c](https://github.com/retroSoC/i2c) | <img src="https://img.shields.io/badge/SPC-done-green?style=flat-square"> <img src="https://img.shields.io/badge/RTF-done-green?style=flat-square"> <img src="https://img.shields.io/badge/SMT-done-green?style=flat-square"> <img src="https://img.shields.io/badge/UVV-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FUC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/COC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/SOI-done-green?style=flat-square"> <img src="https://img.shields.io/badge/FPE-done-green?style=flat-square"> <img src="https://img.shields.io/badge/TPT-no-wheat?style=flat-square"> |
| application | Specific Field IPs|
| [rng](https://github.com/retroSoC/rng) | <img src="https://img.shields.io/badge/SPC-done-green?style=flat-square"> <img src="https://img.shields.io/badge/RTF-done-green?style=flat-square"> <img src="https://img.shields.io/badge/SMT-done-green?style=flat-square"> <img src="https://img.shields.io/badge/UVV-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FUC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/COC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/SOI-done-green?style=flat-square"> <img src="https://img.shields.io/badge/FPE-done-green?style=flat-square"> <img src="https://img.shields.io/badge/TPT-no-wheat?style=flat-square"> |
| [crc](https://github.com/retroSoC/crc) | <img src="https://img.shields.io/badge/SPC-done-green?style=flat-square"> <img src="https://img.shields.io/badge/RTF-done-green?style=flat-square"> <img src="https://img.shields.io/badge/SMT-done-green?style=flat-square"> <img src="https://img.shields.io/badge/UVV-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FUC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/COC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/SOI-done-green?style=flat-square"> <img src="https://img.shields.io/badge/FPE-done-green?style=flat-square"> <img src="https://img.shields.io/badge/TPT-no-wheat?style=flat-square"> |
| multimedia | SPI/QSPI TFT-LCD, VGA/LCD, SDIO TF/WiFi, CMOS Camera, DMA, 2D Graphic Accel.|
| [spi](https://github.com/retroSoC/spi) | <img src="https://img.shields.io/badge/SPC-done-green?style=flat-square"> <img src="https://img.shields.io/badge/RTF-done-green?style=flat-square"> <img src="https://img.shields.io/badge/SMT-done-green?style=flat-square"> <img src="https://img.shields.io/badge/UVV-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FUC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/COC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/SOI-done-green?style=flat-square"> <img src="https://img.shields.io/badge/FPE-done-green?style=flat-square"> <img src="https://img.shields.io/badge/TPT-no-wheat?style=flat-square"> |
| [i2s](https://github.com/retroSoC/i2s) | <img src="https://img.shields.io/badge/SPC-done-green?style=flat-square"> <img src="https://img.shields.io/badge/RTF-done-green?style=flat-square"> <img src="https://img.shields.io/badge/SMT-done-green?style=flat-square"> <img src="https://img.shields.io/badge/UVV-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FUC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/COC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/SOI-done-green?style=flat-square"> <img src="https://img.shields.io/badge/FPE-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/TPT-no-wheat?style=flat-square"> |
| [vga](https://github.com/retroSoC/vga) | <img src="https://img.shields.io/badge/SPC-done-green?style=flat-square"> <img src="https://img.shields.io/badge/RTF-done-green?style=flat-square"> <img src="https://img.shields.io/badge/SMT-done-green?style=flat-square"> <img src="https://img.shields.io/badge/UVV-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FUC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/COC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/SOI-done-green?style=flat-square"> <img src="https://img.shields.io/badge/FPE-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/TPT-no-wheat?style=flat-square"> |
| [dma](https://github.com/retroSoC/dma) | <img src="https://img.shields.io/badge/SPC-done-green?style=flat-square"> <img src="https://img.shields.io/badge/RTF-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/SMT-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/UVV-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FUC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/COC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/SOI-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FPE-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/TPT-no-wheat?style=flat-square"> |
| [dvp](https://github.com/retroSoC/dvp) | <img src="https://img.shields.io/badge/SPC-done-green?style=flat-square"> <img src="https://img.shields.io/badge/RTF-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/SMT-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/UVV-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FUC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/COC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/SOI-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FPE-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/TPT-no-wheat?style=flat-square"> |
| [sdio](https://github.com/retroSoC/sdio) | <img src="https://img.shields.io/badge/SPC-done-green?style=flat-square"> <img src="https://img.shields.io/badge/RTF-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/SMT-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/UVV-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FUC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/COC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/SOI-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FPE-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/TPT-no-wheat?style=flat-square"> |
| memory | on-chip SRAM, QPI SDR FRAM/PSRAM, OPI DDR PSRAM, 16-bit SDR SDRAM|
| [sram](https://github.com/retroSoC/sram) | <img src="https://img.shields.io/badge/SPC-done-green?style=flat-square"> <img src="https://img.shields.io/badge/RTF-done-green?style=flat-square"> <img src="https://img.shields.io/badge/SMT-done-green?style=flat-square"> <img src="https://img.shields.io/badge/UVV-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FUC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/COC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/SOI-done-green?style=flat-square"> <img src="https://img.shields.io/badge/FPE-done-green?style=flat-square"> <img src="https://img.shields.io/badge/TPT-no-wheat?style=flat-square"> |
| [fram](https://github.com/retroSoC/fram) | <img src="https://img.shields.io/badge/SPC-done-green?style=flat-square"> <img src="https://img.shields.io/badge/RTF-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/SMT-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/UVV-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FUC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/COC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/SOI-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FPE-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/TPT-no-wheat?style=flat-square"> |
| [psram](https://github.com/retroSoC/psram) | <img src="https://img.shields.io/badge/SPC-done-green?style=flat-square"> <img src="https://img.shields.io/badge/RTF-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/SMT-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/UVV-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FUC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/COC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/SOI-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FPE-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/TPT-no-wheat?style=flat-square"> |
| [sdram](https://github.com/retroSoC/sdram) | <img src="https://img.shields.io/badge/SPC-done-green?style=flat-square"> <img src="https://img.shields.io/badge/RTF-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/SMT-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/UVV-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FUC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/COC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/SOI-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FPE-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/TPT-no-wheat?style=flat-square"> |
| other | |
| [tapeout<sup>1</sup>](https://github.com/retroSoC/tapeout) | <img src="https://img.shields.io/badge/SPC-done-green?style=flat-square"> <img src="https://img.shields.io/badge/RTF-done-green?style=flat-square"> <img src="https://img.shields.io/badge/SMT-done-green?style=flat-square"> <img src="https://img.shields.io/badge/UVV-no-wheat?style=flat-square"> <img src="https://img.shields.io/badge/FUC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/COC-0-green?style=flat-square"> <img src="https://img.shields.io/badge/SOI-done-green?style=flat-square"> <img src="https://img.shields.io/badge/FPE-done-green?style=flat-square"> <img src="https://img.shields.io/badge/TPT-done-green?style=flat-square"> |

1. this PRIVATE [repo](https://github.com/retroSoC/tapeout)  contains some tapeout-verified IPs:
    1. [chiplink](https://github.com/retroSoC/tapeout/tree/master/chiplink): a 8-bits D2D(die-to-die) bus interface derived from SiFive ChipLink.
    2. [keyboard](https://github.com/retroSoC/tapeout/tree/master/chiplink): an axi4-lite based ps2 keyboard IP.
    3. [spi](https://github.com/retroSoC/tapeout/tree/master/spi/rtl): an apb3-based standard SPI IP.
    4. [uart](https://github.com/retroSoC/tapeout/tree/master/uart): an apb3-based UART IP compatible with UART16550.

| state badge statement | | | | |
| :---:    | :---     |  :---     |  :---     | :--- |
| SPC: SPEC complete | RTF: RTL frozen | SMT: SMOKE test | UVV: UVM verif | FUC: FUNCTION coverage |
| COC: CODE coverage | SOI: SoC integ | FPE: FPGA emu | TPT: TAPEOUT test | |
  
<details>
  <summary>More Info</summary>

## Template
Refer to the [template repo](https://github.com/retroSoC/template/blob/main). If you want to create a new ip repo, You need to:

* Use this repository template to create a new repo
* Update the content `[IP NAME]` in `header` file and remove the `header` file.

## Style
refer to the [style.md](https://github.com/retroSoC/template/blob/main/style.md).

## Contribution
If you want to contribute to this project, be sure to review the [guidelines](https://github.com/retroSoC/template/blob/main/CONTRIBUTING.md). This is an open project and contributions and collaborations are always welcome!! This project adheres to retroSoC's [code_of_conduct](https://github.com/retroSoC/template/blob/main/CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code.

we use GitHub issues for tracking requests and bugs, so please direct specific questions to [issues panel](https://github.com/retroSoC/.github/issues).

The retroSoC project strives to abide by generally accepted best practices in open-source software development, you can issue bugs, pull requests, new features and modification suggestions freely. Your feedbacks could help us ensure a bright future for this project. We value and treasure every issue or contribution, big or small. 😄

## License
All of the IPs codes are redistributed or released under the OSI Approved LICENSE [MulanPSL2](https://opensource.org/license/mulanpsl-2-0/).

## Acknowledgement

## Reference
    
</details>
