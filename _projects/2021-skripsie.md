---
layout: page
title: Remote LoRa Water Monitoring System
description: An end-to-end, full-stack IoT telemetry solution designed, engineered, and deployed as a solo systems architect. <br> <span class="badge badge-pill badge-primary">Full-Stack IoT</span> <span class="badge badge-pill badge-info">Altium / RF Design</span> <span class="badge badge-pill badge-success">Embedded C</span> <span class="badge badge-pill badge-warning">Python / Web UI</span>
img: assets/img/projects/2021-skripsie/3dview_altium_3d.jpg
importance: 1
category: "Academic research"
---

South African livestock farmers frequently drive hundreds of kilometers a week solely to verify water levels in remote grazing camps. To eliminate this operational inefficiency, I engineered a complete, automated remote water monitoring system.

Operating as the **sole systems architect and developer** for my final-year engineering project, I executed the entire product lifecycle - from conceptualizing the RF hardware and writing the bare-metal firmware, to designing a locally hosted, front-end dashboard for the end-user.

The resulting system was successfully deployed and tested in harsh, real-world conditions on a farm in the Western Cape, proving its viability as a scalable agricultural IoT product.

---

### 1. Hardware & RF engineering (Field Device)

Rather than relying on pre-built development boards, I engineered a highly customized, solar-powered field device from the MCU level up to optimize power consumption and physical footprint.

- **MCU & Power architecture:** Built around the STM32WL55CC (a sub-GHz wireless MCU). I designed a dual-stage voltage regulation system (1.5V and 2.5V rails) driven by a 3.7V Li-Ion battery, complete with a custom solar charge controller circuit.
- **Custom RF impedance matching:** Calculated and routed a custom 50-ohm RF transmission line on a 4-layer FR-4 substrate. I designed a highly specific LC matching network and integrated an RF switch to optimize the 868MHz signal for maximum range.
- **Design for environment:** Engineered and 3D-printed a UV-resistant, weather-proof, and animal-proof enclosure, alongside a custom mechanical sensor mount for the water troughs.

<div class="row justify-content-center text-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/2021-skripsie/pcb_layout_segmented.png" title="Segmented PCB Layout" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">Segmented PCB layout demonstrating strict impedance-controlled routing and isolated RF shielding.</div>

---

### 2. Embedded firmware (C/C++)

To achieve sustainable, long-term deployment without battery replacement, the field device firmware was written in C using STM32CubeIDE and programmed via JTAG/SWD.

- **LoRa PHY optimisation:** Configured the Sub-GHz PHY layer parameters (Spreading Factor, Bandwidth, explicit header modes) to prioritize maximum transmission range (tested successfully up to 2.9km) over high data rates, perfectly tailoring the protocol to the agricultural application.
- **Power efficiency:** Implemented software-controlled power switching. The firmware actively shuts down power to the sensors, the 1.5V regulator, and the radio modules during the 6-hour intervals between transmissions, drastically extending battery life.

---

### 3. Base station & Full-stack dashboard

I architected a central Base Station to receive, process, and visually present the telemetry data to the farmer without requiring external internet connectivity.

- **Custom Raspberry Pi HAT:** Designed and manufactured a custom PCB HAT for a Raspberry Pi 3, integrating an SPI-driven RFM95W LoRa transceiver to act as the central receiver.
- **Python backend & Data pipeline:** Authored a Python-based backend to validate incoming LoRa packets (performing CRC checks, payload length validation, and encryption byte verification) before logging the telemetry to a local CSV database.
- **Front-end user interface:** Developed a locally hosted, graphical dashboard using HTML, CSS, and JavaScript. The UI automatically updates, mapping trough levels over a 48-hour period and triggering bright red visual alarms if a trough runs dry.
- **Automated alerting:** Integrated a bash-scripted alert protocol to send automated email warnings to the farmer when critical water levels or hardware fault states are detected.

<div class="row justify-content-center text-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/2021-skripsie/bs_dashboard_annotate.png" title="Base Station Dashboard" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">The custom-built, locally hosted HTML/JS dashboard providing real-time telemetry and fault alerting.</div>

---

### 4. Real-world deployment & Project management

A significant aspect of this project was managing the end-to-end delivery pipeline. Over a highly constrained timeline, I managed procurement (navigating global component shortages), negotiated alternative parts, conducted system-level validation, and executed the physical installation in Swellendam.

<div class="row justify-content-center text-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/2021-skripsie/experiment_device_box.jpg" title="Field Deployment" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">The fully assembled field device successfully deployed and transmitting from a remote grazing camp.</div>

---

### Project assets & Video presentation

To see the hardware and full-stack software operating in real-time, please view the project presentation video below.

<div class="row justify-content-center mt-4">
    <div class="col-sm-10 text-center">
        <div class="embed-responsive embed-responsive-16by9 z-depth-1 rounded">
            <iframe class="embed-responsive-item" src="https://www.youtube.com/embed/https://youtu.be/GgWdfaKdZJU?si=ZR5kBK4GVauKUhch" allowfullscreen></iframe>
        </div>
    </div>
</div>

<br>

**Downloadable documentation:**

- [Download Full Engineering Thesis & Report (PDF)](/assets/pdf/projects/2021-skripsie/RitavdWalt-SkripsieReport-2021.pdf)
- [Download Field Device Schematics (PDF)](/assets/pdf/projects/2021-skripsie/Field-device-schematic-and-assembly.pdf)
- [Download Field Device 3D (PDF)](/assets/pdf/projects/2021-skripsie/Field-device-3D.pdf)
