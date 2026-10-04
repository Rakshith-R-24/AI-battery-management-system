## Voltage Sensing Circuit

<div align="justify">

Voltage sensing is a fundamental measurement function of a Battery Management System because the voltage of individual cells in a series-connected lithium-ion battery pack can differ during charging and discharging. A battery pack consists of multiple electrochemical cells, and differences in cell operating conditions can result in variations in individual cell voltage. Therefore, monitoring the voltage of each cell provides cell-level information that cannot be obtained from the total pack voltage alone.

The proposed prototype uses four lithium-ion cells connected in series to form a 4S1P configuration. In a series connection, the cell voltages add to produce the total pack voltage, while the nominal capacity of the series-connected pack remains equal to the capacity of one cell. The total pack voltage represents the combined voltage of all four cells and does not directly indicate the voltage of each individual cell. Consequently, individual voltage taps are required to monitor the electrical condition of each cell within the series-connected pack.

The voltage sensing circuit provides the electrical interface between the battery pack and the embedded controller. The voltage at each cell junction is measured with respect to the battery negative terminal and scaled using a resistive voltage-divider network before being applied to the controller's analog-to-digital converter (ADC). The sensing stage therefore provides the controller with the voltage information required for individual cell-voltage monitoring, cell-voltage comparison, and voltage-based protection functions.

The implemented sensing circuit uses four identical voltage-divider networks, one for each cell-voltage measurement point. Each network consists of a 100 kΩ upper resistor and a 10 kΩ lower resistor. The resistor-divider arrangement provides an attenuation ratio of 11:1, allowing the cumulative battery-tap voltages to be reduced before analog measurement.

For the implemented resistor values, the divider output is given by:

V<sub>ADC</sub> = V<sub>tap</sub> × R<sub>bottom</sub> / (R<sub>top</sub> + R<sub>bottom</sub>)

With R<sub>top</sub> = 100 kΩ and R<sub>bottom</sub> = 10 kΩ:

V<sub>ADC</sub> = V<sub>tap</sub> / 11

The voltage taps are cumulative measurements referenced to the battery negative terminal. Under the nominal 3.7 V per-cell condition, the four cumulative tap voltages are approximately 3.7 V, 7.4 V, 11.1 V, and 14.8 V. After voltage division, the corresponding sensing outputs are approximately 0.336 V, 0.673 V, 1.01 V, and 1.35 V.

The individual cell voltages are obtained from the cumulative measurements. The first cell voltage corresponds to V1, while the subsequent cell voltages are determined from the difference between adjacent tap voltages. This allows the voltage of each cell to be evaluated independently from the series-connected pack.

The total resistance of each divider network is 110 kΩ. At the nominal cumulative tap voltages, the corresponding divider currents are approximately 33.6 µA, 67.3 µA, 101 µA, and 135 µA for the four sensing branches. The relatively high resistance values limit the continuous current drawn by the voltage-sensing networks.

The voltage sensing circuit was designed and simulated using KiCad. The simulation verifies the expected cumulative tap voltages, divider outputs, and sensing-branch currents for the 4S configuration.

</div>

### KiCad Circuit Design

<p align="center">
  <img src="4cells1_circuit.png" width="950">
</p>

<p align="center">
  <b>Figure: KiCad schematic of the 4S cell-voltage sensing circuit
 <img width="1911" height="1116" alt="4cells1_circuit" src="https://github.com/user-attachments/assets/9783bd8b-3dd4-486f-9b17-2e3bce32cd62" />
 </b>
</p>

<div align="justify">

The KiCad schematic shows the four series-connected cell representations and the corresponding 100 kΩ / 10 kΩ voltage-divider networks. The voltage and current markers in the schematic provide the simulated operating values at each sensing branch.

</div>

### KiCad Simulation Result

<div align="justify">

The KiCad simulation produces approximately 0.336 V, 0.673 V, 1.01 V, and 1.35 V at the four divider outputs for the nominal 3.7 V per-cell condition. The outputs remain at constant levels over the simulated interval because the cell sources used in the simulation are constant-voltage sources.

</div>

<p align="center">
  <img src="4cells_waveform.png" width="950">
</p>

<p align="center">
  <b>Figure: KiCad simulation waveforms of the 4S cell-voltage sensing circuit
 <img width="1917" height="1135" alt="4cells_waveform" src="https://github.com/user-attachments/assets/360048b9-2f11-42d7-ae66-8e6a6dd20f2d" />
 </b>
</p>
