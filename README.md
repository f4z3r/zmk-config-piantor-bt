# Piantor Pro BT ZMK Configuration

This repository contains my ZMK configuration for a [Piantor Pro BT from
Keebart](https://www.keebart.com/products/piantor-wireless).

I own a regular wired 5x6 Piantor Pro for at home configured via QMK, and a bluetooth one for on the
go configured based on this configuration. Both configurations are identical except for the couple
notes below.

## Configuration

Most of the configuration is done via [Keymap Editor](https://nickcoutsos.github.io/keymap-editor/)
with some setting tweaks done by hand.

## Layout

### COLEMAK

![Colemak Layer](./assets/colemak.png)

> [!NOTE]
> The grave escape is modified to print an underscore (`_`) when right-shifted. Additionally, on the
> BT version, the "homerow mods" will only trigger on keys of the other hand.

### SYMBOLS

![Symbols Layer](./assets/symbols.png)

> [!NOTE]
> The `M0` macro prints a double quote with a space (to have a full double quote sequence on US intl
> layouts), and the `M1` macro prints a single quote with a space.

### NUMBERS

![Numbers Layer](./assets/numbers.png)

### MOVEMENT

![Movement Layer](./assets/movement.png)

> [!NOTE]
> On the BT version, the right most three keys serve to define the bluetooth profile. Specifically,
> from top to bottom:
> - Clear bluetooth profile
> - Next bluetooth profile
> - Previous bluetooth profile

## Settings

Generally, the tapping for tap/hold or tap/layer is setup to have a tapping term at 150ms and a
quick tap term of 150ms. I use hold-preferred on tap/hold and tap-preferred tap/layer.
