# libgoblin [![Build Status](https://travis-ci.org/m4b/goblin.svg?branch=master)](https://travis-ci.org/m4b/goblin) [![Current Crates.io Version](https://img.shields.io/crates/v/goblin.svg)](https://crates.io/crates/goblin)

![say the right words](https://s-media-cache-ak0.pinimg.com/736x/1b/6a/aa/1b6aaa2bae005e2fed84b1a7c32ecb1b.jpg)

### Documentation

https://docs.rs/goblin/

### Usage

Goblin requires `rustc` 1.15.

Add to your `Cargo.toml`

```toml
[dependencies]
goblin = "0.0.9"
```

### Features

* awesome crate name
* the best, most feature complete ELF64/32 implementation, ever - now with auto type punning!
* zero-copy, cross-platform, endian-aware, 32/64 bit Mach-o parser - wow!
* PE 32-bit support for binary analysis (raw writers are in the works)
* many cfg options - it will make your head spin, and make you angry when reading the source!
* goblins (TBA)
* tests

`libgoblin` aims to be your one-stop shop for binary parsing, loading,
and analysis.

### Use-cases

Here are some things you could do with this crate (or help to implement so they could be done):

1. write a compiler and use it to generate binaries (all ELF32/64 have [`Pwrite`](https://github.com/m4b/scroll) derived)
2. write a binary analysis tool which loads, parses, and analyzes various binary formats, e.g., [panopticon](https://github.com/das-labor/panopticon)
3. write a [semi-functioning dynamic linker](http://github.com/m4b/dryad)
4. write a [kernel](https://github.com/redox-os/redox) and load binaries using `no_std` cfg. I.e., it is essentially just struct and const defs (like a C header) - no fd, no output, no std.
5. write a bin2json tool (http://github.com/m4b/bin2json), because why shouldn't binary formats be in JSON?

### Cfgs

`libgoblin` is designed to be massively configurable. The current flags are:

* elf64 - 64-bit elf binaries
* elf32 - 32-bit elf binaries
* mach64 - 64-bit mach-o `repr(C)` struct defs
* mach32 - 32-bit mach-o `repr(C)` struct defs
* pe32 - 32-bit PE binary parser
* archive - a Unix Archive parser
* endian_fd - parses according to the endianness in the binary
* std - to allow `no_std` environments
* pe64 - wip
