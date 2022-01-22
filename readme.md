# Quantum Mechanical Keyboard Firmware

This is a fork of the QMK firmware with my special keymapping for the ANSI GMMK Pro.
I use this daily but I am not responsible for your board breaking. Feel free to leave issues & suggestions.

## Features
- Hold FN to light up the second layer keys in white (you'll want to see what they do based on the LAYER variable in [keymap.c](https://github.com/roryeckel/exo-gmmk/blob/e11195a1ec17c0f14a3fc4c4a2e45d27ca324a8d/keyboards/gmmk/pro/ansi/keymaps/roryeckel/keymap.c) - look up the keycodes [here](https://github.com/qmk/qmk_firmware/blob/master/docs/keycodes.md))
- Volume dial now working, hold FN while turning for PC brightness
- Caps lock now turns red when active
- Disabled buggy lighting FX, enabled other cool ones

## GUI Installation from binary
Warning: Completely untested, Windows/Mac only
1. Install [qmk_toolbox](https://github.com/qmk/qmk_toolbox)
2. Download the binary [qmmk_pro_ansi_roryeckel.bin](https://github.com/roryeckel/exo-gmmk/blob/master/gmmk_pro_ansi_roryeckel.bin) from this repo
3. Use the GUI to select/flash the binary file
4. Hard reset the keyboard into bootloader mode (on Glorious Core, hold spacebar and b while plugging it in)

## CLI Installation from source
Only tested on Linux
1. Install [qmk_cli](https://github.com/qmk/qmk_cli) from your preferred package manager
2. `qmk clone https://github.com/roryeckel/exo-gmmk.git`
3. Enter `exo-gmmk` directory
4. Execute `util/qmk_install.sh`
5. `qmk compile`
6. `qmk flash`
7. Hard reset the keyboard into bootloader mode (on Glorious Core, hold spacebar and b while plugging it in)
8. Keyboard should be identified by `qmk` and flashed
