# Low Power AI-Optimised Per-Cell Battery Management System for Electric Two-Wheelers

An embedded Battery Management System for per-cell monitoring of lithium-ion battery packs, combining low-power embedded processing, electro-thermal sensing, protection, and AI-assisted battery analysis.

## Project Overview

The Low Power AI-Optimised Per-Cell Battery Management System (BMS) is an embedded system developed for lithium-ion battery packs used in electric two-wheelers. The system combines per-cell voltage monitoring, current and temperature sensing, battery protection, low-power embedded processing, and AI-assisted battery analysis.

The project uses ESP32 for prototype-level sensor interfacing, data acquisition, and initial testing, while the STM32L476RG is the intended primary MCU for the low-power BMS architecture. A dedicated battery-monitoring AFE is used for individual cell voltage monitoring and passive balancing.

The acquired voltage, current, and temperature data is processed to support State of Charge (SOC), State of Health (SOH), and State of Energy (SOE) estimation, along with abnormal-condition and battery-fault analysis. Lightweight machine-learning techniques are investigated for embedded deployment to provide an additional layer of predictive battery diagnostics alongside conventional hardware protection.
