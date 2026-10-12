# Logos Hello World

A minimal "hello world" UI module for [Logos Basecamp](https://logos.co). It's a single QML file (no C++), packaged as an `.lgx` that shows up as a sidebar tab.

## Quick start

Download the latest `.lgx` from [Releases](https://github.com/hackyguru/logos-hello-world/releases) and install it in Basecamp via **Modules → Install LGX Package**. To build it yourself, read on.

## Prerequisites

- [Nix](https://nixos.org/download/) with flakes enabled (`experimental-features = nix-command flakes` in `~/.config/nix/nix.conf`)
- [Logos Basecamp](https://github.com/logos-co/logos-basecamp/releases)

## Build

```bash
nix flake update        # first time only
nix build '.#lgx-portable' --out-link result-portable
```

## Install in Basecamp

Each build produces an `.lgx` file at `result-portable/*.lgx`. In [Logos Basecamp](https://github.com/logos-co/logos-basecamp/releases), open **Modules → Install LGX Package** and pick the file.

## What's here

- [`Main.qml`](Main.qml): the UI
- [`metadata.json`](metadata.json): module name (`hello_world`), type (`ui_qml`) and version
- [`flake.nix`](flake.nix): builds the module with [`logos-module-builder`](https://github.com/logos-co/logos-module-builder)
