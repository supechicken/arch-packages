# arch-packages

Personal collection of custom Arch Linux package recipes (`PKGBUILD`s).

## Packages

| Directory | Package | Description |
| --- | --- | --- |
| [`cage-custom/`](cage-custom/) | `cage-custom` | Custom build of Cage, a kiosk compositor for Wayland. |
| [`linux-api-headers/`](linux-api-headers/) | `linux-api-headers` | Minimal placeholder package recipe. |
| [`linux-custom/`](linux-custom/) | `linux-custom` | Custom x86-64 Linux kernel and headers, built with LLVM/Clang and custom configuration and patches. |
| [`linux-firmware/`](linux-firmware/) | `linux-firmware`, `amd-ucode` | Linux firmware and AMD CPU microcode packages. |
| [`linux-intel-lts/`](linux-intel-lts/) | `linux-intel-lts` | Intel LTS kernel, headers, and documentation packages. |
| [`nginx-custom/`](nginx-custom/) | `nginx-custom` | Nginx package with additional modules, including Brotli, Zstandard, digest authentication, and GeoIP2. |

## Building a package

Install the standard Arch Linux build tools:

```sh
sudo pacman -S --needed base-devel
```

Build and install a package from its directory:

```sh
cd linux-custom
makepkg -si
```

Build without installing:

```sh
makepkg -s
```

Review the relevant `PKGBUILD` and sources before building. Build dependencies, options, and setup vary by package.

## Important notes

- The recipes primarily target `x86_64` Arch Linux.
- `linux-custom` and `linux-intel-lts` build kernel packages. Check their package conflicts and installation implications before use.
- The `linux-custom` recipe signs the kernel using `/etc/secureboot/DB.key` and `/etc/secureboot/DB.crt`. Configure those files or adapt the recipe before building.
- Some recipes use `SKIP` checksums. Verify upstream sources and review changes before installing packages.

## License

No repository-wide license is specified. Refer to each package recipe and its upstream project for package-specific licensing information.
