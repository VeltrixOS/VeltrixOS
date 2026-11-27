<div align="center">

# VeltrixOS

**A source-based Linux distribution built for speed, control and zero bloat.**

Everything is compiled on your machine by **VPM**, a custom package manager written in pure C++.

[![Release](https://img.shields.io/badge/release-0.2.0%20experimental-blue?style=for-the-badge)](#-status)
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

**VPM** (VeltrixOS Package Manager) builds packages from source.

```bash
# install a package (add -y to answer yes to every prompt)
vpm install <package>
vpm install <package> -y
```

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
