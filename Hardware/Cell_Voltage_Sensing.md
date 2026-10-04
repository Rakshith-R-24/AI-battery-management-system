## Voltage Sensing Circuit

<div align="justify">

The 4S cell-voltage sensing circuit consists of four series-connected 3.7 V cell representations. Each cumulative cell tap is connected to a 100 kΩ / 10 kΩ resistive voltage-divider network. The divider outputs provide scaled voltages V1, V2, V3, and V4 for measurement by the controller's ADC.

</div>

<p align="center">
  <img src="4cells.png" width="950">
</p>

<p align="center">
  <b>Figure:<img width="1911" height="1116" alt="4cells1_circuit" src="https://github.com/user-attachments/assets/81490f92-f3f4-4f9d-9948-99f9b1bd33d3" />
 </b>
</p>

## SPICE Simulation

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
