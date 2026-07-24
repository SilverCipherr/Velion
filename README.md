# Velion · Secure Wake-on-LAN Ecosystem

<p align="center">
  <img src="./assets/icon.png" width="128" height="128" alt="Velion Logo">
</p>

**Velion** is a modern, cross-platform remote control system designed to wake up computers via **Wake-on-LAN (WoL)** using an ESP32 microcontroller and MQTT. It features a sleek, security-hardened Web dashboard and a native Android application.

[**Live Demo (Web)**](https://velion-demo.vercel.app) • [**Download Android APK**](https://github.com/SilverCipherr/Velion/releases/download/1.0.1/Velion-demo.apk)
---

## 🚀 The Architecture

The system is designed for low latency and high reliability, following a "Signal Path" architecture:

1.  **Client (Web/Android)**: User authenticates via password or Biometrics.
2.  **Broker (MQTT)**: A secure message is published to a unique, private topic.
3.  **Controller (ESP32)**: The microcontroller, subscribed to the topic, receives the command.
4.  **Target (PC)**: The ESP32 broadcasts a UDP Magic Packet within the local network to wake the PC.

## ✨ Key Features

### 🔐 Security First
*   **SHA-256 Hashing**: Passwords are never stored or transmitted in plain text.
*   **Biometric Authentication**: Seamless login using **Fingerprint/FaceID** via the WebAuthn API (Web) and Android Biometric API.
*   **Hardened Headers**: The Web dashboard is protected by a strict **Content Security Policy (CSP)** and security headers (HSTS, No-Sniff, XSS-Protection).
*   **Lockout Mechanism**: Intelligent rate-limiting and temporary lockout after multiple failed attempts.

### 🎨 Premium UI/UX
*   **Responsive Design**: Built with modern CSS design tokens and a custom "Obsidian Heritage" dark theme.
*   **Visual Feedback**: A real-time "Signal Path" visualization shows the packet traveling from your device, through the broker, to the PC.
*   **PWA Ready**: Installable on iOS and Android with offline caching via Service Workers.
*   **Native Experience**: The Android app is built with **Jetpack Compose** and **Material 3**, featuring smooth transitions and native biometric integration.

### 🛠️ Technical Stack
| Platform | Technologies |
| :--- | :--- |
| **Web Dashboard** | JavaScript (ES6+), MQTT.js, Web Crypto API, WebAuthn, Service Workers, Vercel |
| **Android App** | Kotlin, Jetpack Compose, Material 3, Coroutines, HiveMQ Client |
| **Microcontroller** | C++ (Arduino/PlatformIO), ESP32, PubSubClient, WakeOnLan Library |

---

## 📸 Screenshots

| Login Screen | Dashboard |
| :---: | :---: |
| <img src="./assets/screenshot_login.png" width="400"> | <img src="./assets/screenshot_dash.png" width="400"> |

---

## 🧪 Showcase Mode (Simulation)

This repository serves as a public showcase. To protect private infrastructure, the **Live Demo** and **Demo APK** operate in a simulated environment:
*   **Authentication**: Use the password `admin` to log in.
*   **MQTT Logic**: The connection and "Wake" commands are visually simulated with high-fidelity animations.
*   **Privacy**: All unique identifiers, MAC addresses, and private MQTT topics have been removed.

---

## 📄 License

This project is proprietary. All rights reserved. See the [LICENSE](LICENSE) file for more details.

---

## 👨‍💻 Author

**SilverCipher**

---
<p align="center">
  <i>Velion - Effortless Control, Absolute Security.</i>
</p>
