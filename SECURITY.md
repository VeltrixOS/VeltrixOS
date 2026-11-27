<div align="center">

# 🔒 Security Policy

**Found a vulnerability in VeltrixOS or VPM? Report it privately. Do not open a public issue.**

[![Report](https://img.shields.io/badge/report-private%20advisory-red?style=for-the-badge)](https://github.com/VeltrixOS/VeltrixOS/security/advisories/new)
[![Response](https://img.shields.io/badge/first%20reply-within%207%20days-blue?style=for-the-badge)](#-what-happens-next)

[Supported versions](#-supported-versions) · [Report](#-how-to-report) · [Scope](#-scope) · [Next](#-what-happens-next)

</div>

---

> [!CAUTION]
> Public issues, pull requests and discussions are visible to everyone. A vulnerability posted there can be abused before a fix exists.

## 📍 Supported versions

VeltrixOS is in **early development**. Only the newest state receives security fixes.

| Version | Supported |
|---------|:---------:|
| `main` | ✅ |
| `0.2.0` (experimental) | ✅ |
| older | ❌ |

## 📨 How to report

1. Open the **[private advisory form](https://github.com/VeltrixOS/VeltrixOS/security/advisories/new)**
   (**Security** tab → **Report a vulnerability**).
2. Fill in the details below.
3. Submit. Only the maintainers can see the report.

<details open>
<summary><code>&lt;/&gt;</code> What to include</summary>

<br>

| Field | Example |
|-------|---------|
| **Component** | VPM, package build, kernel config, ISO scripts |
| **Versions** | `cat /etc/os-release` and the VPM version |
| **Steps to reproduce** | Exact commands, in order |
| **Impact** | What an attacker can do: code execution, privilege escalation, file overwrite |
| **Logs** | Full error output, stack trace or crash dump |
| **Fix idea** | Optional: a patch or a suggested change |

</details>

## 🎯 Scope

| In scope | Out of scope |
|----------|--------------|
| VPM: downloads, signature checks, build sandbox, file installation | Bugs in upstream software we only package (report them upstream) |
| Package recipes and patches in this repository | Social engineering or physical access |
| Kernel configuration and boot setup | Denial of service by running out of your own disk or RAM |
| ISO build scripts | Issues in unsupported versions |

## ⏱️ What happens next

| Step | When |
|------|------|
| First reply | within **7 days** |
| Fix prepared and tested | as soon as possible |
| Fix published, report disclosed | after the patch is available |

We credit reporters in the advisory unless you prefer to stay anonymous.

<div align="center">

<sub>Thank you for helping keep VeltrixOS safe.</sub>

</div>
