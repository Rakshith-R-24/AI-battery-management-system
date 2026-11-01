## Current Sensing Circuit

Current sensing is used to measure the current flowing through the battery and load. The measured current is used for monitoring the battery operating condition, calculating power, and implementing current-based protection functions.

The prototype uses an **INA226 current and power monitor** with an external shunt resistor. The INA226 measures the voltage developed across the shunt resistor and uses this measurement to determine the current flowing through the circuit. The module also measures the bus voltage and provides power measurement through the I²C interface.

### INA226 Module

<img width="447" height="447" alt="image" src="https://github.com/user-attachments/assets/aff2aee2-3ffe-4608-b4db-95962a0f2096" />


The INA226 module contains the current-sensing shunt resistor and the INA226 monitoring IC. The module has `IN+` and `IN−` terminals for connection in the current path and `SDA` and `SCL` pins for I²C communication with the controller. The shunt resistor on the module is marked `R100`, corresponding to a resistance of 0.1 Ω.

### Current Measurement Principle

The current flowing through the shunt resistor is determined from the voltage developed across the resistor:

```text
I_LOAD = V_SHUNT / R_SHUNT
```

For the INA226 module used in the prototype:

```text
R_SHUNT = 0.1 Ω
```

Therefore:

```text
I_LOAD = V_SHUNT / 0.1
```

where `I_LOAD` is the load current and `V_SHUNT` is the voltage measured across the shunt resistor.

### Power Measurement

The load power is calculated from the measured bus voltage and load current:

```text
P_LOAD = V_BUS × I_LOAD
```

where `P_LOAD` is the load power and `V_BUS` is the measured bus voltage.

The power dissipated by the shunt resistor is:

```text
P_SHUNT = I_LOAD² × R_SHUNT
```

For the 0.1 Ω shunt resistor:

```text
P_SHUNT = I_LOAD² × 0.1
```

### KiCad Circuit Design

**Figure: KiCad schematic of the INA226-based current-sensing circuit [current_sensing_circuit]**

The KiCad schematic shows the INA226 connected in the current path through the shunt resistor. The current flowing through the load also flows through the shunt resistor, producing a voltage drop that is measured by the INA226. The measured parameters are transferred to the controller through the I²C interface.

### Practical Working

A **5 V DC motor** was used as the load for testing the current-sensing circuit. The motor was connected through the INA226 current-sensing path.

When the motor is switched ON, current flows through the shunt resistor. The voltage developed across the shunt is measured by the INA226, and the corresponding load current is obtained from the measurement.

The INA226 also provides the bus-voltage and power measurements. These values are read by the controller through the I²C interface.

<p align="center">
  <b>Figure: Practical current-sensing setup using a 5 V DC motor</b>
</p>

### Current Calculation

The load current is calculated using:

```text
I_LOAD = V_SHUNT / R_SHUNT
```

With:

```text
R_SHUNT = 0.1 Ω
```

the calculation becomes:

```text
I_LOAD = V_SHUNT / 0.1
```

For example, if the measured shunt voltage is 20 mV:

```text
V_SHUNT = 20 mV
        = 0.020 V

I_LOAD = 0.020 / 0.1
       = 0.20 A
```

The actual measured value obtained during the practical test is recorded in the results section.

### Power Calculation

The load power is calculated using:

```text
P_LOAD = V_BUS × I_LOAD
```

For example, for a measured bus voltage of 5 V and a current of 0.20 A:

```text
P_LOAD = 5 × 0.20
       = 1.0 W
```

The actual power is calculated using the measured bus voltage and current from the practical test.

### Experimental Results

The INA226 readings obtained with the 5 V DC motor are recorded below.

| Parameter | Measured Value |
|---|---:|
| Bus Voltage | ___ V |
| Shunt Voltage | ___ mV |
| Load Current | ___ A |
| Load Power | ___ W |
| Shunt Power | ___ W |

**Figure: INA226 measurements obtained during the practical test [current_sensing_results]**

The measured shunt voltage is used to determine the load current, while the measured bus voltage and current are used to determine the load power.
