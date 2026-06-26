---
layout: page
title: Commercial E-Bike Telemetry & Fleet Management
description: Lead Project Engineer for an in-development, enterprise-scale cargo e-bike telemetry system focusing on real-time location tracking and battery lifecycle management. <br> <span class="badge badge-pill badge-primary">Lead Project Engineer</span> <span class="badge badge-pill badge-info">Commercial Telemetry</span> <span class="badge badge-pill badge-success">Systems Architecture</span> <span class="badge badge-pill badge-warning">Active Development</span>
img: assets/img/projects/2026-ebike-telemetry/system_architecture_block.png
importance: 2
category: "Highlights"
---

_Note: This commercial hardware project is currently in the active design and development phase. Due to strict intellectual property protection, specific component selections, schematics, and the client identity have been omitted from this public portfolio._

---

Operating a commercial fleet of cargo e-bikes at scale requires far more than just mechanical reliability; it requires absolute, real-time visibility into the health, location, and security of every asset in the field.

Currently operating as the **Lead Project Engineer**, I am directing the end-to-end design and delivery of a bespoke, mass-scale telemetry and battery health management system. This project requires balancing complex mixed-signal hardware design with high-level cloud data ingestion, all while adhering to strict commercial cost constraints and Design for Manufacturing (DFM) requirements.

---

### 1. The Engineering challenge: Fleet-Scale visibility

When managing a decentralised fleet of high-value cargo e-bikes, operational efficiency relies entirely on data. If a bike’s battery fails mid-route, or if an asset is moved outside of a designated geofence, the fleet operators need to know instantly.

The core engineering challenge of this project is to develop a central telemetry node that securely interfaces with the e-bike's internal systems, extracts critical operational data, and pushes that payload to a cloud backend via a reliable cellular network, regardless of the bike's location.

### 2. High-Level system architecture

As the lead systems architect, I am responsible for defining the overarching hardware and telemetry pipeline. While the exact schematics remain proprietary, the system architecture encompasses several advanced technological domains:

- **Wireless Telemetry & GNSS:** Implementing low-power, high-resilience cellular connectivity to ensure continuous data transmission in variable urban environments, paired with highly accurate GNSS tracking for real-time location and geofencing capabilities.
- **BMS Integration & Diagnostics:** Engineering the hardware interfaces required to securely communicate with the e-bike's Battery Management System (BMS). This allows the telemetry node to extract deep diagnostic data, including state-of-charge, thermal parameters, and discharge cycle health, enabling predictive maintenance before a failure occurs in the field.
- **Ruggedised Environmental Design:** The hardware must survive constant high-frequency vibration, mechanical shock, and extreme weather conditions. The PCB and enclosure are being engineered to strict ingress protection (IP) ratings to guarantee multi-year field reliability.

<div class="row justify-content-center text-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        <!-- A generic block diagram showing Bike -> Telemetry Node -> Cloud -->
        {% include figure.liquid loading="eager" path="assets/img/projects/2026-ebike-telemetry/system_architecture_block.png" title="High-Level Telemetry Architecture" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">High-level abstraction of the telemetry data pipeline, illustrating the secure flow of diagnostics from the physical asset to the fleet management backend.</div>

---

### 3. Project leadership & Commercial delivery

Beyond the technical architecture, my role as Lead Project Engineer encompasses the complete commercial delivery lifecycle.

- **Requirements to Reality:** Translating high-level business objectives and fleet operational constraints into strict hardware specifications, firmware logic, and data payload structures.
- **Supply Chain & DFM:** Designing the system from day one for mass manufacturing. This involves navigating current global semiconductor lead times, prioritising high-availability components, and designing the PCB for rapid, automated assembly.
- **Cross-Functional Coordination:** Acting as the technical bridge between the hardware development, embedded firmware programming, and the backend software engineering teams to ensure the final product integrates seamlessly into the client's existing fleet management dashboards.
