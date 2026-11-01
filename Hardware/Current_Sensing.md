## Current Sensing Circuit

Current sensing is an important measurement function of a Battery Management System because the charging and discharging current of the battery changes according to the operating condition and connected load. Monitoring the battery current provides information required for load monitoring, power calculation, State-of-Charge (SOC) estimation, and overcurrent protection.

The proposed prototype uses an **INA226 current and power monitor** for measuring the current flowing through the battery path. The INA226 measures the voltage developed across an external shunt resistor connected in series with the load. The module used in the prototype contains a **0.1 Ω shunt resistor**, marked as R100. The measured shunt voltage is used to determine the current flowing through the circuit.

The current through the shunt resistor is calculated using:

```text
I_LOAD = V_SHUNT / R_SHUNT
```

where `I_LOAD` is the load current, `V_SHUNT` is the voltage developed across the shunt resistor, and `R_SHUNT` is the shunt resistance.

For the implemented INA226 module:

```text
R_SHUNT = 0.1 Ω
```

Therefore, the current can be calculated as:

```text
I_LOAD = V_SHUNT / 0.1
```

The INA226 also measures the bus voltage. The electrical power consumed by the connected load is calculated using:

```text
P_LOAD = V_BUS × I_LOAD
```

where `P_LOAD` is the load power and `V_BUS` is the measured bus voltage.

The power dissipated by the shunt resistor is given by:

```text
P_SHUNT = I_LOAD² × R_SHUNT
```

For the implemented shunt resistor:

```text
P_SHUNT = I_LOAD² × 0.1
```

The INA226 communicates with the embedded controller through the I²C interface. The controller can therefore obtain the measured bus voltage, shunt voltage, current, and power values from the device. The measured current can also be used to identify the battery operating condition. Current flowing from the battery towards the load represents discharging, while current flowing towards the battery represents charging.

### INA226 Module

**Figure: INA226 current and power monitoring module used for current measurement**

The INA226 module contains the current-sensing shunt resistor and the INA226 monitoring IC. The module provides the `IN+` and `IN−` terminals for connection in the current path, along with the I²C communication pins `SDA` and `SCL`. The measured electrical parameters are transferred digitally to the embedded controller through the I²C interface.

### KiCad Circuit Design

**Figure: KiCad schematic of the INA226-based current-sensing circuit [current_sensing_circuit]**

The KiCad schematic shows the INA226 connected in the battery current path through the external shunt resistor. The load current passes through the shunt resistor, producing a small voltage drop that is measured by the INA226. The device communicates the measured parameters to the embedded controller through the I²C interface.

### Practical Working

A **5 V DC motor** was used as the load to verify the practical operation of the INA226-based current-sensing circuit. The motor was connected to the supply through the current-sensing path containing the INA226 module and its shunt resistor.

When the motor is switched ON, current flows through the shunt resistor and produces a voltage drop across it. The INA226 measures this shunt voltage and determines the corresponding load current. The bus voltage, current, and power values are then read by the embedded controller through the I²C interface.

The practical test demonstrates the operation of the current-sensing circuit under a real DC motor load. The motor load also allows changes in current and power to be observed during operation.

**Figure: Practical current-sensing setup using a 5 V DC motor as the load [current_sensing_setup]**

### Current Measurement Calculation

The load current is calculated from the measured shunt voltage and the shunt resistance:

```text
I_LOAD = V_SHUNT / R_SHUNT
```

For the implemented module:

```text
R_SHUNT = 0.1 Ω
```

Therefore:

```text
I_LOAD = V_SHUNT / 0.1
```

For example, if the measured shunt voltage is 20 mV:

```text
V_SHUNT = 20 mV
        = 0.020 V
```

Then:

```text
I_LOAD = 0.020 / 0.1
       = 0.20 A
```

The actual current value obtained during the practical test is recorded in the experimental results.

### Load Power Calculation

The power consumed by the motor is calculated from the measured bus voltage and load current:

```text
P_LOAD = V_BUS × I_LOAD
```

For example, for a bus voltage of 5 V and a current of 0.20 A:

```text
P_LOAD = 5 × 0.20
       = 1.0 W
```

The actual power value is determined using the measured voltage and current obtained during the practical test.

### Shunt Power Dissipation

The power dissipated by the shunt resistor is calculated as:

```text
P_SHUNT = I_LOAD² × R_SHUNT
```

For a current of 0.20 A and a 0.1 Ω shunt resistor:

```text
P_SHUNT = (0.20)² × 0.1
        = 0.004 W
        = 4 mW
```

The low shunt power dissipation keeps the additional power loss in the current-sensing path small during normal operation.

### Experimental Results

The INA226 measurements obtained during the practical test with the 5 V DC motor load are recorded below.

| Parameter | Measured Value |
|---|---:|
| Bus Voltage | ___ V |
| Shunt Voltage | ___ mV |
| Load Current | ___ A |
| Load Power | ___ W |
| Shunt Power Dissipation | ___ W |

The load current is calculated from the measured shunt voltage using the 0.1 Ω shunt resistance, while the load power is calculated from the measured bus voltage and current.

**Figure: INA226 measurements obtained during the practical test [current_sensing_results]**

### Conclusion

The INA226-based current-sensing circuit was implemented and tested using a 5 V DC motor as the load. The circuit provides measurement of the shunt voltage, bus voltage, load current, and power through the I²C interface. The practical test verifies the operation of the current-sensing stage and provides the current and power information required for battery monitoring and protection functions.
