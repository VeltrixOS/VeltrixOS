# VeltrixOS 🐧

An operating system for users who value system efficiency and speed, powered by **VPM**, a custom package manager that builds everything from source.

> **Status:** early development. Current release: `0.2.0` (experimental ISO).

## 🚀 Key features
* **Zero bloat:** engineered for raw performance and maximum efficiency.
* **VPM (VeltrixOS Package Manager):** independent package manager built from scratch in pure C++.
* **Built for power users:** full control over compilation and the system environment.

## 🧱 System
* Architecture: x86_64, glibc
* Kernel: `6.18.10-VeltrixOS`
* Init: systemd, bootloader: GRUB

## 📁 Repository layout
| Path | Contents |
|------|----------|
| `src/` | Projects, one folder each (own `src/`, `include/`, `tests/`) |
| `config/`, `patches/`, `packaging/` | Configuration, patches, packaging |
| `scripts/iso/` | ISO build scripts |
| `tools/` | Helper scripts |
| `tests/` | System-level tests |
| `docs/` | Documentation |

## 🔗 Related repositories
* [VeltrixOS-Package-Manager](https://github.com/VeltrixOS/VeltrixOS-Package-Manager): VPM source
* [VeltrixOS-Website](https://github.com/VeltrixOS/VeltrixOS-Website): official website

## 🤝 Contributing
See [CONTRIBUTING.md](.github/CONTRIBUTING.md). Report vulnerabilities privately, see [SECURITY.md](SECURITY.md).

## 📄 License
Apache License 2.0, see [LICENSE](LICENSE).

---
*Developed by @zawix21*
