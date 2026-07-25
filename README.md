# Velion · Hybrid Remote Control Ecosystem

<p align="center">
  <img src="./assets/icon.png" width="128" height="128" alt="Velion Logo">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Architecture-Hybrid_Local_%26_Remote-E77B49?style=for-the-badge" alt="Hybrid Architecture">
  <img src="https://img.shields.io/badge/Security-Hardened-F76E5D?style=for-the-badge" alt="Security Hardened">
  <img src="https://img.shields.io/badge/Biometrics-FIDO2_/_Fingerprint-280001?style=for-the-badge" alt="Biometrics">
</p>

<p align="center">
  <b>Velion</b> is a high-performance, cross-platform ecosystem engineered to provide absolute control over PC power states. By merging <b>Local Network UDP broadcasting</b> with <b>Global MQTT signaling</b>, Velion offers a zero-compromise solution for waking computers securely from anywhere in the world.
</p>

<p align="center">
  <a href="https://velion-demo.vercel.app"><b>Live Web Demo</b></a> • 
  <a href="https://github.com/SilverCipherr/Velion/releases/download/v1.2.0/Velion-demo.v1.2.0.apk"><b>Android APK</b></a>
</p>

---

## 🛰️ The Identity

The name **Velion** is a fusion of movement, speed, and technical precision:
*   **Vel** — Derived from *velocity* (speed), *velox* (Latin for swift), and *veil* (representing the subtle, hidden background processes).
*   **Ion** — Representing science, energy, and the high-tech foundation of the ecosystem.

<p align="center">
  <img src="./assets/symbol_breakdown.png" width="900" alt="Branding & Design Specification">
</p>

---

## ⚡ Hybrid Intelligence Architecture

Velion doesn't just send a signal; it intelligently chooses the most efficient path based on your environment.

### 🏠 Local-First Dispatch (Zero Latency)
When the system detects you are on your <b>Home SSID</b>, the Android application switches to **Direct Mode**. It bypasses all cloud brokers and broadcasts a Raw UDP Magic Packet directly to the target PC's MAC address. This ensures instant wake-up even if your ESP32 controller is offline.

### 🌐 Remote MQTT Relay (Global Reach)
When outside your local network, Velion utilizes a hardened MQTT bridge. The command is routed through an encrypted topic to your **ESP32 Controller**, which then fires the physical Magic Packet within your home network.

### 📊 Capability Matrix

| Scenario | ESP32 Status | Web UI Result | Android App Result |
| :--- | :--- | :--- | :--- |
| **You are at Home** | **OFF** | ❌ Cannot Wake | ✅ **Wakes PC (Direct UDP)** |
| **You are Remote** | **OFF** | ❌ Cannot Wake | ❌ Cannot Wake |
| **Anywhere** | **ON** | ✅ Wakes PC (via ESP32) | ✅ Wakes PC (via ESP32) |

---

## ✨ Core Pillars

### 🔐 Uncompromising Security
*   **Cryptographic Hashing**: Passwords are never stored in plain text, utilizing **SHA-256** hashing via the native Web Crypto API and Kotlin standard libraries.
*   **Biometric Perimeter**: Experience zero-friction entry with **Android Biometric API** (Fingerprint/Face) and **WebAuthn (FIDO2)** for secure, password-less authentication on the web dashboard.
*   **Rate-Limited Core**: An intelligent lockout mechanism provides edge-level protection against automated brute-force attempts.

### 📡 Hybrid Connectivity
*   **SSID Awareness**: Automatic network detection ensures you are always using the fastest available path.
*   **UDP Broadcasting**: Direct hardware-level signaling for the Android native client.
*   **Resilient Fallback**: Automatic failover to MQTT Broker if local communication is restricted.

### 🎨 Elite UX Design
*   **Obsidian Heritage Theme**: A custom dark aesthetic built for high-contrast legibility and professional appeal.
*   **Signal Path Viz**: Real-time SVG animations visualize the data packet traveling from your device to the PC.
*   **PWA Core**: The web dashboard is fully installable and features comprehensive offline caching via Service Workers.

---

## 🛠️ Technical Deep-Dive

| Layer | Component | Implementation |
| :--- | :--- | :--- |
| **Android** | <img src="https://img.shields.io/badge/Kotlin-7F52FF?logo=kotlin&logoColor=white" height="20"> | Jetpack Compose, Coroutines, Material 3, HiveMQ |
| **Web** | <img src="https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black" height="20"> | ES6+, MQTT.js, WebAuthn API, Vercel Edge |
| **Hardware** | <img src="https://img.shields.io/badge/C++-00599C?logo=c%2B%2B&logoColor=white" height="20"> | ESP32, PubSubClient, UDP Multicast |
| **Logic** | <img src="https://img.shields.io/badge/Protocol-Hybrid-E77B49" height="20"> | Raw UDP Magic Packets + MQTT WebSockets |

---

## 📸 System Interface

<p align="center">
  <img src="./assets/screenshot_login.png" width="450" alt="Login Interface" style="border-radius: 12px; margin-right: 20px; vertical-align: middle;">
  <img src="./assets/screenshot_dash.png" width="380" alt="Dashboard Interface" style="border-radius: 12px; vertical-align: middle;">
</p>

---

## 🧪 Simulation & Showcase

To maintain the privacy of the production infrastructure, this public repository operates in **Showcase Mode**:
*   **Environment**: Connection, biometric flows, and dispatch sequences are high-fidelity simulations.
*   **Credentials**: Access the dashboard using the demo password: `admin`.
*   **Privacy**: All private MAC addresses, IP ranges, and private MQTT topics have been sanitized.

---

## 📄 Licensing & Rights

Copyright (c) 2026 Prottay. All rights reserved. This project is proprietary software.

---
<p align="center">
  <i>Velion — Effortless Control. Absolute Security.</i>
</p>
