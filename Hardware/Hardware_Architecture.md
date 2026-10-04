## Architecture

<div align="justify">

The hardware architecture begins with the 4S lithium-ion battery pack, from which the required electrical and thermal parameters are measured. Individual cell voltages are acquired through voltage-divider sensing circuits, while the pack current is measured using the INA226 current-sensing interface. NTC thermistors are used for temperature monitoring of the battery cells.

The measured parameters are acquired by the embedded controller for real-time monitoring and analysis. The controller evaluates the battery operating conditions and provides control signals to the protection stage when abnormal conditions are detected. The protection stage provides response to conditions such as overvoltage, undervoltage, overcurrent, short circuit, and overtemperature.

The prototype hardware is validated using an ESP32-based embedded platform, while the proposed architecture is designed around an STM32L476RG-based embedded controller. The architecture provides a scalable foundation for future higher-series electric-vehicle battery systems.

</div>
