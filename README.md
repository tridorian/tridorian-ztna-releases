# 🛡️ Tridorian ZTNA - Release Logs


Welcome to the official release repository for **Tridorian ZTNA (Zero Trust Network Access)**. This repository tracks all versions, updates, and major milestones of the Tridorian security ecosystem.

---

## 🚀 Recent Releases

### [v1.6.0] - 2026-08-24
This milestone release introduces Split-Horizon DNS resolution, Clientless Web Access (Web Proxy) with automatic TLS, enhanced Double Layer Encryption, and zero-downtime Gateway routing.

#### ✨ Key Features
- **Internal Split DNS (Split-Horizon Resolution)**:
  - Seamlessly resolve internal corporate domains (e.g. `*.corp.internal`, `*.dev.local`) through internal DNS servers across the ZTNA tunnel.
  - Zero-latency local resolution for public internet traffic.
  - Native OS integration: macOS `/etc/resolver/`, Windows NRPT rules, and Linux `systemd-resolved` routing domains.
  - Version-guarded configuration (v1.6.0+) with interactive Console management.
- **Clientless Web Access Catalog (Web Proxy)**:
  - Direct browser access to internal web applications, WebSSH terminals, and HTML5 WebRDP remote desktops without installing any software.
  - Automatic Let's Encrypt TLS certificate provisioning with automated ACME DNS verification.
- **Double Layer Encryption & Direct Routing**:
  - High-performance ChaCha20-Poly1305 inner payload encryption with multi-threaded packet processing.
  - Direct edge gateway routing eliminating central hub bottlenecks.
- **Enterprise Governance & Compliance (PDPA / SOC 2)**:
  - Immutable audit trail (`audit_events` and `security_events`) with real-time active session revocation.
  - Multi-tenant data isolation with tenant-scoped cryptographic keys and cascade erasure.
- **Cross-Platform Client & Gateway Binaries**:
  - Universal macOS Desktop Client (Apple Silicon & Intel).
  - Windows x64 & ARM64 Installers (`.exe`).
  - Standalone Linux AMD64 / ARM64 Gateway and CLI binaries.

### [v1.5.0] - 2026-02-03
This version marks a significant architectural shift to an enhanced UI/UX experience, enhancing scalability and management capabilities.

#### ✨ Key Features
- **Features**:
    - **Session kick**: You can now kick a session from the console.
    - **Settings**: You can set the default session timeout and max concurrent sessions per user.
    - **Billing**: You can now view your billing information and manage your subscriptions.
- **Gateway**:
    - Several bug fixes. 
- **Enhanced UI/UX**: 
    - **Console**: Enhanced UI/UX experience and several bug fixes.
    - **Cross-Platform Support**:
        - **ZTNA Client**: Several bug fixes and improvements.


### [v1.4.0] - 2026-01-22
This version marks a significant architectural shift to an enhanced UI/UX experience, enhancing scalability and management capabilities.

#### ✨ Key Features
- **Enhanced UI/UX**: 
    - **Console**: New Material-UI based interface for tenant-level management.
- **Improved Security**: 
    - Integrated JWT-based authentication throughout the stack.
    - Role-Based Access Control (RBAC) refinements.
- **Cross-Platform Support**:
    - **ZTNA Client**: Universal installers for Windows (.exe) and macOS (.dmg/.pkg).
    - **ZTNA CLI**: Multi-platform binary support for Linux (amd64/arm64) and Darwin.


---

## 📊 Component Version Matrix

| Component | Version | Build Status |
| :--- | :--- | :--- |
| **Management API** | `v1.6.0` | ✅ Stable |
| **Gateway Control Plane** | `v1.6.0` | ✅ Stable |
| **Edge Gateway** | `v1.6.0` | ✅ Stable |
| **Console** | `v1.6.0` | ✅ Stable |
| **Web Catalog** | `v1.6.0` | ✅ Stable |
| **ZTNA CLI** | `v1.6.0` | ✅ Stable |
| **ZTNA Client** | `v1.6.0` | ✅ Stable |


---
*© 2026 Tridorian. All rights reserved. Distributed and operated by [Tridorian](https://www.tridorian.com).*
