<div align="center">

# VeltrixOS

**A source-based Linux distribution built for speed, control and zero bloat.**

Everything is compiled on your machine by **VPM**, a custom package manager written in pure C++.

[![Download](https://img.shields.io/badge/download-ISO-orange?style=for-the-badge)](https://veltrixos.vercel.app/download)
[![Release](https://img.shields.io/badge/release-0.2.0%20experimental-blue?style=for-the-badge)](https://github.com/VeltrixOS/VeltrixOS/releases/tag/2026-11-03)
[![License](https://img.shields.io/badge/license-Apache--2.0-green?style=for-the-badge)](LICENSE)
[![CI](https://img.shields.io/github/actions/workflow/status/VeltrixOS/VeltrixOS/ci.yml?branch=main&style=for-the-badge&label=CI)](https://github.com/VeltrixOS/VeltrixOS/actions/workflows/ci.yml)

![Kernel](https://img.shields.io/badge/kernel-6.18.10-informational?style=flat-square&logo=linux&logoColor=white)
![Arch](https://img.shields.io/badge/arch-x86__64-informational?style=flat-square)
![libc](https://img.shields.io/badge/libc-glibc-informational?style=flat-square)
![Language](https://img.shields.io/badge/VPM-C%2B%2B-00599C?style=flat-square&logo=cplusplus&logoColor=white)

[Status](#-status) · [Features](#-features) · [System](#-system) · [VPM](#-vpm) · [Layout](#-repository-layout) · [Contributing](#-contributing)

</div>

---

## 📍 Status

> [!WARNING]
> VeltrixOS is in **early development**. The current release is an **experimental** ISO, not meant for production use.

| | |
|---|---|
| **Release** | `0.2.0` (experimental ISO) |
| **VPM** | `v1.0.1` preview |
| **Kernel** | `6.18.10-VeltrixOS` |
| **Download** | [veltrixos.vercel.app/download](https://veltrixos.vercel.app/download) |

## ✨ Features

<table>
<tr>
<td width="33%" valign="top">

### ⚡ Zero bloat
Engineered for raw performance and maximum efficiency. Nothing you did not ask for.

</td>
<td width="33%" valign="top">

### 🔨 Built from source
Every package is compiled locally, with full control over flags and the build environment.

</td>
<td width="33%" valign="top">

### 📦 Custom package manager
VPM is independent and written from scratch in pure C++.

</td>
</tr>
</table>

## 🧱 System

| Component | Choice |
|-----------|--------|
| Architecture | `x86_64` |
| C library | `glibc` |
| Kernel | `6.18.10-VeltrixOS` |
| Init | `systemd` |
| Bootloader | `GRUB` |
| Package manager | `VPM` |

## 📦 VPM

**VPM** (VeltrixOS Package Manager) is a source-based package manager written in C++, built around Portage-style ebuilds. It resolves dependency graphs offline, builds packages in parallel and can install from previously built binary packages.

| | Feature | What it does |
|---|---------|--------------|
| 🌐 | **Offline resolver** | Scans the local ebuild tree directly. No remote API calls, so large dependency graphs do not depend on the network. |
| ⚙️ | **Parallel builds** | A scheduler builds packages concurrently and respects the dependency build order. |
| 📦 | **Binary packages** | Every build can be kept as a `.vpk` archive and reinstalled without compiling. |
| 🩹 | **Self-healing builds** | `AutoFixer` recognizes common build failures (missing headers, bad compiler flags) and retries. `HeuristicEngine` learns which fix worked for which error. |
| ⏪ | **Snapshots & rollback** | System state is snapshotted before a transaction. `vpm rollback` restores it. |
| 🧮 | **VDRA job limits** | Detects CPUs and RAM (cgroup aware) and limits build jobs so large builds do not exhaust the machine. |

### Quick start

```bash
vpm sync                  # fetch the ebuild tree and index
vpm search <pattern>      # find a package
vpm install <package>     # build and install it
```

<details>
<summary><code>&lt;/&gt;</code> All commands</summary>

<br>

| Command | Description |
|---------|-------------|
| `vpm install <pkg>` | Install or update a package |
| `vpm remove <pkg>` | Remove a package |
| `vpm update <pkg>` | Update a package to the newest version in the tree |
| `vpm upgrade` | Upgrade all installed packages |
| `vpm rollback` | Undo the last operation (snapshot) |
| `vpm search <pattern>` | Search available packages |
| `vpm info <pkg>` | Package metadata and install state |
| `vpm files <pkg>` | List files owned by a package |
| `vpm list-installed` | List installed packages |
| `vpm depclean` | Remove packages no longer needed |
| `vpm sync` | Synchronize the full ebuild tree |
| `vpm sync-index` | Rebuild the repository index |
| `vpm graph <pkg>` | Export the dependency graph (Graphviz DOT) |
| `vpm check` | Verify database and file consistency |
| `vpm clean` | Clear download and build caches |

Run `vpm --help` for the full list.

</details>

<details>
<summary><code>&lt;/&gt;</code> Configuration</summary>

<br>

VPM reads `vpm.conf`, `make.conf` and `repos.conf` from `/etc/vpm`.

| Option | Default | Effect |
|--------|---------|--------|
| `COMMITS` | `yes` | Keep rollback snapshots. `no` saves disk, but `vpm rollback` stops working. |
| `BINPKG` | `yes` | Keep a `.vpk` of every build. `no` saves disk, but a reinstall recompiles. |
| `VDRA` | on | `VDRA=off` disables the RAM/CPU job limits. |

</details>

<details>
<summary><code>&lt;/&gt;</code> Build VPM from source</summary>

<br>

```bash
meson setup build
ninja -C build
meson test -C build
```

| | Dependencies |
|---|---|
| **Required** | `sqlite3`, `glib-2.0`, `libcurl`, `openssl`, `libarchive`, `pkg-config`, `meson`, `ninja` |
| **Optional** | `ostree-1`, `gpgme`, `appstream`, `libcap` (each one disables its feature when missing) |

</details>

VPM source: [VeltrixOS-Package-Manager](https://github.com/VeltrixOS/VeltrixOS-Package-Manager)

## 📁 Repository layout

<details open>
<summary><code>&lt;/&gt;</code> Directory map</summary>

<br>

| Path | Contents |
|------|----------|
| [`src/`](src) | Projects, one folder each (own `src/`, `include/`, `tests/`) |
| [`config/`](config) | System configuration |
| [`patches/`](patches) | Patches applied to upstream sources |
| [`packaging/`](packaging) | Packaging files |
| [`scripts/iso/`](scripts/iso) | ISO build scripts |
| [`tools/`](tools) | Helper scripts (`bash/`, `python/`) |
| [`tests/`](tests) | System-level tests: `low-level`, `userland`, `gui`, `cybersecurity` |
| [`docs/`](docs) | Documentation |

</details>

## 🤝 Contributing

Contributions are welcome.

1. Read [CONTRIBUTING.md](.github/CONTRIBUTING.md).
2. Open or pick an [issue](https://github.com/VeltrixOS/VeltrixOS/issues).
3. Send a pull request using the template.

> [!IMPORTANT]
> Do not report vulnerabilities in public issues. Follow [SECURITY.md](SECURITY.md).

## 📄 License

Released under the **Apache License 2.0**. See [LICENSE](LICENSE).

<div align="center">

<sub>Developed by <a href="https://github.com/zawix21">@zawix21</a></sub>

</div>
