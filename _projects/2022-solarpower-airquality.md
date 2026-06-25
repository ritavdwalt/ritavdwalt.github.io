---
layout: page
title: Solar-Powered LoRa Air Quality Monitor
description: An end-to-end, low-power IoT environmental sensor node featuring custom mixed-signal hardware, I2C sensor integration, and LoRa telemetry. <br> <span class="badge badge-pill badge-primary">Full-Stack IoT</span> <span class="badge badge-pill badge-info">Mixed-Signal PCB</span> <span class="badge badge-pill badge-success">Low-Power Firmware</span> <span class="badge badge-pill badge-warning">Enclosure Design</span>
img: assets/img/projects/2022-solarpower-airquality/pcb_3d.png
importance: 3
category: "Professional engagement"
---

Continuous environmental monitoring requires hardware that can operate autonomously for extended periods without maintenance. To address this, I engineered a solar-powered, low-power air quality sensor node capable of aggregating diverse atmospheric data and transmitting it over a point-to-point (P2P) LoRa network.

I managed the complete lifecycle of this device, including the mixed-signal schematic design, PCB layout, C/C++ firmware development, and custom mechanical enclosure design.

---

### 1. Hardware architecture & Sensor payload

The hardware was architected around a central STM32 microcontroller to balance processing capability with extreme power efficiency.

- **Environmental Sensor Suite:** Integrated a comprehensive I2C sensor payload, including an Ambient Light Sensor (ALS), a high-precision Temperature & Relative Humidity sensor, and a dedicated VOC/CO2 sensor for robust air quality analysis.
- **LoRa Telemetry:** Implemented a sub-GHz LoRa transceiver for P2P communications, ensuring reliable, long-range data transmission from remote monitoring sites.
- **Low-Power Clocking:** Integrated an external Low-Speed Oscillator (LSE) to maintain accurate timekeeping while the primary MCU cores enter deep-sleep states between measurement intervals.
- **Hardware Debugging:** Incorporated a physical hardware reset (RST) button and dedicated JTAG/SWD headers for seamless firmware flashing and in-circuit debugging via an ST-Link.

<div class="row justify-content-center text-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/2022-solarpower-airquality/pcb_3d.png" title="Assembled PCB" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">The fully assembled air quality monitor PCB, highlighting the STM32 MCU, LoRa transceiver, and modular I2C sensor payload.</div>

---

### 2. Power management & Analogue signal conditioning

For a solar-powered IoT device, maximizing battery life and telemetry accuracy is critical. The system is powered by a rechargeable 18650 Li-Ion battery, maintained by a custom solar charge controller circuit and isolated by a physical DIP switch.

Dual voltage regulators (3.0V and 3.3V) were implemented to isolate the sensitive analogue/RF domains from the digital sensor rails. Furthermore, I designed a custom **analogue signal conditioning circuit** to maximize the resolution of the battery health telemetry.

- **The ADC Resolution Challenge:** The system's voltage regulators shut down at **2.0V**, while the battery peaks at **3.7V**. If a simple voltage divider stepped the 3.7V down to the microcontroller's 3.3V ADC limit, the "empty" 2.0V state would read as roughly 1.78V, wasting more than half of the ADC's dynamic range.
- **Analogue Level-Shifting:** I designed a differential amplifier circuit (verified in LTspice) that mathematically applies a DC offset and gain. This maps the critical **2.0V – 3.7V** battery discharge curve perfectly onto the **0V – 3.3V** ADC input, allowing the firmware to track the state-of-charge with absolute maximum digital resolution.

<div class="row justify-content-center text-center mt-4">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/2022-solarpower-airquality/aq_battery_level_manager.png" title="Analogue Battery Level Manager" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">LTspice schematic of the analogue level-shifter, demonstrating the specific resistor networks used to scale and offset the battery discharge curve for the ADC.</div>

---

### 3. Mechanical enclosure design

To protect the hardware in deployed environments while ensuring adequate airflow for the VOC/CO2 and temperature sensors, I designed a custom mechanical enclosure.

Utilising **Autodesk Inventor**, I modeled a two-part assembly consisting of a mounting base and a fitted lid. The design accounted for PCB standoffs, solar panel cable routing, and external antenna mounting, ensuring the final product was both structurally robust and highly functional for atmospheric sampling.

<div class="row justify-content-center text-center mt-4">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/2022-solarpower-airquality/enclosure.png" title="3D Enclosure Design" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">Autodesk Inventor render of the two-part mechanical enclosure, optimized for internal airflow and environmental protection.</div>

<br>

**Downloadable documentation:**

- [Download Selected Schematics (PDF)](/assets/pdf/projects/2022-solarpower-airquality/2022-SolarPower-AirQuality.PDF)
