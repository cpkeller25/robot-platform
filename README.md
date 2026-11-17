# robot-platform

A small (~20 cm) autonomous four-wheel-drive indoor robot.

- **Main board:** custom KiCad PCB with an ESP32-S3 for motor control, sensors and power management
- **Linux computer:** Raspberry Pi on a header, running a custom Yocto/OpenEmbedded image
- **Chassis:** FreeCAD

> **Status:** Main board schematic in progress.  Nothing here has been built or tested yet.

## Repository layout

| Folder | Contents |
|---|---|
| `hardware/main-board/` | KiCad project for the main board |
| `hardware/lib/` | Project symbols, footprints and 3D models (shared by all boards) |
| `firmware/esp32/` | ESP-IDF firmware for the ESP32-S3 |
| `linux/meta-robot/` | Yocto layer for the Raspberry Pi image |
| `mechanical/` | Chassis CAD (stored with Git LFS) |
| `docs/` | Design notes, block diagram, bring-up log |

## Tools

- KiCad 10 (files saved in 10 will not open in KiCad 9)
- Git with [Git LFS](https://git-lfs.com) for STEP, STL and FreeCAD files
- ESP-IDF (version to be pinned when firmware starts)
- Yocto (release to be chosen; layer versions pinned with kas)

## Getting started

```
git lfs install
git clone https://github.com/cpkeller25/robot-platform.git
```

Open `hardware/main-board/main-board.kicad_pro` in KiCad. Every part 
the board uses comes from either KiCad's standard libraries or 
`hardware/lib/`, so nothing extra needs installing.

Manufacturing files (Gerbers, drill files, BOM) are attached to each
[Release](../../releases), not committed to the repo.

## License

| Part | License |
|---|---|
| Hardware (`hardware/`, `mechanical`) | CERN-OHL-P-2.0 |
| Firmware and Linux layer | MIT |
| Documentation (`docs/`) | CC BY 4.0 |

See the `LICENSE` file int each folder for the full text
