# Example of how to build ICED using nix

This repository provides example for building counter example for [ICED](https://github.com/iced-rs/iced) GUI framework.

Code is taken from the repo, with minor modifications.

In order to build those steps were needed:

1. Initilize the shell by running `nix develop`.

```
nix develop
```

3. Generate lock file. Result already in repo, so it is needed only then you will be recreating it in your project.

```
cargo check
```

3. Generate Cargo.nix. Again result already in repo, so it is needed only then you will be recreating it in your project.

```
nix run github:cargo2nix/cargo2nix
```

4. nix build

```
nix build
```

resulting executable will apprear as `./result-bin/bin/counter`

## Caveats

flake.nix provided by this repo will only build for wayland systems. Building for x11 will require extra effort.


## Counter

The classic counter example explained in the [`README`](../../README.md).

The __[`main`]__ file contains all the code of the example.

<div align="center">
  <img src="https://iced.rs/examples/counter.gif">
</div>

You can run it with `cargo run`:
```
cargo run --package counter
```

The web version can be run with [`trunk`]:

```
cd examples/counter
trunk serve
```

[`main`]: src/main.rs
[`trunk`]: https://trunkrs.dev/
