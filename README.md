# AltoBeam Wifi Driver for 6xxx Series Chipsets

Find more information at [AltoBeam's official website](https://www.altobeam.com/channels/28.html).

This driver supports a range of chipsets in the 6xxx series.  Some Altobeam-based ODM chipsets are also compatible.

Below is a detailed list of the supported chipsets, including their dimensions, production dates, features, and current production status.

The original ATBM6062 (Cronus) lives in the `atbm-606x` branch. The newer Wi-Fi 6
"40M lite" SDK — covering **ATBM6062**, **ATBM6062-C**, **ATBM6162** and
**ATBM6132-C** — lives in the `atbm-606x-c` branch; see the [Wi-Fi 6 Variants](#wi-fi-6-variants-atbm-606x-c-branch)
table below for the per-chip build/firmware matrix.

### ALTOBEAM:
| chip        | size | release | status  | description                                                                              |
|-------------|------|---------|---------|------------------------------------------------------------------------------------------|
| ATBM6011B   | 4x4  | Q2 2019 | EOL     | 1T1R, IEEE 802.11b/g/n, HT20, SDIO                                                       |
| ATBM6012B   | 4x4  | Q2 2019 | Current | 1T1R, IEEE 802.11b/g/n, HT20, USB                                                        |
| ATBM6012B-X | 4×4  | Q2 2023 | Current | 1T1R, IEEE 802.11b/g/n, HT20, BLE, USB                                                   |
| ATBM6021    | 4×4  | Q1 2018 | EOL     | 1T1R, IEEE 802.11b/g/n, HT20/HT40, SDIO                                                  |
| ATBM6022    | 4×4  | Q1 2018 | EOL     | 1T1R, IEEE 802.11b/g/n, HT20/HT40, USB                                                   |
| ATBM6031    | 4×4  | Q2 2019 | Current | 1T1R, IEEE 802.11b/g/n, HT20/HT40, SDIO                                                  |
| ATBM6031-X  | 4x4  | Q2 2023 | Current | 1T1R, IEEE 802.11b/g/n, HT20/HT40, BLE, SDIO                                             |
| ATBM6032    | 4×4  | Q2 2019 | Current | 1T1R, IEEE 802.11b/g/n, HT20/HT40, USB                                                   |
| ATBM6032-X  | 4x4  | Q2 2023 | Current | 1T1R, IEEE 802.11b/g/n, HT20/HT40, BLE, USB                                              |
| ATBM6132    | 5x5  | Q4 2023 | Current | 1T1R, IEEE 802.11a/b/g/n, 2.4/5GHz dual band, HT20/HT40, BLE v5.0 Combo chip             |
| ATBM6x41    | 6x6  | Q2 2021 | Current | 1T1R, IEEE 802.11b/g/n, low power iot Wi-Fi chip, embedded MCU, 2Mbit Flash              |
| ATBM6062    | 5x5  | Q1 2023 | Current | 1T1R, IEEE 802.11b/g/n/ax, 2.4GHz, HT20/HT40, Wi-Fi 6 + BLE v5.0 (Cronus)                |
| ATBM6062-C  | 4x4  | Q4 2024 | Current | 1T1R, IEEE 802.11b/g/n/ax, 2.4GHz, HT20/HT40, Wi-Fi 6 + BLE v5.0 (Cronus-Lite)           |
| ATBM6162    | 4x4  | Q4 2024 | Current | 1T1R, IEEE 802.11a/b/g/n/ac/ax, 2.4/5GHz dual band, HT20/HT40, Wi-Fi 6 + BLE v5.0 (Oceanus) |
| ATBM6132-C  | 4x4  | Q4 2024 | Current | 1T1R, IEEE 802.11a/b/g/n, 2.4/5GHz dual band, HT20/HT40, Wi-Fi 4 + BLE v5.0 (Oceanus die) |

### Wi-Fi 6 Variants (`atbm-606x-c` branch)

The `atbm-606x-c` branch builds the Wi-Fi 6 SDK for four products spanning three
silicon dies. The chip is auto-detected at runtime; each build is configured for one
bus and loads a single firmware blob (named by `CONFIG_ATBM_FW_NAME_WIFI6`, installed
as `<module>_fw.bin`). All variants are Wi-Fi-only (no BLE-comb) in these configs.

| product     | silicon     | chip_id | bands  | Wi-Fi | bus  | module      | config              | firmware blob              |
|-------------|-------------|---------|--------|-------|------|-------------|---------------------|----------------------------|
| ATBM6062    | Cronus      | 0x5A    | 2.4    | 6     | USB  | atbm6062u   | atbm6062u.config    | firmware_usb_cronus.bin    |
| ATBM6062    | Cronus      | 0x5A    | 2.4    | 6     | SDIO | atbm6062s   | atbm6062s.config    | firmware_sdio_cronus.bin   |
| ATBM6062-C  | Cronus-Lite | 0x5C    | 2.4    | 6     | USB  | atbm6062cu  | atbm6062cu.config   | firmware_usb_clite.bin     |
| ATBM6062-C  | Cronus-Lite | 0x5C    | 2.4    | 6     | SDIO | atbm6062cs  | atbm6062cs.config   | firmware_sdio_clite.bin    |
| ATBM6162    | Oceanus     | 0x30    | 2.4/5  | 6+ac  | USB  | atbm6162u   | atbm6162u.config    | firmware_usb_ocea.bin      |
| ATBM6162    | Oceanus     | 0x30    | 2.4/5  | 6+ac  | SDIO | atbm6162s   | atbm6162s.config    | firmware_sdio_ocea.bin     |
| ATBM6132-C  | Oceanus     | 0x30    | 2.4/5  | 4     | USB  | atbm6132cu  | atbm6132cu.config   | firmware_usb_ocea.bin      |
| ATBM6132-C  | Oceanus     | 0x30    | 2.4/5  | 4     | SDIO | atbm6132cs  | atbm6132cs.config   | firmware_sdio_ocea.bin     |

Notes:
- **ATBM6162 and ATBM6132-C share the same Oceanus die** (`chip_id 0x30`) and the same
  `ocea` firmware. The 6132-C is fused to Wi-Fi 4 (no HE/VHT); the firmware reports the
  capability at runtime, so one build serves both.
- **ATBM6062-C is the cost-reduced "Cronus-Lite" revision** of the ATBM6062 — a distinct
  die (`chip_id 0x5C`) with its own `clite` firmware.
- Configs are in `configs/`; firmware blobs (generated from the `hal_apollo/firmware_*.h`
  headers via `firmware/create_firmware.sh`) are in `firmware/`.

### SIGMASTAR:
| chip        | size | release | status  | description                                                                              |
|-------------|------|---------|---------|------------------------------------------------------------------------------------------|
| SSW101B     | 4x4  | N/A     | Current | 1T1R, IEEE 802.11b/g/n, HT20 and HT40, USB (SigmaStar Technology)                        |
| SSW102B     | 4x4  | N/A     | Current | 1T1R, IEEE 802.11b/g/n, HT20 and HT40, SDIO (SigmaStar Technology)                       |

HARDWARE:
| name      | chip              | 
|-----------|-------------------|
| athenab   | atbm601x atbm602x |
| aresb     | atbm603x          |
| asmlite   | atbm6012b-x       |
| mercurius | atbm6132          |
| comb      | wifi4_all_chip    |
| hera      | atbm6x41          |
| cronus    | atbm6062          |
| cronus-lite | atbm6062-c      |
| oceanus   | atbm6162 atbm6132-c |
