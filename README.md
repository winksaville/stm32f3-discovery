# `stm32f3-discovery`

Board support package for the [STM32F3DISCOVERY][stm32f3discovery] board.

![Rust](https://github.com/rubberduck203/stm32f3-discovery/workflows/Rust/badge.svg)
[![crates.io](https://img.shields.io/crates/d/stm32f3-discovery.svg)](https://crates.io/crates/stm32f3-discovery)
[![crates.io](https://img.shields.io/crates/v/stm32f3-discovery.svg)](https://crates.io/crates/stm32f3-discovery)
[![docs.rs](https://docs.rs/stm32f3-discovery/badge.svg)](https://docs.rs/stm32f3-discovery)

## Dependencies

To build embedded programs using this you'll need:

- Rust 1.31 or newer toolchain
- `rust-std` components (pre-compiled `core` crate) for the ARM Cortex-M
  target.

``` console
$ cargo install cargo-generate
$ rustup target add thumbv7em-none-eabihf
```

For more info on working with embedded Rust, see the [Embedded Rust Book][book] and the [Discovery Book][discovery-book].

## Documentation

https://docs.rs/stm32f3-discovery

For the board specific functionality this crate adds, see:
 - The [examples directory](./examples).
 - The [leds module documentation](https://docs.rs/stm32f3-discovery/0.3.4/stm32f3_discovery/leds/index.html)
 - The [button module documentation](https://docs.rs/stm32f3-discovery/0.3.4/stm32f3_discovery/button/index.html)
 - The [compass module](https://docs.rs/stm32f3-discovery/0.3.4/stm32f3_discovery/compass/index.html) and [lsm303dhlc documentation](https://docs.rs/lsm303dlhc/0.2.0/lsm303dlhc/)

## VS Code

This repository includes launch configurations for debugging CortexM programs with Visual Studio Code in the `.vscode/` directory.  
See [.vscode/README.md](./.vscode/README.md) for more information.  

To debug one of the examples, open the example source file in the editor and press F5.

# License

This template is licensed under either of

- Apache License, Version 2.0 (http://www.apache.org/licenses/LICENSE-2.0)
- MIT license (http://opensource.org/licenses/MIT)

at your option.

## Contribution

Unless you explicitly state otherwise, any contribution intentionally submitted
for inclusion in the work by you, as defined in the Apache-2.0 license, shall be
dual licensed as above, without any additional terms or conditions.

<!-- references -->
[stm32f3discovery]: https://www.st.com/en/evaluation-tools/stm32f3discovery.html#
[book]: https://rust-embedded.github.io/book
[discovery-book]: https://rust-embedded.github.io/discovery/

## Changelog

### 0.5.0

- Updated dependencies
- `InputSwitch for UserButton` now has an `Error` type of `core::convert::Infallible` instead of `()`

### 0.4.0

- Updated `stm32f3xx-hal` from 0.4.0 to 0.4.1
- Allows setting `TriggerMode` on the user button (breaking change)
- Removes deprecated `GpioE` struct and `Leds::init` function

### 0.3.4

- Introduced `Compass` struct and implemented [Accelerometer trait](https://crates.io/crates/accelerometer).
- Add `Leds::new` function and deprecate `Leds::init`.

### 0.3.3

- Add `wait_for_interrupt` function
- Upgrade `switch-hal` version

### 0.3.2

- Re-export `lsm303dhlc` driver