# Piantor Pro BT ZMK Configuration

This repository contains my ZMK configuration for a [Piantor Pro BT from
Keebart](https://www.keebart.com/products/piantor-wireless).

I own a regular wired 5x6 Piantor Pro for at home configured via QMK, and a bluetooth one for on the
go configured based on this configuration. Both configurations are identical except for the couple
notes below.

Moreover I emulate this layout using [kanata](https://github.com/jtroo/kanata) on my laptops. The
configurations for this can be found in my [Nix setup
repository](https://github.com/f4z3r/nix/blob/master/nixos/kanata.nix). In that setup I have
additional macros for QoL. I rarely use them though.

## Configuration

Most of the configuration is done via [Keymap Editor](https://nickcoutsos.github.io/keymap-editor/)
with some setting tweaks done by hand.

## Layout

![Layout](./assets/piantor_pro_bt.svg)

> [!NOTE]
> The grave escape is modified to print an underscore (`_`) when right-shifted on the base layer.
> Additionally, on the BT version, the "homerow mods" will only trigger on keys of the other hand.

> [!NOTE]
> The `my_double_quote` macro prints a double quote with a space (to have a full double quote
> sequence on US intl layouts), and the `my_quote` macro prints a single quote with a space.

## Settings

Generally, the tapping for tap/hold, mod/tap, or tap/layer is setup to have a tapping term at 150ms
and a quick tap term of 150ms. I use:

- `balanced` tap behaviour with `hold-trigger-on-release` on tap/hold for the homerow mods
- `hold-preferred` tap behaviour with `hold-trigger-on-release` on mod/tap for shifted enter
- `tap-preferred` tap behaviour on tap/layer.

This configuration perfectly matches my typing style for homerow mods and how I use my mod/tap
"Enter RS" key on the right thumb. It allows for the typical rolling movements of the Colemak layout
while easily allowing to combine mods on one hand with a keys press of the other hand.

## Flashing

> [!WARNING]
> If the no new device shows in `lsblk` when connecting and reseting it, try connecting to a
> different USB port on the computer.

1. Connect the keyboard to your computer via USB-C.
2. Double press the SIM entry at the back of the keyboard to reset it.
3. Mount the keyboard as a drive: `sudo mount /dev/sdc /mnt/drive/`
4. Copy the correct firmware to it, for instance for the right side:
   ```bash
   sudo cp nice_view-piantor_pro_bt_right-zmk.uf2 /mnt/drive/
   ```
5. Wait between 15 to 30 seconds for the firmware to flash. The screen will flash when completed.
6. Unmount the drive: `sudo umount -l /mnt/drive`
7. Repeat for the other side.
