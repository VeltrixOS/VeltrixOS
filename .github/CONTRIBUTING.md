<div align="center">

# 🤝 Contributing to VeltrixOS

**Thank you for helping keep the system fast, modern and light.**

[![Issues](https://img.shields.io/badge/open-an%20issue-blue?style=for-the-badge)](https://github.com/VeltrixOS/VeltrixOS/issues/new/choose)
[![PRs](https://img.shields.io/badge/pull%20requests-welcome-green?style=for-the-badge)](https://github.com/VeltrixOS/VeltrixOS/pulls)
[![License](https://img.shields.io/badge/license-Apache--2.0-green?style=for-the-badge)](../LICENSE)

[Workflow](#-workflow) · [Coding rules](#-coding-rules) · [Layout](#-repository-layout) · [Commits](#-commit-messages) · [Security](#-security)

</div>

---

## 🚀 Workflow

1. **Discuss.** Pick an open [issue](https://github.com/VeltrixOS/VeltrixOS/issues) or open one to talk about your idea first.
2. **Fork** the repository and create a branch from `main`.
3. **Build and test** your change. See the project's own README for commands.
4. **Open a pull request** using the template and paste your build and test output.

> [!TIP]
> Small, focused pull requests get reviewed faster than large ones.

## 🧪 Coding rules

| Rule | Details |
|------|---------|
| **Language** | VPM is written in pure C++. Use modern C++ (C++20 or newer). |
| **No bloat** | Keep code efficient, fast and optimized. No dependency for a few lines of code. |
| **Independence** | Package compilation stays independent from, and sandboxed from, the host system. |
| **Safety** | No memory leaks. Check the result of every system call. |
| **Root cause** | Fix the cause of a bug. Do not hide it by disabling a feature or a USE flag. |

## 📁 Repository layout

<details open>
<summary><code>&lt;/&gt;</code> Directory map</summary>

<br>

| Path | Contents |
|------|----------|
| `src/<project>/` | One folder per project (for example `greeter`), each with its own `src/`, `include/` and `tests/` |
| `config/`, `patches/`, `packaging/` | System configuration, patches and packaging files |
| `scripts/iso/` | ISO build scripts |
| `tools/` | Helper scripts (`bash/`, `python/`) |
| `tests/` | System-level tests: `low-level`, `userland`, `gui`, `cybersecurity` |
| `docs/` | Documentation |

Inside a project, headers (`.hpp`) go to its `include/` and sources (`.cpp`) to its `src/`.

</details>

## ✍️ Commit messages

Short imperative subject, about 50 characters. Add a body when the reason is not obvious.

<details>
<summary><code>&lt;/&gt;</code> Examples</summary>

<br>

```text
✅ Add greeter project skeleton
✅ Fix resolver rebuilding unrelated slots
❌ fixed stuff
❌ Updated files and also changed things
```

</details>

## 🔒 Security

> [!IMPORTANT]
> Do not report vulnerabilities in public issues. Follow [SECURITY.md](../SECURITY.md).

## 📄 License

By contributing you agree that your work is released under the **Apache License 2.0**. See [LICENSE](../LICENSE).
