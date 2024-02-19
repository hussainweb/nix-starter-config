# Nix Starter Config

This is a simple template to set up system configuration using Nix. It contains configuration entry points for [NixOS](https://nixos.org/), [Nix-Darwin](https://github.com/LnL7/nix-darwin), and [Home Manager](https://github.com/nix-community/home-manager/).

## How to use this?

Simply download or clone this repository and begin editing. Feel free to remove sections you don't need. For example, if you don't need nix-darwin, remove it from `flake.nix` from `inputs` and the section with `darwinConfigurations`. And then you can also remove the `nix-darwin` directory.

### More documentation

This starter configuration is primarily influenced by [Misterio77's nix-starter-config](https://github.com/Misterio77/nix-starter-configs). The main reason I am writing this is because that does not have nix-darwin configuration. I found myself trying to understand how to incrementally add support for my systems and package configuration. That is why this template is very similar to the original starter configuration. As such, you can refer to the documentation in that repository for more details.

## Running the flakes

To run `nix-darwin`, use this command:

```bash
nix run nix-darwin -- build --flake .#simple
```

Similarly, to run `home-manager, use the command:

```bash
nix run home-manager -- build --flake .#simple
```

Replace `simple` with the entry point in `darwinConfigurations` or `homeConfigurations` you want to run. The template uses `simple` but you can and should replace it with your machine's hostname or whatever else you want to call it.

When the build is successful, replace `build` with `switch` to make the changes effective. You don't need to run `build` explicitly as `switch` will do that as well. This just helps in testing.

## Contribution

Your contribution is very welcome. Primarily, I am looking to improve the template by making it more flexible (more systems) and/or making it more customizable. I am also looking to improve the documentation here, which is almost non-existent right now.
