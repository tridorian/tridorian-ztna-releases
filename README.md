# 🛡️ Tridorian ZTNA - Release Logs

Welcome to the official release repository for **Tridorian ZTNA (Zero Trust Network Access)**. This repository tracks all versions, updates, and major milestones of the Tridorian security ecosystem.

---

## 🚀 What's New in v1.7.5

### 🌟 Release Overview
- **Enhanced Desktop Client Experience**: Seamless startup and connection across macOS and Windows, with native authorization and full support for standard (non-admin) user accounts.
- **Smart Connection & Posture Policies**: Improved reconnection intelligence and flexible, policy-driven device posture checks.
- **Web Access & Automated TLS**: Streamlined browser-based clientless access with automated Let's Encrypt certificate management across all gateway tiers.
- **Performance & Reliability**: Core routing optimizations, faster session handshakes, and enhanced multi-platform stability.

---

## 📦 Release Artifacts Matrix

All binaries, container images, and desktop installers are automatically compiled and published to [GitHub Releases](https://github.com/tridorian/tridorian-ztna-releases/releases):

| Component | Target Platform | Filename | Format | Description |
|---|---|---|---|---|
| **macOS Desktop Client** | macOS Universal (Apple Silicon & Intel) | `Tridorian-ZTNA.dmg` | Apple Disk Image (`.dmg`) | Official Wails GUI desktop client with drag-and-drop `/Applications` installer. |
| **macOS Desktop Client** | macOS Universal (Enterprise / MDM) | `Tridorian-ZTNA.pkg` | Installer Package (`.pkg`) | Enterprise installer package with automated postinstall routing setup for MDM fleets. |
| **Windows Desktop Client** | Windows `amd64` (x64) | `ztna-client-windows-amd64-installer.exe` | NSIS Executable Installer | GUI client with bundled Wintun TUN drivers and automatic UAC elevation. |
| **Windows Desktop Client** | Windows `arm64` (Snapdragon) | `ztna-client-windows-arm64-installer.exe` | NSIS Executable Installer | Native ARM64 GUI client with ARM64 Wintun drivers for Windows on ARM. |
| **Linux Desktop Client** | Linux `amd64` (Debian/Ubuntu) | `ztna-client_1.7.5_amd64.deb` | Debian Package (`.deb`) | GUI and system daemon desktop client package for Linux distributions. |
| **ZTNA CLI** | Linux `amd64` / `arm64` | `ztna-cli-linux-amd64`<br>`ztna-cli-linux-arm64` | Standalone Executable | Headless command-line client for Linux servers, containers, CI/CD pipelines, and scripts. |
| **ZTNA CLI** | macOS `amd64` / `arm64` | `ztna-cli-darwin-amd64`<br>`ztna-cli-darwin-arm64` | Standalone Executable | Lightweight CLI client for macOS terminal power-users. |
| **ZTNA Gateway Data Plane** | Linux `amd64` / `arm64` | `gateway-linux-amd64`<br>`gateway-linux-arm64` | Standalone Executable | Wire-speed data plane daemon with encrypted TUN routing for VPC / on-premise edge nodes. |
| **ZTNA Gateway Container** | Linux Multi-Arch | `tridorian/gateway:v1.7.5` | OCI Container Image | Containerized edge gateway for Kubernetes, Docker, and edge appliances. |

---

## 🚀 Quick Start Guide

### 1. Workstation Desktop Client
* **macOS**: Download `Tridorian-ZTNA.dmg`, drag to `/Applications`, launch the app, enter your organization domain (e.g. `company.triztna.com`), and authenticate via Corporate SSO.
* **Windows**: Download and launch `ztna-client-windows-amd64-installer.exe` with administrator confirmation, enter your domain, and connect.

### 2. Command-Line Interface (`ztna-cli`)
```bash
# Interactive Single Sign-On and connection
sudo ztna-cli connect --domain company.triztna.com

# Direct Gateway connection
sudo ztna-cli connect --domain company.triztna.com --gateway <GATEWAY_UUID>

# Run in background as persistent daemon
sudo ztna-cli connect --domain company.triztna.com --daemon

# Headless server / CI/CD pipeline using pre-issued JWT token
sudo ztna-cli connect --domain company.triztna.com --token <JWT_TOKEN>

# Disconnect
sudo ztna-cli stop
```

### 3. Edge Gateway Node Deployment
```bash
# Run binary directly
sudo ./ztna-gateway --node-id <NODE_ID> --control-plane gateway.triztna.com:5443 --enrollment-token <ENROLLMENT_TOKEN>

# Install as persistent Linux systemd service (Auto-start on boot)
sudo ./ztna-gateway --install-service --node-id <NODE_ID> --control-plane gateway.triztna.com:5443 --enrollment-token <ENROLLMENT_TOKEN>

# Deploy via Docker container
docker run -d --name tridorian-gateway --restart=always --privileged --net=host \
  -e NODE_ID=<NODE_ID> \
  -e CONTROL_PLANE=gateway.triztna.com:5443 \
  -e ENROLLMENT_TOKEN=<ENROLLMENT_TOKEN> \
  tridorian/gateway:latest
```

#### Docker Compose Example (`docker-compose.yml`)
```yaml
version: '3.8'
services:
  ztna-gateway:
    image: tridorian/gateway:v1.7.5
    container_name: tridorian-gateway
    restart: always
    network_mode: host
    privileged: true
    environment:
      - NODE_ID=your-gateway-node-uuid
      - CONTROL_PLANE=gateway.triztna.com:5443
      - ENROLLMENT_TOKEN=your-gateway-enrollment-token
```

---

## 💻 System Requirements

| Platform | Minimum Supported Version | Hardware Architectures | Privileges |
|---|---|---|---|
| **macOS** | macOS Monterey (12.0+) or newer | Apple Silicon (M1/M2/M3/M4) & Intel (x86_64) | Standard User (One-time Touch ID / Admin approval for routing) |
| **Windows** | Windows 10 (19041+) / Windows 11 | x64 (AMD64) & ARM64 (Snapdragon X Elite/Plus) | Administrator (Automatic UAC Prompt on launch) |
| **Linux Client** | Kernel 5.4+ (systemd) | x86_64, ARM64 (glibc 2.31+ / musl) | `sudo` for virtual `utun` / TUN creation & routing |
| **Edge Gateway** | Linux Kernel 5.4+ | x86_64, ARM64 | Root / `CAP_NET_ADMIN` in container |

---

## 🔒 Security & Verification

All official release artifacts are signed and published with cryptographic SHA-256 checksums in `checksums.txt`:

```bash
# Verify checksum on Linux / macOS
sha256sum -c checksums.txt

# Verify checksum on Windows PowerShell
Get-FileHash .\ztna-client-windows-amd64-installer.exe -Algorithm SHA256
```

---

## 📊 Component Version Matrix

| Component | Version | Build Status |
| :--- | :--- | :--- |
| **Management API** | `v1.7.5` | ✅ Stable |
| **Authentication API** | `v1.7.5` | ✅ Stable |
| **Gateway Control Plane** | `v1.7.5` | ✅ Stable |
| **Edge Gateway Data Plane** | `v1.7.5` | ✅ Stable |
| **Console** | `v1.7.5` | ✅ Stable |
| **Backoffice** | `v1.7.5` | ✅ Stable |
| **Web Catalog** | `v1.7.5` | ✅ Stable |
| **Landing Page** | `v1.7.5` | ✅ Stable |
| **ZTNA CLI** | `v1.7.5` | ✅ Stable |
| **ZTNA Desktop Client** | `v1.7.5` | ✅ Stable |

---

*© 2026 Tridorian. All rights reserved. Distributed and operated by [Tridorian](https://www.tridorian.com).*
