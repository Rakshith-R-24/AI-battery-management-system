## Architecture

<div align="justify">

The hardware architecture begins with the 4S lithium-ion battery pack, from which the required electrical and thermal parameters are measured. Individual cell voltages are acquired through voltage-divider sensing circuits, while the pack current is measured using the INA226 current-sensing interface. NTC thermistors are used for temperature monitoring of the battery cells.

The measured signals are provided to the embedded controller for parameter acquisition and monitoring. The controller evaluates the battery operating conditions and provides control signals to the protection stage when abnormal conditions are detected. The protection stage is intended to respond to overvoltage, undervoltage, overcurrent, short-circuit, and overtemperature conditions.

For the present academic prototype, hardware testing and measured outputs are obtained using an ESP32 DevKit V1. The STM32L476RG was part of the planned embedded architecture, but the NUCLEO-L476RG board was damaged during earlier development and is not used for the present hardware validation.

</div>
