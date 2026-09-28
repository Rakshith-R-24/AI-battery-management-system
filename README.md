# Low Power AI-Optimised Per-Cell Battery Management System for Electric Two-Wheelers

An embedded Battery Management System for per-cell monitoring of lithium-ion battery packs, combining low-power embedded processing, electro-thermal sensing, protection, and AI-assisted battery analysis.

## Project Overview

Battery Management Systems (BMS) are critical components in electric vehicles and energy storage systems,
ensuring the safe, reliable, and efficient operation of lithium-ion battery packs. Battery performance directly
influences driving range, charging efficiency, thermal stability, operational safety, and battery lifespan.
Conventional BMS architectures primarily rely on threshold-based protection mechanisms such as
overvoltage, undervoltage, overcurrent, and overtemperature protection. Although these methods are
essential for safe battery operation, they are largely reactive and offer limited capability for identifying
gradual electro-thermal abnormalities before critical operating conditions occur.
In practical battery operation, factors such as cell imbalance, temperature rise, charging-discharging stress,
aging, and varying load conditions continuously affect battery performance and degradation characteristics.
Weak-cell behaviour and progressive electro-thermal variations can reduce battery efficiency, reliability, and
lifespan, while traditional monitoring systems often struggle to detect these conditions during their early
stages due to dependence on fixed-threshold protection logic. Therefore, there is a growing need for
intelligent battery monitoring systems capable of providing enhanced abnormality awareness and future
predictive analysis.
Recent advancements in embedded systems and Artificial Intelligence (AI) have enabled the development of
intelligent monitoring frameworks that analyse real-time battery data and electro-thermal features. Unlike
conventional approaches, AI-assisted monitoring techniques can observe parameter variations and operating
trends under dynamic conditions, enabling improved battery behaviour analysis and supporting future
predictive battery management applications.
This project presents an AI-Optimized Ultra-Low-Power Per-Cell Battery Management System using an
STM32-based embedded platform for real-time electro-thermal monitoring and protection of lithium-ion
battery packs. The developed 4S lithium-ion battery prototype incorporates per-cell voltage sensing, current
sensing, NTC-based temperature monitoring, and relay-based protection circuitry. The implemented
protection mechanisms include overvoltage, undervoltage, overcurrent, short-circuit, and overtemperature
protection to ensure safe battery operation during testing and validation.
AI-Optimized Ultra-Low-Power Battery Management System
2
The STM32 microcontroller performs real-time data acquisition, parameter monitoring, protection control,
and electro-thermal feature extraction while maintaining ultra-low-power operation suitable for embedded
battery applications. In addition to conventional protection functions, the proposed architecture supports AIassisted battery analysis and future implementation of State of Charge (SoC) estimation, State of Health
(SoH) prediction, Remaining Useful Life (RUL) analysis, and intelligent fault prediction. Although the
current work focuses on a 4S prototype for development and experimental validation, the overall architecture
is scalable to higher-series EV battery systems and future industrial BMS platforms.
In summary, the proposed system combines low-power embedded operation, real-time electro-thermal
monitoring, intelligent protection, and AI-assisted analysis to enhance battery safety, operational reliability,
and future predictive battery management capabilities.
