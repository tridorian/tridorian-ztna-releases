# 🛡️ Tridorian ZTNA - Release Logs

Welcome to the official release repository for **Tridorian ZTNA (Zero Trust Network Access)**. This repository tracks all versions, updates, and major milestones of the Tridorian security ecosystem.

---

## 🚀 Recent Releases

### [v1.7.0] - 2026-08-27
This major milestone release introduces High-Availability Gateway Clusters, Advanced Dynamic Policy Engine, Granular User & Logical Groups, Comprehensive Security Hardening, Automated 100% Cloud Build Client Packaging, and Unified Billing Life Cycle Management.

#### ✨ Key Features & Enhancements

- **🛡️ Gateway & High-Availability Clusters**:
  - **High-Availability (HA) Clustering**: Active-active cluster failover, dynamic health probing, and automatic traffic re-routing across multi-node edge gateways.
  - **Token-Based Gateway Enrollment**: Secure, zero-touch provisioning for edge gateways with rotating node tokens and hardware identity verification.
  - **WireGuard & TUN Data Plane**: High-performance multi-threaded ChaCha20-Poly1305 encryption delivering wire-speed throughput on Linux `amd64` and `arm64`.
  - **Zero-Downtime Rolling Updates**: Smooth gateway control-plane reconnections without interrupting active user tunnels.

- **🚦 Policy Engine & Granular Access Control**:
  - **User Groups & Logical Resource Groups**: Dynamic assignment of users and servers into logical tiers for fine-grained Zero Trust policy enforcement.
  - **Context-Aware Rule Evaluation**: Real-time inspection of IP CIDR, domain names, protocols, and port ranges per user identity and device posture.
  - **Split-Horizon DNS (Split DNS)**: Seamless resolution of internal corporate domains (`*.corp.internal`, `*.dev.local`) through internal DNS servers across the tunnel.

- **🔒 Platform Security & Compliance Hardening**:
  - **Tamper-Resistant Device Posture**: Continuous compliance checks (disk encryption, firewall status, OS version) gating tunnel access.
  - **Instant Session Revocation**: Immediate termination of compromised user sessions and real-time JWT invalidation.
  - **Immutable Audit Trail**: Structured `audit_events` and `security_events` logging for PDPA, ISO 27001, and SOC 2 compliance.

- **🌐 Clientless Web Access Proxy**:
  - **Browser-Based Application Catalog**: Zero-install access to internal web portals, WebSSH terminals, and HTML5 WebRDP remote desktops.
  - **Automated Let's Encrypt TLS**: Automatic certificate provisioning and renewal via ACME DNS challenges.

- **💳 Billing & Subscription Lifecycle**:
  - **7-Day Grace Period Architecture**: Automated transition pipeline (`trial_active` ➔ `trial_expired` ➔ `paid`) ensuring uninterrupted service during renewals.
  - **SKU Discounts & Dispute Resolution**: Dynamic discount codes, invoice adjustments, and tenant billing state management.

- **📦 100% Unified Cloud Build Release Pipeline**:
  - **macOS Universal DMG (`Tridorian-ZTNA.dmg`)**: Native Apple UDZO disk image with custom drag-to-Applications Finder window layout, volume icons, and self-elevation permissions.
  - **Windows Installers (`.exe`)**: Executable NSIS installers with bundled signed Wintun 0.14.1 drivers for both `AMD64` and `ARM64` (Snapdragon Copilot+ PCs).
  - **Standalone Gateway & CLI Binaries**: Pre-compiled static binaries for Linux and Darwin.

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
| **ZTNA Gateway Data Plane** | Linux `amd64` / `arm64` | `gateway-linux-amd64`<br>`gateway-linux-arm64` | Standalone Executable | High-performance wire-speed data plane daemon with WireGuard & TUN routing for on-premise/VPC gateways. |
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
