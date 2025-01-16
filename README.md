# Petricore Firmware

This project is built upon a template generated through the [RMK](RMK.md) project.

## Building
The aim of building is to produce a hex binary or a UF2 binary (dependent on flashing mechanism). This repo relies on cargo-make and to unblock your local development, run the following command:

Note: This step should be tackled as a build dependency but is currently not recognised in the Cargo.toml file. As Mrinal gains more experience with Rust, he will try to solve this. If Mrinal no longer exists, do your best.
```shell
cargo install cargo-make
```
Run the following command at the root of the repo:
```shell
cargo make uf2 --release
```

This builds the repo, its packages and produces both `petricore_firmware.hex` and `petricore_firmware.uf2`.

## Deploying to PCB Board

[Theoretical instructions for debug probe](https://haobogu.github.io/rmk/user_guide/3_flash_firmware.html#use-debug-probe)