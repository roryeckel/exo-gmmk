# GMMK Pro Custom QMK Firmware

Personal [QMK](https://docs.qmk.fm) firmware fork for the GMMK Pro (ANSI, Rev 1).

## Custom keymap features

- **Fn layer highlighting** -- hold Fn to light active layer-1 keys in white
- **Rotary encoder** -- volume control on the base layer, screen brightness while Fn is held
- **Caps Lock indicator** -- lights the indicator LED red
- **RGB sleep** -- RGB matrix turns off after 10 minutes of inactivity
- **Media keys** -- Fn+F5/F6/F7/F8 for Previous/Next/Play/Stop
- **NKRO toggle** -- Fn+N to switch between 6KRO and NKRO (persisted to EEPROM)
- **Calculator** -- Fn+C opens the system calculator
- **Bootloader** -- Fn+\ enters the bootloader for flashing

The keymap source lives in [`keyboards/gmmk/pro/rev1/ansi/keymaps/roryeckel/`](keyboards/gmmk/pro/rev1/ansi/keymaps/roryeckel/).

## Building

Linux or WSL is recommended. On Windows, WSL avoids the need for a separate MSYS2 installation.

### 1. Install the QMK CLI

```sh
curl -fsSL https://install.qmk.fm | sh
```

### 2. Clone and set up

Clone the repo **inside the Linux/WSL filesystem** (not under `/mnt/c/`) for build performance:

```sh
git clone https://github.com/roryeckel/exo-gmmk.git ~/qmk_firmware
cd ~/qmk_firmware
qmk setup -H ~/qmk_firmware
```

Answer `y` to all prompts.

### 3. Compile

```sh
qmk compile -kb gmmk/pro/rev1/ansi -km roryeckel
```

This produces `gmmk_pro_rev1_ansi_roryeckel.bin` in the repo root.

## Flashing

### Option A: QMK CLI (Linux native)

```sh
qmk flash -kb gmmk/pro/rev1/ansi -km roryeckel
```

### Option B: QMK Toolbox (Windows / macOS)

1. Download [QMK Toolbox](https://github.com/qmk/qmk_toolbox/releases/latest).
2. If you built in WSL, copy the `.bin` to your Windows filesystem:
   ```sh
   cp ~/qmk_firmware/gmmk_pro_rev1_ansi_roryeckel.bin /mnt/c/Users/$USER/Desktop/
   ```
3. Open QMK Toolbox, select the `.bin` file, and flash.

### Entering the bootloader

Use any of the following to put the keyboard into bootloader mode:

- Hold **Esc** while plugging in USB
- Hold the **reset switch** on the underside of the PCB while plugging in USB
- Press **Fn+\\** from the default layer (once this keymap is already flashed)

## Upstream

This fork is based on [qmk/qmk_firmware](https://github.com/qmk/qmk_firmware). See the [QMK documentation](https://docs.qmk.fm) for general reference.
