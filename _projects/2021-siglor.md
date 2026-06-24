---
layout: page
title: Siglor Radio & Chassis Architecture
description: A modular, dual-board IoT sensor device for Sigfox and LoRaWAN networks, developed during a hardware engineering internship.
img: assets/img/projects/2021-siglor/siglor-assembled.png
importance: 1
category: "Professional engagement"
---

The **Siglor** device is a custom-architected IoT environmental sensor node designed for high reliability, multi-sensor integration, and compatibility with both Sigfox and LoRaWAN networks.

Developed entirely over a three-month engineering internship within a cross-functional agile team, I owned the end-to-end hardware development of this first-iteration prototype - from initial component conceptualisation to final hardware manufacturing. The successful delivery of this functional prototype, alongside comprehensive internal and client-facing documentation, directly resulted in the award of a full final-year undergraduate academic bursary.

To optimise prototyping flexibility, testing, and future iterations, the system utilises a modular, dual-board architecture: an MCU-driven Radio Board and a dedicated Chassis (Mounting) Board.

<div class="row justify-content-center text-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/2021-siglor/siglor-assembled.png" title="Assembled Siglor Device" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">The fully assembled Siglor prototype, showcasing the Radio Board mounted onto the Chassis Board.</div>

---

### 1. Role & Project Ownership

Operating as the sole hardware intern embedded within a multidisciplinary hardware and firmware team, I was responsible for the full PCB design lifecycle:

- **Lifecycle management:** Managed component selection, schematic capture, and custom footprint generation from scratch in Altium Designer.
- **Cross-Functional agile workflow:** Participated in weekly sprints, design reviews, and monthly performance evaluations, utilising enterprise Git version control and secure YubiKey authentication.
- **Manufacturing & procurement:** Prepared final fabrication files (Gerbers, NC Drill, ODB++) and managed physical PCB procurement through Würth Elektronik.
- **Technical documentation:** Authored comprehensive handover documentation for the internal engineering team to ensure project continuity, as well as an operational manual defining hardware states (e.g., test vs. run modes) for the end client.

---

### 2. Architectural & Technical Highlights

**Modular Dual-Board Design**
Separated the core sub-GHz processing logic (Radio Board) from the power regulation and sensor payload (Chassis Board). This isolation allows for flexible upgrades to the sensor suite without requiring a redesign of the highly sensitive, impedance-controlled RF layout.

<div class="row justify-content-center text-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/2021-siglor/siglor-radio-3d.png" title="Radio Board" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/2021-siglor/siglor-chassis-3d.png" title="Chassis Board" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">Left: The MCU-driven Radio Board. Right: The dedicated Chassis Board housing power regulation and sensor payloads.</div>

**Configurable RF Engineering**
The primary technical challenge involved designing a generic, high-efficiency RF front-end capable of interchanging antenna types without signal degradation.

- Implemented a customisable RF matching network utilising an RF switch.
- Incorporated specific 0402 Do-Not-Install (DNI) footprints along the transmission line, allowing for precise post-manufacturing impedance matching.
- Calculated and routed precise trace widths, thicknesses, and RF clearances with strategic via stitching to route the signal to either an onboard chip antenna or an external SMA connector.

<div class="row justify-content-center text-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/2021-siglor/siglor-rf-topview.png" title="RF Circuitry Close-Up" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">Impedance-controlled RF layout featuring DNI footprints for post-fabrication antenna matching and via stitching for signal integrity.</div>

**Dual-Stage Power Management**
Architected a highly efficient, battery-driven power supply utilising ultra-low quiescent current buck-boost converters.

- **Primary Converter:** Provides a continuous, stable 2.5V rail for the dual-core wireless microcontroller and onboard telemetry.
- **Secondary Converter:** Conditionally enabled via a GPIO pin to conserve power, featuring a manual hardware switch to toggle its output between 3V and 5V to accommodate a wide range of external, third-party sensors.

**Integrated Telemetry & Diagnostics**

- Embedded specialised environmental gas and air quality monitoring sensors directly via I2C, alongside precise temperature and relative humidity monitoring. Both sensors feature dedicated power switches to eliminate idle current draw.
- Incorporated dedicated 0-ohm resistors for isolated current measurements during the debugging phase, hardware interrupt pushbuttons for manual reset and transmission testing, and a bottom-layer NFC connector positioned to prevent electromagnetic interference with the RF shield.
