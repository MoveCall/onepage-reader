# OnePage electronics — ESP32-C61 (variant: c61)

PCB design for the OnePage C61 board. Designed in **LCEDA / EasyEDA (立创EDA)**.

## Source of truth

- LCEDA source project — either the exported project file (`*.epro` / JSON) committed under
  `lceda/`, **or** the LCEDA open-hardware page on oshwhub: **<oshwhub link — TBD>**.
  (If the design lives on oshwhub, link it here and keep the exported/fab files below in-repo.)

## Files to add here

- `lceda/` — exported LCEDA source project (`*.epro` or JSON), if committing the source.
- `gerber/` — fabrication Gerbers + drill (tool-agnostic; any fab house can use these).
- `assembly/bom.csv` — bill of materials.
- `assembly/cpl.csv` — pick-and-place / component placement (LCEDA "坐标文件").
- `schematic.pdf` — readable schematic export (viewable without LCEDA).
- `pinout.md` — pin map.
- `LICENSE` — CERN-OHL-S-2.0 for the electronic design (optional, in addition to repo CC-BY-SA).

> Tip: Gerber + BOM + CPL + schematic.pdf are the tool-agnostic essentials — commit these so
> anyone can review and fabricate the board without opening LCEDA.

## Notes for the BOM / build (known gotchas)

- **SPI flash vendor matters for flashing.** Winbond W25Q128JW flashes fast with the
  esptool stub (~95 s); Puya PY25Q128HA crashes the stub and **must** be flashed with
  `--no-stub` (~380 s). Record which part is fitted.
- **32.768 kHz crystal** on the dedicated XTAL_32K pins is required for BLE low-power
  (enables the firmware's 42→23 mA idle optimization).
- Pin map (from firmware `InputManager`): front 4 keys = ADC ladder on GPIO4;
  side keys GPIO6/GPIO9; power GPIO2; EPD + SD share the power rail on GPIO27;
  USB D+ = GPIO13.
