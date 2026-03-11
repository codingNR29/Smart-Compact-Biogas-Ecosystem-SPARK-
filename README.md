# 🌿 Smart Compact Biogas Ecosystem

> An AI-Powered Decentralized Energy Solution developed by Team Kyros for the SPARK Challenge 2025/26. 

![Status](https://img.shields.io/badge/Status-Ongoing-blue)
![Hardware](https://img.shields.io/badge/Hardware-Raspberry%20Pi%20%7C%20ESP32-success)
![AI](https://img.shields.io/badge/AI-LSTM%20Machine%20Learning-orange)
![IoT](https://img.shields.io/badge/IoT-MQTT%20%7C%20Firebase-yellow)

## 📌 Project Overview
Sri Lanka faces a dual crisis of unmanaged urban organic waste and escalating fossil fuel costs. While traditional biogas digesters offer a solution, they frequently fail due to user error, lack of visibility, and acidification. 

To solve this, we engineered the **Smart Compact Biogas Kit**—a modular system integrated with a hybrid Edge-Cloud IoT architecture. It actively monitors the health of the digester and utilizes machine learning to predict daily gas generation, transforming a passive tank into a reliable, smart appliance.

---

## 🏗️ System Architecture 

### 1. The Hardware Layer (ARTI Digester)
We modified a commercial-grade ARTI telescopic digester (1m³ capacity) to eliminate common failure modes:
* **Thermal Insulation Jacket:** Maintains mesophilic temperatures (30°C–37°C) to prevent cold shocks.
* **Inline Grease Trap:** Prevents scum formation from oily commercial food waste.
* **Modular Scalability:** Allows multiple units to be daisy-chained in parallel for higher capacity.

### 2. The Edge Layer (Critical Safety)
A hard-coded, low-latency safety loop runs locally to protect the system even without internet access.
* **Sensors:** Continuously polls an MQ-4 (Methane) sensor for leaks, a BMP180 for pressure buildup, a DS18B20 for temperature, and an MD0415 pH Probe for acidification risks.
* **Alerts:** Triggers an immediate local buzzer alarm and emergency alerts if critical thresholds are breached.

### 3. The Cloud & AI Layer
* **Data Pipeline:** Sensor data is securely transmitted via MQTT to a serverless cloud backend (Firebase/AWS).
* **LSTM Prediction Engine:** A custom Machine Learning model analyzes historical digestion trends to forecast the "Cooking Minutes Remaining" for the user.

---

## 📱 The User Experience (UX)
We abstracted the complex physics of methanogenesis into a highly intuitive mobile dashboard.
* **The "Gas Battery":** Eliminates "Energy Anxiety" by displaying available gas as a simple battery percentage.
* **Active Guidance:** Provides clear "Feed Now" or "Wait" indicators based on real-time pH health, preventing users from over-feeding and crashing the system.

---

## 🚀 Current Status & Roadmap (MVP)
This project is currently **Ongoing**. 

For our High-Fidelity MVP, we are utilizing a **Raspberry Pi 4** as an edge gateway to process real-time sensor data and locally train our LSTM models. Our commercial roadmap involves migrating this finalized logic to a highly cost-effective **ESP32** microcontroller, ensuring the system can be mass-produced and scaled affordably.
