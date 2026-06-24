---
layout: page
title: Siglor Radio & Chassis Architecture
description: A modular, dual-board IoT sensor device for Sigfox and LoRa(WAN).
img: assets/img/placeholder.jpg
importance: 1
category: Professional engagement
---

The **Siglor** device is a custom-architected IoT environmental sensor node, designed for high reliability and multi-sensor integration and is compatible with both Sigfox and LoRa(WAN) networks. To optimize manufacturing and testing, the system is designed with a modular, dual-board architecture: an MCU-driven Radio Board and a dedicated Chassis (Mounting) Board.

This device was designed and developed as a first iteration prototype for sensing, and therefore was designed with as many prototyping and configurable features. The Chassis (Mounting) board 

<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/placeholder.jpg" title="Assembled Siglor Device" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
<div class="caption">
  Figure 1: The fully assembled Siglor device, showcasing the Radio Board mounted onto the Chassis Board via two 15-pin headers.
</div>

### Architectural Highlights

- **Modular Dual-Board Design:** Separated the core processing logic (Radio Board) from the power regulation and sensor payload (Chassis Board). This isolation allows for flexible upgrades to the sensor suite without redesigning the RF-sensitive microcontroller layout.
- **Selectable RF Engineering:** Implemented a customizable RF matching network utilizing an RF switch. By configuring specific 0402 footprint capacitors or inductors during assembly and RF matching, the hardware routes the RF signal to either an onboard chip antenna or an external SMA connector without signal degradation.
- **Dual-Stage Power Management:** Architected a highly efficient, battery-driven power supply utilising two separate buck-boost converters.
  - **Converter U1** provides a continuous, stable 2.5V rail for the STM32WL55CC and onboard telemetry.
  - **Converter U4** is conditionally enabled via a GPIO pin to conserve power and features a manual hardware switch to toggle its output between 3V and 5V, accommodating a wide range of external, third-party sensors.
- **Integrated Telemetry & Diagnostics:** Embedded primary environmental sensors directly via I2C, including eCO2 and eVOC monitoring, and precise temperature and relative humidity data. Both sensors feature dedicated power switches to eliminate idle current draw.
- **Hardware-Level Debugging:** Incorporated dedicated $0\Omega$ resistors for isolated current measurements during the debugging phase, hardware interrupt pushbuttons for manual reset and transmitting test messages, and a bottom-layer NFC connector to prevent electromagnetic interference with the RF shield.

<div class="row">
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/placeholder.jpg" title="Radio Board" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/placeholder.jpg" title="Chassis Board" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
<div class="caption">
  Left: The Radio Board featuring the STM32WL55CC, RF switch, and antenna selection footprint. Right: The Chassis Board housing the dual TPS63900 power supplies, I2C sensor payload, and external connector headers.
</div>

---

### Project Assets

_For IP protection, full manufacturing files, BOMs, and complete schematics are not publicly distributed._

- [Download Sanitized 3D Assembly Overview (PDF)](#)
- [Download MCU Pinout & Interface Specification Extract (PDF)](#)
