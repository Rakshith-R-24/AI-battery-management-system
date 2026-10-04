# Project Overview

## Project Introduction

Battery Management Systems (BMS) are essential for the safe, reliable, and efficient operation of lithium-ion battery packs used in electric two-wheelers. A BMS monitors important battery parameters such as cell voltage, current, and temperature and provides protection against unsafe operating conditions.

This project focuses on developing a **low-power per-cell Battery Management System for electric two-wheelers**. A 4S lithium-ion battery prototype is used to implement and validate individual cell-voltage monitoring, pack-current measurement, temperature monitoring, and battery protection.

## About the Project

The proposed system continuously monitors the **voltage of individual cells, battery-pack current, and cell temperature** during charging and discharging. The monitored parameters are processed by an embedded controller to identify abnormal operating conditions and control the protection circuitry.

The prototype incorporates voltage-divider-based per-cell sensing, INA226-based current measurement, NTC thermistors for temperature monitoring, and protection mechanisms for overvoltage, undervoltage, overcurrent, short-circuit, and overtemperature conditions.

The prototype uses **four 18650 lithium-ion cells connected in series (4S)**, with a nominal pack voltage of 14.8 V and maximum voltage of 16.8 V.

## Problem Statement

Lithium-ion battery packs used in electric two-wheelers require continuous monitoring to maintain safe and reliable operation. In a series-connected battery pack, individual cells can exhibit differences in voltage and temperature due to variations in cell characteristics, operating conditions, and aging.

Conventional protection systems mainly depend on fixed voltage, current, and temperature limits. Such protection is necessary for battery safety, but it provides limited information about gradual cell imbalance, abnormal temperature rise, and weak-cell behaviour before a critical condition occurs.

Therefore, there is a need for a **low-power per-cell BMS that provides continuous monitoring of individual cell voltage, current, and temperature while providing reliable protection against abnormal battery conditions**.
