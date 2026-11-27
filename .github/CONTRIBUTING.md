# Contributing to VeltrixOS

Thank you for your interest in VeltrixOS! We want to keep the system fast, modern and light.

## Coding rules
* **Language:** VPM is written in pure C++. Use modern C++ (C++20 or newer).
* **No bloat:** keep code efficient, fast and optimized.
* **Independence:** package compilation stays independent from and sandboxed from the host system.
* **Safety:** no memory leaks, check every system call result.

## Repository layout
| Path | Contents |
|------|----------|
| `src/<project>/` | One folder per project (for example `greeter`). Each has its own `src/`, `include/` and `tests/`. |
| `config/`, `patches/`, `packaging/` | System configuration, patches and packaging files |
| `scripts/iso/` | ISO build scripts |
| `tools/` | Helper scripts (`bash/`, `python/`) |
| `tests/` | System-level tests (`low-level/`, `userland/`, `gui/`, `cybersecurity/`) |
| `docs/` | Documentation |

Inside a project: headers (`.hpp`) go to its `include/`, sources (`.cpp`) to its `src/`.

## How to contribute
1. Look at open **Issues**, or open one to discuss your idea first.
2. Fork the repository and create a branch.
3. Build and test your change. See the project's own README for commands.
4. Open a **Pull Request** using the template and paste your build/test output.

## Commit messages
Short imperative subject (about 50 characters), for example `Add greeter project skeleton`. Add a body when the reason is not obvious.

## Security
Do not report vulnerabilities in public issues. See [SECURITY.md](../SECURITY.md).
