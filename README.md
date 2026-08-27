# 🛡️ Tridorian ZTNA - Release Logs

Welcome to the official release repository for **Tridorian ZTNA (Zero Trust Network Access)**. This repository tracks all versions, updates, and major milestones of the Tridorian security ecosystem.

---

## 🚀 What's New in v1.7.0

### 🖥️ Desktop Client (macOS & Windows)
- **Split-Horizon DNS**: Dynamic per-session internal DNS resolution (`*.corp.internal`, `*.dev.local`) through tunnel servers without leaking public queries.
- **Device Posture Inspection**: Real-time evaluation of endpoint health (OS version, disk encryption with FileVault/BitLocker, firewall state).
- **Universal macOS DMG & Windows ARM64**: Native `Tridorian-ZTNA.dmg` (Apple Silicon + Intel) and native Windows 11 ARM64 (Snapdragon Copilot+ PCs) & x64 installers with bundled Wintun drivers.
- **Auto-Reconnect & Dynamic Updates**: Resilient connection roaming and in-app notifications for one-click updates.

### 💻 ZTNA CLI (Linux & macOS)
- **Headless Non-Interactive Auth**: Automated login via API tokens (`--token=...`) for servers, containers, and CI/CD pipelines.
- **Multi-Architecture Static Binaries**: Pre-compiled single standalone executables for Linux `amd64`/`arm64` and macOS `amd64`/`arm64`.
- **Scriptable JSON Output**: Structured JSON formatting (`--json`) across `status`, `devices`, and `peers` commands.
- **Embedded Secure Tunnel Engine**: Ultra-low memory (<15MB RAM) with full wire-speed end-to-end encryption.

### 🛡️ ZTNA Gateway (Linux Data Plane)
- **Remote Software Update Manager**: Live update lifecycle (`idle` ➔ `downloading` ➔ `updating` ➔ `updated`) with remote update triggers from Console.
- **High-Availability (HA) Clustering**: Active/Standby multi-node clustering with sub-second health checks and failover.
- **Automated Let's Encrypt TLS**: Automated certificate issuance and ACME DNS challenge validation for Web Proxy internal domains.
- **Token-Based Zero-Touch Enrollment**: Fast node provisioning with rotating tokens and hardware fingerprint verification.

---

## 📦 Release Artifacts Matrix

All binaries and desktop installers are automatically compiled and published to [GitHub Releases](https://github.com/tridorian/tridorian-ztna-releases/releases):

| Component | Target Platform | Filename | Format | Description |
|---|---|---|---|---|
| **macOS Desktop Client** | macOS Universal (Apple Silicon & Intel) | `Tridorian-ZTNA.dmg` | Apple Disk Image (`.dmg`) | Official Wails GUI desktop client with drag-to-Applications installer layout and self-elevation. |
| **Windows Desktop Client** | Windows `amd64` (x64) | `ztna-client-windows-amd64-installer.exe` | NSIS Executable Installer | GUI client with bundled Wintun 0.14.1 TUN drivers and desktop/start menu shortcuts. |
| **Windows Desktop Client** | Windows `arm64` (Snapdragon) | `ztna-client-windows-arm64-installer.exe` | NSIS Executable Installer | Native ARM64 GUI client with ARM64 Wintun drivers for Windows on ARM devices. |
| **ZTNA CLI** | Linux `amd64` / `arm64` | `ztna-cli-linux-amd64`<br>`ztna-cli-linux-arm64` | Standalone Executable | Headless command-line client for Linux servers, containers, CI/CD pipelines, and scripts. |
| **ZTNA CLI** | macOS `amd64` / `arm64` | `ztna-cli-darwin-amd64`<br>`ztna-cli-darwin-arm64` | Standalone Executable | Lightweight CLI client for macOS terminal power-users. |
| **ZTNA Gateway Data Plane** | Linux `amd64` / `arm64` | `gateway-linux-amd64`<br>`gateway-linux-arm64` | Standalone Executable | High-performance wire-speed data plane daemon with encrypted TUN routing for on-premise/VPC gateways. |
| **ZTNA Gateway Container** | Linux (Multi-Arch) | `gateway:v1.7.0` | OCI Container Image | Containerized gateway deployment for Kubernetes, Docker, and edge appliances. |

---

## 📊 Component Version Matrix

| Component | Version | Build Status |
| :--- | :--- | :--- |
| **Management API** | `v1.7.0` | ✅ Stable |
| **Authentication API** | `v1.7.0` | ✅ Stable |
| **Gateway Control Plane** | `v1.7.0` | ✅ Stable |
| **Edge Gateway Data Plane** | `v1.7.0` | ✅ Stable |
| **Console** | `v1.7.0` | ✅ Stable |
| **Backoffice** | `v1.7.0` | ✅ Stable |
| **Web Catalog** | `v1.7.0` | ✅ Stable |
| **Landing Page** | `v1.7.0` | ✅ Stable |
| **ZTNA CLI** | `v1.7.0` | ✅ Stable |
| **ZTNA Desktop Client** | `v1.7.0` | ✅ Stable |

---

*© 2026 Tridorian. All rights reserved. Distributed and operated by [Tridorian](https://www.tridorian.com).*
