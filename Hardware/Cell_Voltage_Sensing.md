## Voltage Sensing Circuit

<div align="justify">

Voltage sensing is a fundamental measurement function of the Battery Management System because the electrical condition of a lithium-ion battery cannot be determined reliably from the total pack voltage alone. A battery pack consists of multiple electrochemical cells, and the voltage of individual cells can vary due to differences in state of charge, internal characteristics, temperature, ageing, charging history, and load conditions. Therefore, monitoring the voltage of each cell provides more detailed information about the condition of the battery pack.

In the proposed system, the prototype battery consists of four lithium-ion cells connected in series to form a 4S1P configuration. When cells are connected in series, their voltages add together while the available capacity remains that of a single cell. Although the total pack voltage provides information about the overall electrical condition of the battery, it does not indicate how the voltage is distributed among the individual cells. One cell may reach a high voltage or a low voltage before the remaining cells, even though the total pack voltage appears to be within the expected range. Per-cell voltage measurement is therefore necessary for detecting such cell-level variations.

The voltage sensing circuit provides an electrical interface between the battery pack and the embedded controller. The voltage present at each cell junction is sensed and converted into a lower voltage suitable for acquisition through an analog-to-digital converter. The sensing stage therefore performs two important functions: obtaining information about the individual cell voltages and scaling the relatively higher battery voltage to a level that can be safely processed by the controller.

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
