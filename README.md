# Low Power AI-Optimised Per-Cell Battery Management System for Electric Two-Wheelers

An embedded Battery Management System (BMS) developed for real-time per-cell voltage, pack current, and temperature monitoring of lithium-ion battery packs, with a focus on low-power operation and AI-assisted battery analysis.

## Overview

This project focuses on the development of an AI-Optimised Ultra-Low-Power Per-Cell Battery Management System for lithium-ion battery packs used in electric two-wheelers.

The system is designed to monitor individual cell voltage, pack current, temperature variation, and cell-level imbalance during battery operation. The target embedded architecture uses an STM32-based controller for real-time data acquisition, monitoring, protection control, and electro-thermal feature extraction.

A 4S lithium-ion battery prototype is used for hardware development and experimental validation. The prototype incorporates per-cell voltage sensing using voltage-divider circuits, pack-current measurement using an INA226 current sensor, and temperature monitoring using NTC thermistors.

During prototype development and validation, an ESP32-based platform is used for selected sensing, data-acquisition, and load-testing activities. The STM32-based architecture remains the target BMS implementation.

The project also investigates AI-assisted battery analysis using measured and publicly available battery data. The current work includes Linear Regression-based State of Charge (SoC) estimation and comparative evaluation of multiple AI architectures for battery-management applications.

The present implementation represents a prototype-level research and development platform. Further development includes complete protection validation, advanced battery-state estimation, intelligent fault prediction, long-duration testing, cell-balancing studies, low-power optimisation, and higher-series battery-system integration.

---

## Problem Statement

Lithium-ion batteries used in electric vehicles require continuous monitoring to ensure safe, reliable, and efficient operation.

Conventional Battery Management Systems primarily depend on fixed-threshold protection mechanisms such as overvoltage, undervoltage, overcurrent, and overtemperature protection. While these mechanisms are essential for battery safety, they are mainly reactive and provide limited capability for identifying gradual electro-thermal abnormalities, cell imbalance, and weak-cell behaviour.

Battery operating conditions are also affected by temperature variation, charging and discharging stress, aging, and changing load conditions. These factors can influence battery performance, efficiency, reliability, and lifespan.

The project therefore focuses on developing a low-power per-cell BMS architecture capable of real-time battery monitoring, electro-thermal analysis, embedded protection, and AI-assisted battery condition analysis.

---

## Objectives

- Develop a low-power Battery Management System for lithium-ion battery monitoring and protection.
- Implement real-time per-cell voltage monitoring.
- Measure battery pack current and electrical power.
- Monitor cell and battery temperature using NTC thermistors.
- Observe cell-level voltage imbalance and battery operating behaviour.
- Implement embedded monitoring and protection functions.
- Develop an STM32-based target architecture for real-time battery data acquisition and processing.
- Use an ESP32-based prototype platform for selected sensing, data-acquisition, and experimental validation activities.
- Develop electro-thermal features from battery operating data.
- Implement lightweight State of Charge (SoC) estimation.
- Investigate AI/ML approaches suitable for battery-management applications.
- Develop a scalable architecture for future higher-series EV battery systems and dedicated BMS IC integration.

---

## System Architecture

The proposed system follows the following general architecture:

```text
                 4S Li-ion Battery Pack
                          |
             +------------+------------+
             |            |            |
             v            v            v
       Cell Voltage     Pack Current   Temperature
         Sensing          Sensing       Sensing
             |              |              |
             +--------------+--------------+
                            |
                            v
                   Embedded Controller
                    STM32 Target System
                            |
             +--------------+--------------+
             |              |              |
             v              v              v
        Data Processing   Protection    Communication
             |              |              |
             v              v              v
       Battery Analysis  Cut-off       UART / Display
             |
             v
        AI-assisted Analysis
             |
             v
       Battery Condition
          Assessment
