---
layout: page
title: IAQ LoRaWAN Sensor Network
description: End-to-end development and deployment of a remote indoor air quality monitoring system.
importance: 1
category: "IoT & Systems"
---

Developing a robust remote sensing network requires seamlessly integrating custom physical hardware with reliable data pipelines. This project involved the complete lifecycle development of an Indoor Air Quality (IAQ) monitoring system, deploying LoRaWAN-enabled sensors to transmit environmental data to a centralized base station.

### 1. System Architecture
The network was designed for high reliability and low-power remote operation. 
* **End Devices:** Custom-designed sensor nodes deployed in the field to capture continuous environmental metrics.
* **Base Station:** A Raspberry Pi-based gateway utilizing a custom HAT for peer-to-peer LoRa and LoRaWAN network management.
* **Data Pipeline:** Telemetry data was routed via webhooks into a structured pipeline for automated cleaning, processing, and statistical analysis.

### 2. Hardware Engineering & Manufacturing
Managing the physical layer involved moving from breadboard prototypes to mass-producible units. 
* **PCB Design:** Iterative schematic design and custom PCB routing for the sensor nodes and base station HAT.
* **Production Management:** Handled component selection, rigorous BOM management, and oversaw the mass production and population of the final boards.
* **Mechanical Integration:** Designed custom enclosures using Autodesk Inventor to protect the hardware while ensuring optimal sensor exposure.

### 3. Firmware & Data Processing
To extract actionable insights from the hardware, the software stack had to be highly resilient.
* **Embedded Firmware:** Developed the C/C++ firmware to handle sensor polling, power management, and LoRaWAN transmission protocols.
* **Data Analytics:** Built the backend data collection infrastructure, executing data cleaning and processing routines to prepare the raw telemetry for research-grade analysis.
