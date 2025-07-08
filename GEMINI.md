# ZMK Firmware Build Instructions

This document provides the commands to build the ZMK firmware for the a4 keyboard.

## Prerequisites

- A working ZMK development environment. See the [ZMK documentation](https://zmk.dev/docs/development/setup) for setup instructions.
- The `west` tool is initialized. If you have not done so, run:
  ```bash
  west init -l config
  west update
  ```

## Build Commands

To build the firmware for the left and right halves of the keyboard, run the following commands from the root of the project:

### Left side

```bash
west build -d build/left -b akdk_bt1 -- -DSHIELD=a4_left
```

### Right side

```bash
west build -d build/right -b akdk_bt1 -- -DSHIELD=a4_right
```

## Flashing

After a successful build, the firmware files will be located in `build/left/zephyr/zmk.uf2` and `build/right/zephyr/zmk.uf2`.

Follow the standard ZMK flashing procedure to flash the firmware to your keyboard.
