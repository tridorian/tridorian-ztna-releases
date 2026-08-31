# 🛡️ Tridorian ZTNA - Release Logs

Welcome to the official release repository for **Tridorian ZTNA (Zero Trust Network Access)**. This repository tracks all versions, updates, and major milestones of the Tridorian security ecosystem.

---

## 🚀 What's New in v1.7.3

### 🔒 Security Hardening & Platform Remediations
- **Gateway Enrollment Token & Takeover Protection**: New gateways now require a cryptographically random `enrollment_token` upon initial registration, preventing unauthorized edge node registrations.
- **Split DNS Security Hardening**: Strict RFC domain syntax validation and path traversal defenses across macOS, Linux (`/etc/resolver/`), and Windows PowerShell NRPT rules.
- **Client Privilege Hardening**: Eliminated SUID root privileges on GUI binaries on macOS in favor of least-privilege scoped helper execution.
- **Web Proxy & Clientless ZTNA Isolation**: Injected `Referrer-Policy: same-origin`, `X-Content-Type-Options: nosniff`, and `X-Frame-Options: SAMEORIGIN` headers alongside session cookie isolation.
- **Web SSH & RDP Stored XSS Mitigation**: Fully HTML-escaped dynamic application names and destination hostnames across browser-based terminal and remote desktop sessions.
- **IP Spoofing Protection**: Enforced trusted reverse proxy subnet validation before accepting `X-Forwarded-For` and `X-Real-IP` headers.
- **OAuth CSRF State Verification**: Enforced strict cross-site request forgery cookie checks across Single Sign-On and IdP callback endpoints.
- **Redis Session Indexing**: Upgraded Web Access session management to indexed user sets for $O(1)$ lookup performance and DoS protection.
- **Dynamic Version Synchronizer**: Real-time multi-path `versions.json` dynamic reloading across management APIs and control planes.

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
| **ZTNA Gateway Container** | Linux (Multi-Arch) | `gateway:v1.7.3` | OCI Container Image | Containerized gateway deployment for Kubernetes, Docker, and edge appliances. |

---

## 📊 Component Version Matrix

| Component | Version | Build Status |
| :--- | :--- | :--- |
| **Management API** | `v1.7.3` | ✅ Stable |
| **Authentication API** | `v1.7.3` | ✅ Stable |
| **Gateway Control Plane** | `v1.7.3` | ✅ Stable |
| **Edge Gateway Data Plane** | `v1.7.3` | ✅ Stable |
| **Console** | `v1.7.3` | ✅ Stable |
| **Backoffice** | `v1.7.3` | ✅ Stable |
| **Web Catalog** | `v1.7.3` | ✅ Stable |
| **Landing Page** | `v1.7.3` | ✅ Stable |
| **ZTNA CLI** | `v1.7.3` | ✅ Stable |
| **ZTNA Desktop Client** | `v1.7.3` | ✅ Stable |

---

*© 2026 Tridorian. All rights reserved. Distributed and operated by [Tridorian](https://www.tridorian.com).*
