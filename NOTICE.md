# Unofficial modification notice

This repository is an unofficial, modified, non-commercial ZMK user-config wrapper initially created on 2026-09-01 and audited on 2026-09-02.

It is **not** an official EKS Inc. or MODU release.

## Original work

- Project: `22sh22/modu-c-firmware`
- Original firmware copyright: Copyright (c) 2026 EKS Inc.
- Original firmware creator: Ryu
- Pinned upstream revision: `bee0bb4b812f63f279eb67e928accc89600b5904`
- Original license: EKS NON-COMMERCIAL SOURCE LICENSE 1.0

## Modifications in this wrapper

- Copied the original `modu.keymap` into the conventional user-config path `config/modu.keymap`, then customized it through Keymap Editor.
- Added Keymap Editor layout metadata for the 67-position `default_transform`.
- Added a pinned west manifest that fetches the original MODU-C board, shield, custom scanning code, and PMW3610 driver.
- Added GitHub Actions automation for left/right builds and the same nRF52840 HEX-to-UF2 family used by the original build scripts.
- Added exact output selection, Intel HEX validation/normalization, UF2 structural verification, and dependency-free self-tests.
- Added static consistency checks, license/notice packaging, and Korean setup documentation.

No trademark rights, patent rights, warranty, or endorsement are provided.

## ZMK Studio integration

Studio build configuration, physical layout, and validation checks are adapted from
22sh22/modu-c-zmk-config studio-test commit
5c5a60ace453b11ecf7fab9e1fb70f4483942caa. The custom keymap is retained from
cherrytomato1/modu-c-zmk-config commit 7677fa5c8e6b65ee6a353d68a5585be82f60fdfa,
with Studio unlock and USB output on service-layer R/T. Existing licenses apply.
