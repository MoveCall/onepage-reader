# OnePage Reader

Open-hardware DIY e-reader — **firmware · board · 3D case · web**, in one place.

OnePage is a self-designed e-reader built on the **ESP32-C61**. This is the project hub: it holds the hardware (schematic/PCB) and 3D enclosure design, and aggregates the code repos as submodules so `git clone --recursive` gets the whole project.

## Repositories

| Component | Repo | What |
|---|---|---|
| **Firmware** | [`firmware/`](firmware) → [crosspoint-onepage](https://github.com/MoveCall/crosspoint-onepage) | Reader firmware — a port of [CrossPoint Reader](https://github.com/crosspoint-reader/crosspoint-reader) to the OnePage C61. |
| **Board SDK** | (nested in firmware) → [onepage-reader-sdk-arduino](https://github.com/MoveCall/onepage-reader-sdk-arduino) | Arduino/PlatformIO board-support drivers (display/input/battery/SD). |
| **Web** | [`web/`](web) → [onepage-reader-web](https://github.com/MoveCall/onepage-reader-web) | Product site + browser tools. |
| **Hardware** | [`electronics/`](electronics) | Schematic, PCB, BOM (this repo). |
| **3D case** | [`mechanical/`](mechanical) → MakerWorld | Printable enclosure — published on **MakerWorld** (models not in this repo). |

## Clone

```bash
# whole project (firmware + its SDK + web) in one shot:
git clone --recursive git@github.com:MoveCall/onepage-reader.git
```

## Repository layout

```
onepage-reader/
├── firmware/        submodule → crosspoint-onepage (nested: onepage-reader-sdk-arduino)
├── web/             submodule → onepage-reader-web
├── electronics/     PCB design (LCEDA/EasyEDA source + Gerber/BOM/CPL) — per hardware variant
│   └── c61/
├── mechanical/      3D enclosure — pointers to MakerWorld (models NOT in repo) + assembly docs
│   └── c61/
└── docs/            whole-device docs
```

Hardware variant (C61 now, S3 later) lives in `c61/` / `s3/` subdirs; repo names stay variant-agnostic.

## Licensing

This is a **mixed-license** project — open electronics + firmware, protected enclosure:

- Electronics + docs in this repo: **CC-BY-SA-4.0** (`/electronics` may additionally carry **CERN-OHL-S** for the PCB).
- Firmware & SDK submodules: **MIT** (see their repos; firmware preserves the CrossPoint Reader copyright).
- **3D enclosure: [MakerWorld Exclusive License](https://makerworld.com.cn/zh/@MoveCall)** — models are distributed only via MakerWorld and are **not** included in this repo. `mechanical/` holds pointers/assembly docs only.
- OnePage name and logo: All Rights Reserved.

Based on [CrossPoint Reader](https://github.com/crosspoint-reader/crosspoint-reader) (MIT © Dave Allie). Not affiliated with CrossPoint or Xteink.
