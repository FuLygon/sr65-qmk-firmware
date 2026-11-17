# Firmware for SR Studio Radiance65 keyboard (SR65)

The stock Radiance65 firmware uses a 1ms `DEBOUNCE`. Which is way too short and often cause chattering. This repo contains custom QMK firmware builds with longer `DEBOUNCE` and different `DEBOUNCE_TYPE` that could possibly fix the chattering.

Pre-built firmware is available in multiple variants:

- `DEBOUNCE`: 2, 3, 5, 8, 10 ms
- `DEBOUNCE_TYPE`: `sym_defer_g`, `sym_defer_pr`, `sym_defer_pk`, `sym_eager_pr`, `sym_eager_pk`, `asym_eager_defer_pk`

All variant images are also built with `CONSOLE_ENABLE = no` and `COMMAND_ENABLE = no`.

## Download

[Releases](https://github.com/FuLygon/sr65-qmk-firmware/releases)

## How to install

You can flash the firmware with [Vial](https://vial.rocks).

1. Open Vial with the keyboard connected.
2. Go to **File** > **Save current layout** to save your current layout setup (*optional*)
2. Go to the **Firmware updater** > **Select file...** and pick the `.vfw` you want.
3. Leave **Restore current layout after flashing** checked, then click **Flash**.

Vial reboots the keyboard into the bootloader, flashes the image and restores your layout when the keyboard reconnects.

Flashing does not erase the emulated EEPROM, so your keyboard layout normally survives, but in case it doesn't, you can restore them if you backed it up in previous step: **File** > **Load saved layout**.

### Entering the bootloader manually

If you prefer, or if the automatic reboot fails, you can enter the bootloader yourself:

- In Vial: **Security > Reboot to bootloader**.
- Or hold **Esc** while plugging the keyboard into the computer.

## Reverting to stock

The stock firmware `radiance65-stock.vfw` in the release assets is the unmodified firmware: `DEBOUNCE`: 1ms, `DEBOUNCE_TYPE`: `sym_defer_g`, console and command chords enabled. Flash it the same way to undo any changes.

## Disclaimer

* I am not responsible for bricked devices. Proceed at your own risk.
* I have tested the firmware on my keyboard, but I can't guarantee it will work on yours.
