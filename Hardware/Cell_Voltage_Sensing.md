## Voltage Sensing Circuit

<div align="justify">

Voltage sensing is a fundamental measurement function of a Battery Management System because the voltage of individual cells in a series-connected lithium-ion battery pack can differ during charging and discharging. A battery pack consists of multiple electrochemical cells, and differences in cell operating conditions can result in variations in individual cell voltage. Therefore, monitoring the voltage of each cell provides cell-level information that cannot be obtained from the total pack voltage alone.

The proposed prototype uses four lithium-ion cells connected in series to form a 4S1P configuration. In a series connection, the cell voltages add to produce the total pack voltage, while the nominal capacity of the series-connected pack remains equal to the capacity of one cell. The total pack voltage represents the combined voltage of all four cells and does not directly indicate the voltage of each individual cell. Consequently, individual voltage taps are required to monitor the electrical condition of each cell within the series-connected pack.

The voltage sensing circuit provides the electrical interface between the battery pack and the embedded controller. The voltage at each cell junction is measured with respect to the battery negative terminal and scaled using a resistive voltage-divider network before being applied to the controller's analog-to-digital converter (ADC). The sensing stage therefore provides the controller with the voltage information required for individual cell-voltage monitoring, cell-voltage comparison, and voltage-based protection functions.

</div>

<p align="center">
  <img src="4cells.png" width="950">
</p>

<p align="center">
  <b>Figure:<img width="1911" height="1116" alt="4cells1_circuit" src="https://github.com/user-attachments/assets/81490f92-f3f4-4f9d-9948-99f9b1bd33d3" />
 </b>
</p>

## KiCAD Simulation

<div align="justify">

The designed voltage-sensing circuit was verified using SPICE simulation. The simulation shows the cumulative voltages of the four series-connected cells and the corresponding scaled divider outputs. For the nominal 3.7 V cell condition, the cumulative tap voltages are approximately 3.7 V, 7.4 V, 11.1 V, and 14.8 V, while the divider outputs are approximately 0.336 V, 0.673 V, 1.01 V, and 1.35 V, respectively.

</div>

<p align="center">
  <img src="4cells1.png" width="950">
</p>

<p align="center">
  <b>Figure:<img width="1917" height="1135" alt="4cells_waveform" src="https://github.com/user-attachments/assets/50217f60-4fb2-4b8a-a80a-924e2e683bb7" />
</b>
</p>
