# Personal Arch AUR

This repository tracks personal PKGBUILDs that are either not available in the official Arch User Repository or diverge from the upstream packages. Each directory contains everything needed to build and install the package with the standard Arch packaging toolchain.

## Packages

| Package  | Version | Description |
|----------|---------|-------------|
| `binance` | 2.0.2 | Desktop client for the Binance cryptocurrency exchange, re-packaged from the upstream Debian build. |
| `dbeaver` | 25.2.4 | Community edition of DBeaver, a universal SQL client for database developers and administrators. |

## Building

All packages follow the usual Arch workflow:

```bash
cd <package>
updpkgsums          # optional, only when sources change
makepkg -si
```

The `makepkg` invocation resolves dependencies, builds the package, and installs it into the local system. To inspect or edit a package before building, modify the corresponding `PKGBUILD` (and any auxiliary files) in the package directory.

## Repository Layout

- `binance/` — PKGBUILD for the Binance Electron desktop app; includes a `check()` routine that verifies upstream checksums before packaging.
- `dbeaver/` — PKGBUILD plus helper scripts, desktop entries, hooks, and install scripts required to ship the DBeaver Community edition with bundled plugins.

Feel free to fork or cherry-pick individual PKGBUILDs if they are useful in your own AUR workflow.
