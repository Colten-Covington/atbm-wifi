# AltoBeam Wifi Driver for 6xxx Series Chipsets

Find more information at [AltoBeam's official website](https://www.altobeam.com/channels/28.html).

This driver supports a range of chipsets in the 6xxx series.  Some Altobeam-based ODM chipsets are also compatible.

Below is a detailed list of the supported chipsets, including their dimensions, production dates, features, and current production status.

The original ATBM6062 (Cronus) lives in the `atbm-606x` branch. The newer Wi-Fi 6
"40M lite" SDK — covering **ATBM6062**, **ATBM6062-C**, **ATBM6162** and **ATBM6132-C** —
lives in the `atbm-606x-c` branch (per-chip configs in `configs/`, firmware blobs in
`firmware/`). The chip is auto-detected at runtime; each build targets one bus and loads
a single firmware blob, installed as `<module>_fw.bin`.

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
| ATBM6062    | 5x5  | Q1 2023 | Current | 1T1R, IEEE 802.11b/g/n/ax, 2.4GHz, HT20/HT40, Wi-Fi 6 + BLE v5.0 (Cronus, 0x5A) — firmware_{usb,sdio}_cronus.bin |
| ATBM6062-C  | 4x4  | Q4 2024 | Current | 1T1R, IEEE 802.11b/g/n/ax, 2.4GHz, HT20/HT40, Wi-Fi 6 + BLE v5.0 (Cronus-Lite, 0x5C) — firmware_{usb,sdio}_clite.bin |
| ATBM6162    | 4x4  | Q4 2024 | Current | 1T1R, IEEE 802.11a/b/g/n/ac/ax, 2.4/5GHz dual band, HT20/HT40, Wi-Fi 6 + BLE v5.0 (Oceanus, 0x30) — firmware_{usb,sdio}_ocea.bin |
| ATBM6132-C  | 4x4  | Q4 2024 | Current | 1T1R, IEEE 802.11a/b/g/n, 2.4/5GHz dual band, HT20/HT40, Wi-Fi 4 + BLE v5.0 (Oceanus die 0x30, shares 6162 firmware) |

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
