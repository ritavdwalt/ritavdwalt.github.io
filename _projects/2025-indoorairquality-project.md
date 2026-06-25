---
layout: page
title: Scalable LoRaWAN Environmental Network
description: An end-to-end industrial IoT telemetry network—from custom hardware manufacturing to data pipelines—driving municipal infrastructure policy. <br> <span class="badge badge-pill badge-primary">Full-Stack IoT</span> <span class="badge badge-pill badge-info">LoRaWAN (RFM95)</span> <span class="badge badge-pill badge-success">Data Engineering</span> <span class="badge badge-pill badge-warning">Policy Impact</span>
img: assets/img/projects/2025-indoorairquality-project/sensor_3dview_4_3.jpg
importance: 1
category: "Academic research"
---

Infrastructure dictates the indoor air environment, which in turn acts as a critical driver of educational equity. To quantify health, comfort, and cognitive risks in low-income educational infrastructure, a highly resilient, long-term environmental monitoring system was required.

Operating as the sole systems architect, I executed the entire "sensor-to-policy" pipeline. I designed and mass-produced the generic IoT hardware, deployed and managed the multi-site LoRaWAN network, and architected the data pipelines to ingest over 3 million data points over a 24-month period.

The resulting observational analysis was presented to the City of Cape Town's Environmental Health specialists, directly influencing capital infrastructure upgrades (roof retrofitting) for container classrooms.

---

### 1. Hardware architecture & Mass production

The hardware required a delicate balance between low-power longevity and highly reliable RF transmission.

- **Generic Hardware Platform:** I architected the core node around an Atmel microcontroller and an RFM95 LoRa transceiver. Crucially, the board was designed to be highly generic and modular. This exact architecture was subsequently adapted and repurposed for multiple other remote sensing deployments, including outdoor forestry anemometers and the Saldanha Bay industrial dust loggers.
- **Design for Manufacturing (DFM):** I managed the transition from early-stage in-house prototyping (PCB milling and manual SMD soldering) to outsourced volume manufacturing. This involved strict BOM management, component sourcing, and yield validation for a mass-produced fleet of 100 end devices.
- **Mechanical Integration:** I modelled and 3D-printed custom enclosures designed for tamper-resistance and optimal airflow, ensuring the I2C environmental sensors could sample accurately without external interference.

<div class="row justify-content-center text-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/2025-indoorairquality-project/sensies.jpg" title="Mass Produced PCBS" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">A subset of the mass-produced, Atmel-based LoRaWAN sensor nodes prior to final enclosure assembly and deployment.</div>

---

### 2. Network operations & Fleet management

Deploying hardware is only the first step; maintaining an operational fleet across diverse, remote locations requires rigorous network management.

- **Infrastructure Deployment:** I directed the physical deployment of the sensor fleet across multiple schools, configuring and installing the gateway infrastructure to ensure overlapping coverage and high signal resilience.
- **Uptime & Maintenance:** Over the 24-month longitudinal data collection period, I monitored gateway uptimes, managed node power consumption profiles, and conducted on-site debugging and hardware maintenance to ensure the continuity of the dataset.

<div class="row justify-content-center text-center mt-4">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/2025-indoorairquality-project/sensors_with_powerbank_4_3.jpg" title="Deployed Device in Classroom" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">Two of the 100 custom sensor nodes successfully deployed within a school classroom, actively transmitting indoor air quality telemetry.</div>

---

### 3. Data engineering & Pipeline architecture

With a fleet of 100 devices transmitting high-frequency data, I engineered a robust, automated backend to capture and structure the telemetry without data loss.

- **Ingestion Pipelines:** I architected custom data pipeline workflows utilising Webhooks and JavaScript (Google Apps Script) to capture, decrypt, and log real-time telemetry data transmitted from the remote gateways.
- **Data Cleaning & Validation:** Managing the ingestion of over **3 million data points**, I developed automated filtering algorithms in Python (utilising Pandas and SciPy). These algorithms successfully identified and isolated sensor drift, warm-up anomalies, and false readings while preserving the raw telemetry for post-hoc reliability analysis.

---

### 4. Observational analysis & Policy impact

The ultimate value of this engineering effort was the translation of raw telemetry into actionable municipal policy.

By applying advanced statistical analyses to the cleaned 24-month dataset, my Python algorithms successfully isolated **thermal solar loading anomalies** specific to certain building infrastructures. I provided an evidence base quantifying the severe exposure levels and comfort risks experienced by students in prefabricated container classrooms.

When benchmarked against international environmental standards (SANS, WHO, ASHRAE, ISO), these data-driven findings were used to justify immediate capital expenditure, resulting in the successful execution of roof retrofitting for the affected schools.

<div class="row justify-content-center text-center mt-4">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/2025-indoorairquality-project/bae_plots.png" title="Thermal Solar Loading Analysis" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">Data visualisation demonstrating the automated detection of thermal solar loading anomalies, which directly justified municipal roof retrofitting.</div>
