# hermit-dtb

[![Documentation](https://img.shields.io/badge/docs-latest-blue.svg)](https://docs.rs/hermit-dtb/latest/hermit_dtb/)
![License](https://img.shields.io/badge/license-MIT%2FApache--2.0-blue)

Crate to parse Flattened Device Trees (FDT)/Device Tree Blobs (DTB) in a `no_std` environment.
Performs no dynamic memory allocations and can therefore be universally used for operating system development.
Originally written for the AArch64 port of [HermitCore-rs](https://github.com/hermitcore/libhermit-rs), hence the name.

## Features
* Enumerating subnodes of a given path.
* Enumerating properties of a given path.
* Getting the data of a specific property.
* Finding incomplete paths (e.g. looking for `/uart@` reliably yields `/uart@fe001000` if that is the only UART device).
* Written in mostly safe Rust.
  `unsafe` is only used when accessing the in-memory DTB in the first place (unavoidable).
* `parse_dtb` example tool to demonstrate the features.

## ToDo
* Implement an iterator for the memory reservation block.
* Implement a method to fetch the `boot_cpuid_phys` value.

## References
* [Devicetree Specification 0.2](https://github.com/devicetree-org/devicetree-specification/releases/tag/v0.2)

## Contact
The hermit-dtb crate has been written by Colin Finck (colin.finck@rwth-aachen.de).
