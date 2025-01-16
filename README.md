# Petricore Firmware
This project is built upon a template generated through the [RMK](RMK.md) project.

## Building
The aim of building is to produce a hex binary (flash via debug probe) or a UF2 binary (flash via USB bootloader). 

### Pre-Requisites
This repo relies on [cargo-make](https://crates.io/crates/cargo-make) and to unblock your local development, run the following command:

```shell
cargo install cargo-make

Note: This step^ should be tackled as a build dependency but is currently not recognised in the Cargo.toml file. As Mrinal gains more experience with Rust, he will try to solve this. If Mrinal no longer exists, do your best.
```

### Supported targets
Currently as we're targetting the firmware for the `nrf52840`, rmkit put the `thumbv7em-none-eabihf` target in our [rust-toolchain.toml](rust-toolchain.toml). If this isn't the intended processor or we need to build more varietals, please add it there.
For more information on bare-metal chips, see [Platform support](https://doc.rust-lang.org/nightly/rustc/platform-support.html)

### Build binary
Run the following command at the root of the repo:
```shell
cargo make uf2
```
This builds the repo, its packages and produces both `petricore_firmware.hex` and `petricore_firmware.uf2`. By default, it builds using dev options specified in the [Cargo.toml](Cargo.toml). Add `--release` to build a release configuration of the binary


## Deploying to PCB Board
[Theoretical instructions for debug probe](https://haobogu.github.io/rmk/user_guide/3_flash_firmware.html#use-debug-probe)