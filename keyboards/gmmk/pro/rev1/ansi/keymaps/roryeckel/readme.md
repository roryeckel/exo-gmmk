# Rory Eckel's GMMK Pro ANSI keymap

This keymap preserves the custom behavior from this fork while staying aligned with current upstream QMK.

## Custom behavior

* Hold `Fn` to light the active layer-1 keys in white.
* The rotary encoder controls volume on the base layer and screen brightness while `Fn` is held.
* Caps Lock lights the indicator LED red.
* RGB matrix sleep and timeout behavior are enabled, with a 10 minute timeout.
* Several RGB effects that were noisy or buggy in the original fork stay disabled.

## Build

```sh
qmk compile -kb gmmk/pro/rev1/ansi -km roryeckel
```

## Flash

```sh
qmk flash -kb gmmk/pro/rev1/ansi -km roryeckel
```

If you prefer QMK Toolbox, compile first and then flash the generated `.bin` file manually.

To enter the bootloader, use one of the following:

* Hold the reset switch on the underside of the PCB while connecting USB.
* Hold `Esc` while connecting USB.
* Press `Fn+\` from the default layer after this keymap is flashed.
