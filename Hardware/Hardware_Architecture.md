# Hardware Architecture

<div align="justify">

The hardware architecture of the proposed Battery Management System is designed for continuous monitoring and protection of a 4S lithium-ion battery pack. The system consists of the battery pack, per-cell voltage sensing, pack current sensing, temperature sensing, an embedded controller, protection circuitry, and monitoring interfaces.

The 4S battery pack consists of four lithium-ion cells connected in series, providing a nominal voltage of 14.8 V and a maximum voltage of 16.8 V. Individual cell voltages are measured using voltage-divider sensing circuits, while the battery current is measured using an INA226 current-sensing interface. NTC thermistors are used to monitor the temperature of the battery cells.

The sensed electrical and thermal parameters are acquired by the embedded controller and used for real-time battery monitoring. The controller processes the measured parameters to identify abnormal operating conditions and controls the protection stage when required.

The protection section provides response to abnormal conditions including overvoltage, undervoltage, overcurrent, short circuit, and overtemperature. Local indication and monitoring interfaces are used to provide information about the battery operating condition and protection status.

The hardware architecture is implemented as a 4S prototype for experimental validation. The current hardware testing uses an ESP32-based platform, while the intended embedded architecture is based on the STM32L476RG. The architecture provides a foundation for future expansion to higher-series electric-vehicle battery systems.

</div>
