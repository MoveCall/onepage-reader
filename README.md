<div align="center">

<a href="https://github.com/MoveCall/onepage-reader">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/logo-dark.svg">
    <img alt="OnePage Logo" src="assets/logo-light.svg" width="56">
  </picture>
</a>

# OnePage Reader

**Open-Hardware DIY E-Reader Ecosystem**  
*Firmware · Custom Board · Enclosure · Browser Tools*

<br/>

[![MCU](https://img.shields.io/badge/MCU-ESP32--C61-red.svg)](https://www.espressif.com/)
[![Firmware Release](https://img.shields.io/badge/Firmware-v0.1.0-blue.svg)](https://github.com/MoveCall/crosspoint-onepage/releases)
[![Hardware](https://img.shields.io/badge/Hardware-V1_2026--08--19-success.svg)](electronics/c61/)
[![Enclosure](https://img.shields.io/badge/MakerWorld-Exclusive-orange.svg)](https://makerworld.com.cn/zh/@MoveCall)
[![License](https://img.shields.io/badge/License-Mixed-lightgrey.svg)](#licensing)

<br/>

<img src="assets/onepage-c61-front.png" width="680" alt="OnePage C61 Front View" style="border-radius: 12px; box-shadow: 0 8px 24px rgba(0,0,0,0.12);" />

<br/>
<br/>

</div>

---

## <img src="assets/icons/book.svg" width="20" height="20" style="vertical-align: -4px; margin-right: 6px;" /> Overview

**OnePage** is an open-hardware DIY e-reader built around the **ESP32-C61** RISC-V wireless SoC. 

This repository serves as the central hub of the entire ecosystem: it houses the complete electronic fabrication packages (schematic, PCB, BOM, iBOM) and mechanical panel files, while aggregating the firmware, board SDK, and web companion tools via Git submodules.

---

## <img src="assets/icons/chip.svg" width="20" height="20" style="vertical-align: -4px; margin-right: 6px;" /> Key Features

- **Next-Gen ESP32-C61**: Low-power RISC-V core with integrated Wi-Fi 6 and BLE.
- **BLE Page-Turner Remote**: Supports Bluetooth remote page turning with battery monitoring, key swapping, and live scanning.
- **Web Companion Tools**:
  - **Web Serial Flasher**: Flash firmware directly from Chromium-based browsers without local toolchain setups.
  - **Online Font Tool (`cpfont`)**: In-browser CJK font subsetting and glyph rasterization.
- **Production-Ready Hardware**: Complete gerbers, pick-and-place files, schematic PDF, and interactive BOM (iBOM).
- **Hybrid Craftsmanship**: Clean PET front and acrylic rear panels with an optional CNC mid-frame and MakerWorld 3D printable shell.

---

## <img src="assets/icons/layers.svg" width="20" height="20" style="vertical-align: -4px; margin-right: 6px;" /> Ecosystem & Repositories

| Component | Submodule / Link | Description |
|:---|:---|:---|
| <img src="assets/icons/book.svg" width="16" height="16" style="vertical-align: -3px; margin-right: 4px;" /> **Firmware** | [`firmware/`](firmware) → [crosspoint-onepage](https://github.com/MoveCall/crosspoint-onepage) | Port of [CrossPoint Reader](https://github.com/crosspoint-reader/crosspoint-reader) tailored for OnePage C61 (`v0.1.0`). |
| <img src="assets/icons/chip.svg" width="16" height="16" style="vertical-align: -3px; margin-right: 4px;" /> **Board SDK** | *(Nested in firmware)* → [onepage-reader-sdk-arduino](https://github.com/MoveCall/onepage-reader-sdk-arduino) | Arduino & PlatformIO board-support drivers (EPD, keys, power management, SD). |
| <img src="assets/icons/pcb.svg" width="16" height="16" style="vertical-align: -3px; margin-right: 4px;" /> **Electronics** | [`electronics/c61/`](electronics/c61/) | Schematic, Gerbers, BOM, iBOM, and SMT pick-and-place data. |
| <img src="assets/icons/box.svg" width="16" height="16" style="vertical-align: -3px; margin-right: 4px;" /> **Enclosure & Panels** | [`mechanical/c61/`](mechanical/c61/) → [MakerWorld](https://makerworld.com.cn/zh/@MoveCall) | Custom PET / Acrylic panels (`.epanm`), CNC mid-frame, and MakerWorld 3D models. |
| <img src="assets/icons/browser.svg" width="16" height="16" style="vertical-align: -3px; margin-right: 4px;" /> **Web Tools** | [`web/`](web) → [onepage-reader-web](https://github.com/MoveCall/onepage-reader-web) | Official website, WebSerial flasher, and `cpfont` builder. |

---

## <img src="assets/icons/terminal.svg" width="20" height="20" style="vertical-align: -4px; margin-right: 6px;" /> Quick Start

### 1. Clone with all Submodules

To clone the entire project including firmware, drivers, and web tools in one shot:

```bash
git clone --recursive git@github.com:MoveCall/onepage-reader.git
```

If you already cloned without `--recursive`:
```bash
git submodule update --init --recursive
```

### 2. Flash Firmware via Browser

No need to install Python or compilation toolchains — visit the Web Flasher from Chrome / Edge to flash the latest release via USB-C:
[Open Web Flasher](https://github.com/MoveCall/onepage-reader-web)

---

## <img src="assets/icons/folder.svg" width="20" height="20" style="vertical-align: -4px; margin-right: 6px;" /> Repository Layout

```text
onepage-reader/
├── firmware/        Submodule → crosspoint-onepage (nested: onepage-reader-sdk-arduino)
├── web/             Submodule → onepage-reader-web (browser flasher & font tools)
├── electronics/     PCB design, schematics & fabrication files per hardware variant
│   └── c61/
├── mechanical/      Panels (.epanm), CNC models (.stl) & MakerWorld 3D model links
│   └── c61/
└── assets/          Logos, graphics & media assets
```

---

## <img src="assets/icons/shield-lock.svg" width="20" height="20" style="vertical-align: -4px; margin-right: 6px;" /> Licensing

This is a **mixed-license** project designed to balance open hardware collaboration with design protection:

- **Electronics & Docs** (this repository): **[CC-BY-SA-4.0](https://creativecommons.org/licenses/by-sa/4.0/)** (`/electronics` may additionally carry **CERN-OHL-S** for hardware designs).
- **Firmware & SDK**: **[MIT](firmware/LICENSE)** (preserves CrossPoint Reader copyright).
- **3D Enclosure**: **[MakerWorld Exclusive License](https://makerworld.com.cn/zh/@MoveCall)** — 3D printable models are distributed exclusively via MakerWorld and are **not** stored directly in this repository.
- **OnePage Name & Logo**: All Rights Reserved.

---

## <img src="assets/icons/heart.svg" width="20" height="20" style="vertical-align: -4px; margin-right: 6px;" /> Acknowledgements

- Built on top of the [CrossPoint Reader](https://github.com/crosspoint-reader/crosspoint-reader) project (MIT © Dave Allie). *(Not affiliated with CrossPoint or Xteink)*.
- Powered by Espressif ESP32-C61 & Open-Source Community.
