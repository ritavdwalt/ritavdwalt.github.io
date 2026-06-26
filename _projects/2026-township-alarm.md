---
layout: page
title: Mass-Scale IoT Alarm System for Informal Settlements
description: An end-to-end, commercially deployed security node engineered for mass rollout in South African townships, featuring extreme DFM and cost-optimised hardware. <br> <span class="badge badge-pill badge-primary">Commercial IoT</span> <span class="badge badge-pill badge-info">DFM & Mass Scale</span> <span class="badge badge-pill badge-success">Firmware</span> <span class="badge badge-pill badge-warning">Product Management</span>
img: assets/img/projects/2026-township-alarm/pcb_3d_isometric.png
importance: 1
category: "Highlights"
---

Deploying hardware in informal settlements presents one of the most rigorous engineering challenges in the IoT industry. Devices must be exceptionally low-cost for mass scalability, yet physically robust enough to survive extreme indoor temperatures, dust, unstable power grids, and physical tampering.

Partnering with a major infrastructure provider deploying connectivity in South African townships, I directed the end-to-end development of a bespoke, mass-scale IoT alarm system designed specifically for shack environments. This device includes a **whatsapp-operated arming and disarming**, **motion detect**, **siren integration**, **panic button** and **fire sensor**. 

Operating as the lead systems architect and technical product manager, I drove the complete product lifecycle: from initial customer engagement and requirement scoping, through custom hardware and firmware engineering, enclosure design, and the final transition to mass manufacturing (DFM).

---

### 1. Hardware architecture & IP-Protected DFM

When engineering for a mass rollout, every cent on the Bill of Materials (BOM) compounds. The hardware architecture required relentless optimisation to balance aggressive unit-cost targets with unwavering field reliability.

- **Cost-Optimised Topology:** Architected the core processing and connectivity hardware to minimise the component count without sacrificing security or uptime.
- **Design for Mass Manufacturing (DFM):** Transitioned the board from early-stage prototyping to a fully optimised state for high-volume pick-and-place assembly. This included standardising component packages, optimising trace routing for automated optical inspection (AOI), and managing global supply chain lead times.
- **Power Resilience:** Engineered robust power management circuitry to handle the erratic voltage spikes, brownouts, and load shedding endemic to the deployment environment, ensuring the alarm logic remains active and uncorrupted during grid failures.

_Note: Due to active commercial Non-Disclosure Agreements (NDAs) and IP protection protocols, exact schematics and proprietary component selections cannot be disclosed. The provided 3D render has been deliberately sanitised, with silkscreen overlays and part numbers removed._

<div class="row justify-content-center text-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        <!-- Placeholder for your sanitised PCB render -->
        {% include figure.liquid loading="eager" path="assets/img/projects/2026-township-alarm/pcb_3d_topview_redacted.png" title="Sanitised PCB Render" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">A sanitised 3D Altium render of the production-candidate PCB, demonstrating the highly optimised, scalable footprint designed for high-volume manufacturing.</div>

---

### 2. Embedded firmware & Edge logic

In a security application, false positives destroy user trust, while false negatives defeat the product's purpose. The firmware had to be exceptionally resilient to edge cases.

- **State-Machine Architecture:** Authored the embedded C/C++ firmware utilising a rigid state-machine architecture to handle complex trigger logic, arming delays, and network reconnection loops seamlessly.
- **Network Resilience:** Developed robust connectivity protocols capable of queuing, encrypting, and pushing critical telemetry and alarm payloads even in low-bandwidth or highly congested network environments.
- **Over-The-Air (OTA) Readiness:** Configured the firmware foundation to support scalable fleet management, allowing the partner to push vital security updates and feature enhancements to thousands of distributed nodes remotely.

---

### 3. Mechanical enclosure & Environmental design

The physical reality of an informal settlement requires enclosures that are as tough as they are cost-effective.

- **Custom 3D CAD Design:** Utilised Autodesk Inventor to design a bespoke enclosure tailored precisely to the custom PCB footprint.
- **Tamper & Environment Resistance:** The mechanical design incorporated specific mounting strategies and tamper-evident features to prevent unauthorised removal, while accounting for thermal dissipation in uninsulated, corrugated iron structures that regularly exceed standard operating temperatures.
- **Tooling Preparation:** Optimised the enclosure wall thicknesses, draft angles, and snap-fits to prepare the CAD models for large-scale injection molding tooling.

<div class="row justify-content-center text-center mt-4">
    <div class="col-sm-8 mt-3 mt-md-0">
        <!-- Placeholder for your enclosure design -->
        {% include figure.liquid loading="eager" path="assets/img/projects/2026-township-alarm/photo_3d_enclosure.jpg" title="Enclosure CAD Model" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">Autodesk Inventor mechanical design of the alarm enclosure, engineered for injection molding and rapid field installation.</div>

---

### 4. Customer engagement & Commercial rollout

Engineering a product is only half the battle; ensuring it perfectly aligns with the client's business model is what dictates a successful mass rollout.

- **Stakeholder Management:** Acted as the primary technical interface with the client, translating high-level business requirements and township security challenges into strict engineering deliverables and firmware logic.
- **Quality Assurance & Testing:** Developed the automated testing jigs and QA protocols required by the manufacturing partner to rapidly flash and verify the boards at scale as they come off the assembly line.
- **Deployment Readiness:** Successfully delivered the final production-candidate hardware and firmware packages, paving the way for the impending mass rollout across targeted informal settlements.
