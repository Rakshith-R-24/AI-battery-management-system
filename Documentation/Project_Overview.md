# Project Overview

## Introduction

<div align="justify">

Battery Management Systems (BMS) are essential for the safe, reliable, and efficient operation of lithium-ion battery packs used in electric vehicles. Battery performance directly influences vehicle range, charging efficiency, thermal stability, operational safety, and battery lifespan. Conventional BMS architectures primarily use threshold-based protection mechanisms such as overvoltage, undervoltage, overcurrent, and overtemperature protection. Although these mechanisms are necessary for safe operation, they are mainly reactive and have limited capability to identify gradual changes in battery behaviour.

During practical operation, factors such as cell imbalance, temperature variation, charging and discharging stress, ageing, and changing load conditions can affect the performance of individual cells. Continuous monitoring of these parameters is therefore important for maintaining safe and reliable battery operation.

The proposed project focuses on developing a low-power per-cell Battery Management System capable of continuously monitoring important electrical and thermal parameters of a lithium-ion battery pack while providing embedded protection against abnormal operating conditions.

</div>

## About the Project

<div align="justify">

The project develops a per-cell Battery Management System for electric two-wheeler battery applications, with emphasis on continuous monitoring, embedded protection, and low-power operation. The system is implemented as a 4S lithium-ion battery prototype for experimental development and validation.

The prototype consists of four lithium-ion cells connected in series, with a nominal pack voltage of 14.8 V and a maximum voltage of 16.8 V. Individual cell voltages are monitored using voltage-divider sensing circuits, while pack current is measured using a current-sensing interface. Temperature monitoring is performed using NTC thermistors to observe thermal conditions during battery operation.

The embedded controller acquires and processes the measured electrical and thermal parameters and provides monitoring and protection functions. The system is designed to observe cell voltage variation, pack current, temperature variation, and cell-level imbalance during charging and discharging operation.

Protection functions are incorporated to respond to abnormal operating conditions such as overvoltage, undervoltage, overcurrent, short-circuit conditions, and overtemperature. The prototype also provides a foundation for further development of advanced battery monitoring and diagnostic functions.

Although the present implementation is based on a 4S prototype, the overall architecture is intended to provide a scalable foundation for higher-series battery systems used in electric-vehicle applications.

</div>

## Problem Statement

<div align="justify">

Lithium-ion battery packs consist of multiple cells whose electrical and thermal characteristics can vary during operation. Differences between cells, temperature variation, ageing, charging and discharging conditions, and changes in load can result in cell imbalance and abnormal battery behaviour.

Conventional Battery Management Systems primarily depend on predefined voltage, current, and temperature thresholds to protect the battery. These protection mechanisms are essential for preventing unsafe operating conditions, but they are mainly reactive and provide limited information about gradual changes in cell behaviour.

Cell voltage imbalance, abnormal temperature rise, weak-cell behaviour, and other electro-thermal variations may develop over time before reaching a predefined protection threshold. Continuous monitoring of individual cells is therefore important for identifying such variations and maintaining reliable battery operation.

Another important requirement is reducing the power consumed by the monitoring system itself. Since a BMS operates continuously with the battery pack, unnecessary processing and monitoring power consumption can reduce overall system efficiency.

Therefore, there is a need for a low-power per-cell Battery Management System that can continuously monitor individual cell voltage, battery current, and temperature, provide reliable protection against abnormal operating conditions, and support detailed analysis of battery behaviour for electric two-wheeler applications.

</div>

## Objectives

<div align="justify">

The major objectives of the proposed system are:

</div>

- To develop a low-power Battery Management System for lithium-ion battery packs.
- To implement continuous per-cell voltage monitoring for identifying cell-level voltage variation and imbalance.
- To monitor battery current and temperature during charging and discharging operation.
- To implement embedded protection against overvoltage, undervoltage, overcurrent, short-circuit, and overtemperature conditions.
- To develop an STM32-based embedded monitoring and protection architecture.
- To analyse electrical and thermal battery parameters for identifying abnormal operating conditions.
- To validate the proposed monitoring and protection functions using a 4S lithium-ion battery prototype.
- To develop a scalable architecture suitable for future higher-series electric-vehicle battery systems.
