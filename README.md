[![GitHub license](https://img.shields.io/github/license/cartheur/aeon-tokens-iot)](https://github.com/cartheur/aeon-tokens-iot/blob/main/LICENSE)
[![GitHub issues](https://img.shields.io/github/issues/cartheur/aeon-tokens-iot)](https://github.com/cartheur/aeon-tokens-iot/issues)

# aeon-tokens-iot
A project that interweaves emotional exchange with aeon logic to generate tokens as an encapsulation of a human's experience.

## Building

### Install dependencies:

```sh
arduino-cli core install arduino:samd
cargo install cargo-binutils cargo-make
rustup component add llvm-tools-preview
```

### Build & flash:

```sh
cargo build --release
rust-objcopy -O binary target/thumbv6m-none-eabi/release/aeon-array-33-iot target/aeonarray.bin
arduino-cli upload -i target/aeonarray.bin -b arduino:samd:nano_33_iot -p /dev/ttyACM0
```
### Automated build and flash

To save time, use the makefile for cargo-make so you can just run following command while your arduino in bootloader mode.

```sh
cargo make flash
```

### NOTE
**After flashing, serial communication between your arduino and pc will be gone. So if you want to put your arduino into bootloader mode you just need to press `rst` button on the board twice.**
Then you will be able to flash your application to arduino again.
