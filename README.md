# Low Power AI-Optimised Per-Cell Battery Management System for Electric Two-Wheelers

An embedded Battery Management System for per-cell monitoring of lithium-ion battery packs, combining low-power embedded processing, electro-thermal sensing, protection, and AI-assisted battery analysis.

## Project Overview

This project focuses on the development of a low-power, per-cell Battery Management System (BMS) for lithium-ion battery packs used in electric two-wheelers. The system is designed to provide real-time monitoring of individual cell voltages, pack current, battery temperature, and cell-level electrical conditions, with an emphasis on efficient embedded implementation and reliable battery protection.

The target BMS architecture is based on the STM32L476RG microcontroller, which is used for real-time data acquisition, monitoring, protection control, and electro-thermal feature extraction. A 4S lithium-ion battery prototype, rated at 14.8 V nominal and 16.8 V maximum, is used for hardware development and experimental validation. The prototype incorporates per-cell voltage sensing through voltage-divider circuits, INA226-based pack current and power measurement, and NTC-based temperature monitoring.

The embedded system includes real-time data monitoring through UART along with protection functions for battery operating conditions. Prototype-stage testing also uses an ESP32 for selected sensing, data-acquisition, and load-testing activities, while the STM32-based architecture remains the target controller for the BMS implementation.

The project further investigates AI-assisted battery analysis for resource-constrained embedded systems. Linear Regression-based State of Charge (SoC) estimation has been developed using battery-data analysis, while multiple machine-learning and deep-learning architectures have been comparatively evaluated for their suitability to battery-management applications. The overall development combines battery-system engineering, embedded firmware, sensor interfacing, data acquisition, and AI-assisted analysis within a single BMS development workflow.
